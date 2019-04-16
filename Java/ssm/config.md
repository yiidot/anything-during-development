# 配置cors
1. 引入cors-filter
```xml
<!-- https://mvnrepository.com/artifact/com.thetransactioncompany/cors-filter -->
<dependency>
    <groupId>com.thetransactioncompany</groupId>
    <artifactId>cors-filter</artifactId>
    <version>2.6</version>
</dependency>
```
2.配置web.xml
<filter>  
    <filter-name>CORS</filter-name>  
    <filter-class>com.thetransactioncompany.cors.CORSFilter</filter-class>  
    <init-param>  
     <param-name>cors.allowOrigin</param-name>  
        <param-value>*</param-value>  
    </init-param>  
    <init-param>  
     <param-name>cors.supportedMethods</param-name>  
        <param-value>GET, POST, HEAD, PUT, DELETE</param-value>  
    </init-param>  
    <init-param>  
     <param-name>cors.supportedHeaders</param-name>  
        <param-value>Accept, Origin, X-Requested-With, Content-Type, Last-Modified</param-value>  
    </init-param>  
    <init-param>  
        <param-name>cors.exposedHeaders</param-name>  
        <param-value>Set-Cookie</param-value>  
    </init-param>  
    <init-param>  
        <param-name>cors.supportsCredentials</param-name>  
        <param-value>true</param-value>  
    </init-param>  
</filter>  
<filter-mapping>  
    <filter-name>CORS</filter-name>  
    <url-pattern>/*</url-pattern>  
</filter-mapping>  
