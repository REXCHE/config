



set u client in the discovery first or the config first mode 


### “client-config-first”
```courseignore
spring:
  application:
    name: client-config-first
  profiles:
    active: local
  cloud:
    config:
      uri: http://localhost:8672
      fail-fast: true
      retry:
        max-attempts: 20
        max-interval: 15000
        initial-interval: 10000
server:
  port: 8763

```

### client-discovery-first

```courseignore
spring:
  application:
    name: client-discovery-first
  profiles:
    active: local
  cloud:
    config:
      fail-fast: true
      retry:
        max-attempts: 20
        max-interval: 15000
        initial-interval: 10000
       discovery:
        enabled: true
        service-id: config-server
server:
  port: 8764

eureka:
  client:
    enabled: true
    register-with-eureka: true
    fetch-registry: true
    serviceUrl:
      defaultZone: http://localhost:8761/eureka

```



this is the link 

https://medium.com/@athulravindran/spring-cloud-config-server-discovery-first-vs-config-first-72cc6a56f471


this is the github
https://github.com/athulravindran87/spring-cloud-config/blob/master/client-discovery-first/src/main/resources/bootstrap.yaml


