# Spring Boot Rest Template Builder example

Example why to use RestTemplateBuilder instead of create your own instance of a RestTemplate.

```bash
curl http://localhost:8080/first
``` 

Sleuth distributed tracing is broken:

```
2019-07-02 21:02:38.117  INFO [-,917abb9dfdaeca7d,917abb9dfdaeca7d,false] 24753 --- [nio-8080-exec-1] c.e.resttemplate.SelfInvokingController  : Received call to first, calling second
2019-07-02 21:02:38.152  INFO [-,e317f161c3b6f5bf,e317f161c3b6f5bf,false] 24753 --- [nio-8080-exec-2] c.e.resttemplate.SelfInvokingController  : Received call to second
2019-07-02 21:02:38.168  INFO [-,917abb9dfdaeca7d,917abb9dfdaeca7d,false] 24753 --- [nio-8080-exec-1] c.e.resttemplate.SelfInvokingController  : Received response from second: hello from second
```


Metrics for http server requests:

[http://localhost:8080/actuator/metrics/http.server.requests](http://localhost:8080/actuator/metrics/http.server.requests)
