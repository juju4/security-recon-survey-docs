# Logs format

## Web server

For webserver, if WAF in front of it, ensure that webserver logs use X-Forwarded-For to have real source IP!!!

* <https://xorl.wordpress.com/2012/09/28/admin-mistake-f5-load-balancer-snat-ip-address-apache-logging/>
* <https://devcentral.f5.com/s/articles/dire-load-balancing-straits-i-want-my-client-ip>
* <https://www.haproxy.com/documentation/hapee/1-9r1/traffic-management/http-rewrite/>

Regex webserver

```regex
{"time":".*","time_local":".*","remote_addr":".*","remote_user":".*","request":".*","request_method":".*","uri": ".*","query_parameters":".*","protocol":".*","request_time":".*","status":"[0-9]+","body_bytes_sent":".*","http_referrer":".*","http_user_agent":".*","vhost":".*","xff":".*".*}
```

### Apache

* <https://httpd.apache.org/docs/current/mod/mod_log_config.html>
* <https://blog.rapid7.com/2014/08/12/json-logging-in-apache-and-nginx-with-logentries/>

```apache2.conf
LogFormat "{ \"time\":\"%t\", \"remoteIP\":\"%a\", \"host\":\"%V\", \"request\":\"%U\", \"query\":\"%q\", \"method\":\"%m\", \"status\":\"%>s\", \"userAgent\":\"%{
User-agent}i\", \"referer\":\"%{Referer}i\" }" combined_json
# same field name than nginx
LogFormat "{ \"time\":\"%t\", \"remote_addr\":\"%a\", \"remote_user\":\"%u\", \"host\":\"%V\", \"request\":\"%U\", \"query\":\"%q\", \"request_method\":\"%m\", \"request_time\":\"%T\", \"status\":\"%>s\", \"http_user_agent\":\"%{User-agent}i\", \"http_referer\":\"%{Referer}i\" }" combined_json
```

* <https://stackoverflow.com/questions/39592834/how-to-make-apache-output-its-logs-in-json-instead-of-its-default-logging-format>
* <https://httpd.apache.org/docs/2.4/logs.html>

```apache2.conf
ErrorLogFormat "{ \"time\":\"%{%Y-%m-%d}tT%{%T}t.%{msec_frac}tZ\", \"function\" : \"[%-m:%l]\" , \"process\" : \"[pid %P:tid %T]\" , \"message\" : \"%M\" ,\ \"refe
rer\"\ : \"%{Referer}i\" },"
ErrorLogFormat "{ \"time\":\"%{cu}tZ\", \"function\" : \"[%-m:%l]\" , \"process\" : \"[pid %P:tid %T]\" , \"message\" : \"%M\"}"
LogFormat "{ \"time\":\"%{%Y-%m-%d}tT%{%T}t.%{msec_frac}tZ\", \"process\":\"%D\", \"filename\":\"%f\", \"remoteIP\":\"%a\", \"host\":\"%V\", \"request\":\"%U\", \"
query\":\"%q\", \"method\":\"%m\", \"status\":\"%>s\", \"userAgent\":\"%{User-agent}i\", \"referer\":\"%{Referer}i\" }," combined
LogFormat "{ \"time\":\"%t\", \"remoteIP\":\"%a\", \"host\":\"%V\", \"request\":\"%U\", \"query\":\"%q\", \"method\":\"%m\", \"status\":\"%>s\", \"userAgent\":\"%{
User-agent}i\", \"referer\":\"%{Referer}i\" }"
```

%{X-Forwarded-For}i as remote_addr if WAF/LB

```log
{ "time":"2020-07-27T04:04:44+0000", "time_local":"[27/Jul/2020:04:04:44 +0000]", "remote_addr":"127.0.0.1", "remote_user":"-", "host":"localhost", "request":"OPTIONS / HTTP/1.1", "uri":"/", "query_parameters":"", "protocol":"HTTP/1.1", "request_method":"OPTIONS", "request_time":"0", "status":"403", "http_user_agent":"curl/7.68.0", "http_referer":"-", "vhost":"localhost", "xff":"-" }
```

### Nginx

* <https://nginx.org/en/docs/http/ngx_http_log_module.html#log_format>
* <https://github.com/juju4/ansible-harden-nginx/blob/master/templates/harden-nginx-server.j2#L43>

```nginx.conf
log_format combined_json escape=json
  '{'
    '"time":"$time_iso8601",'
    '"time_local":"$time_local",'
    '"remote_addr":"$remote_addr",'
    '"remote_user":"$remote_user",'
    '"request":"$request",'
    '"request_method":"$request_method",'
    '"request_time":"$request_time",'
    '"status": "$status",'
    '"body_bytes_sent":"$body_bytes_sent",'
    '"http_referrer":"$http_referer",'
    '"http_user_agent":"$http_user_agent"'
  '}';
```

```log
{"time":"2020-07-26T22:12:35+00:00","time_local":"26/Jul/2020:22:12:35 +0000","remote_addr":"127.0.0.1","remote_user":"","request":"HEAD / HTTP/2.0","request_method":"HEAD","uri": "/index.html","query_parameters": "","protocol": "HTTP/2.0","request_time":"0.000","status": "200","body_bytes_sent":"0","http_referrer":"","http_user_agent":"curl/7.68.0","cookie_COOKIE":""}
```

