SpringBoot项目整合prometheus
1、prometheus官方提供了SpringBoot的客户端，如下：
<dependency>
    <groupId>io.prometheus</groupId>
    <artifactId>simpleclient_spring_boot</artifactId>
</dependency>
但是该客户端已经不支持SpringBoot2。

由于SpringBoot2 的Actuator采用了Micrometer进行监控数据统计，而Micrometer提供了prometheus的支持，
我们可以用micrometer-registry-prometheus来集成SpringBoot2 ，加入相应的依赖

 <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-actuator</artifactId>
  </dependency>
 <dependency>
        <groupId>io.micrometer</groupId>
         <artifactId>micrometer-core</artifactId>
 </dependency>
 <dependency>
        <groupId>io.micrometer</groupId>
        <artifactId>micrometer-registry-prometheus</artifactId>
 </dependency>

添加监控项
统计http请求的总数量
如果要统计