### Tomcat

* <https://tomcat.apache.org/tomcat-9.0-doc/config/valve.html#Access_Log_Valve>
* <https://tomcat.apache.org/tomcat-7.0-doc/api/org/apache/catalina/valves/AccessLogValve.html>

```config
<Valve className="org.apache.catalina.valves.AccessLogValve" directory="logs"
               prefix="localhost_access_log." suffix=".txt"
               pattern="%h %l %u %t &quot;%r&quot; %s %b" />
%h - Remote host name (or IP address if enableLookups for the connector is false)
%l - Remote logical username from identd (always returns '-')
%u - Remote user that was authenticated (if any), else '-'
%t - Date and time, in Common Log Format
%r - First line of the request (method and request URI)
%s - HTTP status code of the response
%b - Bytes sent, excluding HTTP headers, or '-' if zero

pattern="{&quot;time&quot;:&quot;%t&quot;,&quot;remote_addr&quot;:&quot;%h&quot;,&quot;remote_user&quot;:&quot;%u&quot;,&quot;request&quot;:&quot;%r&quot;,&quot;request_method&quot;:&quot;%m&quot;,&quot;uri&quot;:&quot;%U&quot;,&quot;query_parameters&quot;:&quot;%q&quot;,&quot;protocol&quot;:&quot;%H&quot;,&quot;request_time&quot;:&quot;%D&quot;,&quot;status&quot;:&quot;%s&quot;,&quot;body_bytes_sent&quot;:&quot;%b&quot;,&quot;http_referrer&quot;:&quot;%{Referer}i&quot;,&quot;http_user_agent&quot;:&quot;%{User-Agent}i&quot;}"
```

if LB/WAF, use `<Valve className="org.apache.catalina.valves.RemoteIpValve" />`

```log
{"time":"2020-08-02T13:49:48.130Z","time_local":"[02/Aug/2020:13:49:48 +0000]","remote_addr":"0:0:0:0:0:0:0:1","remote_user":"-","request":"GET / HTTP/1.1","request_method":"GET","uri":"/","query_parameters":"","protocol":"HTTP/1.1","request_time":"16","status":"302","body_bytes_sent":"-","http_referrer":"http://www.example.com","http_user_agent":"curl/7.61.1","jira_request_id":"829x4x1","jira_request_username":"-"}
```

### misc

%{X-Forwarded-For}i as remote_addr if WAF/LB

### Haproxy

* <https://www.haproxy.com/blog/introduction-to-haproxy-logging/>
mode tcp `log-format "%ci:%cp [%t] %ft %b/%s %Tw/%Tc/%Tt %B %ts %ac/%fc/%bc/%sc/%rc %sq/%bq"`
* <https://www.haproxy.com/documentation/hapee/latest/onepage/#8.2.3>
mode http, `log-format "%ci:%cp [%tr] %ft %b/%s %TR/%Tw/%Tc/%Tr/%Ta %ST %B %CC %CS %tsc %ac/%fc/%bc/%sc/%rc %sq/%bq %hr %hs %{+Q}r"`
* <https://jablonskis.org/2014/haproxy-logging-to-syslog-in-json/index.html>
`log-format {"time":%Ts,"remote_addr":"%ci","request":"%HP","query":"%HQ","request_method":"%HM","status":%ST,"body_bytes_sent":%B,"ssl_version":"%sslv","ssl_ciphers":"%sslc","session_duration":"%Tt","termination_state":"%ts"}`

```log
{"time":1595875297,"time_local":"27/Jul/2020:18:41:37 +0000","remote_addr":"127.0.0.1","request":"GET /?a=b&c=d HTTP/1.1","uri":"/","query":"?a=b&c=d","request_method":"GET","status":503,"body_bytes_sent":212,"ssl_version":"-","ssl_ciphers":"-","session_duration":"0","termination_state":"SC"}
```

Regex haproxy

```regex
{"time":".*","time_local":".*","remote_addr":".*","request":".*","request_method":".*","uri":".*","query_parameters":".*","request_time":".*","status":"[0-9]+","body_bytes_sent":".*","ssl_version":".*","ssl_ciphers":".*","session_duration":".*","termination_state":".*".*}
```

### F5

* <https://techdocs.f5.com/en-us/bigip-15-0-0/big-ip-asm-implementations/logging-application-security-events.html#GUID-E0742D0B-9829-4210-AD70-EAFFD58B9767>

> From the Logging Format list, select the appropriate type:
> To store traffic on a remote logging server in CSV format, select Comma Separated Values
> To store traffic on a reporting server (such as Splunk) using a preconfigured storage format with key-value pairs in the log messages, select Key-Value Pairs
> If your network uses ArcSight logs, select Common Event Format (ArcSight)
> To store logs on the BIG-IQ system, select BIG-IQ

* <https://devcentral.f5.com/s/articles/f5-analytics-iapp> = json
