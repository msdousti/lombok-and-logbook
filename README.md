# lombok-and-logbook

Project to discuss [Logbook issue 1705](https://github.com/zalando/logbook/issues/1705).

IntelliJ does not find a Lombok dependency in this project:
![image](https://github.com/msdousti/lombok-and-logbook/assets/3616518/1a435ea2-65fa-49c4-927e-c76654618dac)


Neither does running `mvn dependency:tree` show Lombok:

```
[INFO] Scanning for projects...
[INFO] 
[INFO] -------------------------< com.example:demo17 >-------------------------
[INFO] Building demo17 0.0.1-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- dependency:3.6.1:tree (default-cli) @ demo17 ---
[INFO] com.example:demo17:jar:0.0.1-SNAPSHOT
[INFO] +- org.springframework.boot:spring-boot-starter-web:jar:3.2.0:compile
[INFO] |  +- org.springframework.boot:spring-boot-starter:jar:3.2.0:compile
[INFO] |  |  +- org.springframework.boot:spring-boot:jar:3.2.0:compile
[INFO] |  |  +- org.springframework.boot:spring-boot-autoconfigure:jar:3.2.0:compile
[INFO] |  |  +- org.springframework.boot:spring-boot-starter-logging:jar:3.2.0:compile
[INFO] |  |  |  +- ch.qos.logback:logback-classic:jar:1.4.11:compile
[INFO] |  |  |  |  \- ch.qos.logback:logback-core:jar:1.4.11:compile
[INFO] |  |  |  +- org.apache.logging.log4j:log4j-to-slf4j:jar:2.21.1:compile
[INFO] |  |  |  |  \- org.apache.logging.log4j:log4j-api:jar:2.21.1:compile
[INFO] |  |  |  \- org.slf4j:jul-to-slf4j:jar:2.0.9:compile
[INFO] |  |  +- jakarta.annotation:jakarta.annotation-api:jar:2.1.1:compile
[INFO] |  |  \- org.yaml:snakeyaml:jar:2.2:compile
[INFO] |  +- org.springframework.boot:spring-boot-starter-json:jar:3.2.0:compile
[INFO] |  |  +- com.fasterxml.jackson.core:jackson-databind:jar:2.15.3:compile
[INFO] |  |  |  +- com.fasterxml.jackson.core:jackson-annotations:jar:2.15.3:compile
[INFO] |  |  |  \- com.fasterxml.jackson.core:jackson-core:jar:2.15.3:compile
[INFO] |  |  +- com.fasterxml.jackson.datatype:jackson-datatype-jdk8:jar:2.15.3:compile
[INFO] |  |  +- com.fasterxml.jackson.datatype:jackson-datatype-jsr310:jar:2.15.3:compile
[INFO] |  |  \- com.fasterxml.jackson.module:jackson-module-parameter-names:jar:2.15.3:compile
[INFO] |  +- org.springframework.boot:spring-boot-starter-tomcat:jar:3.2.0:compile
[INFO] |  |  +- org.apache.tomcat.embed:tomcat-embed-core:jar:10.1.16:compile
[INFO] |  |  +- org.apache.tomcat.embed:tomcat-embed-el:jar:10.1.16:compile
[INFO] |  |  \- org.apache.tomcat.embed:tomcat-embed-websocket:jar:10.1.16:compile
[INFO] |  +- org.springframework:spring-web:jar:6.1.1:compile
[INFO] |  |  +- org.springframework:spring-beans:jar:6.1.1:compile
[INFO] |  |  \- io.micrometer:micrometer-observation:jar:1.12.0:compile
[INFO] |  |     \- io.micrometer:micrometer-commons:jar:1.12.0:compile
[INFO] |  \- org.springframework:spring-webmvc:jar:6.1.1:compile
[INFO] |     +- org.springframework:spring-aop:jar:6.1.1:compile
[INFO] |     +- org.springframework:spring-context:jar:6.1.1:compile
[INFO] |     \- org.springframework:spring-expression:jar:6.1.1:compile
[INFO] +- org.zalando:logbook-spring-boot-starter:jar:3.7.0:compile
[INFO] |  +- org.zalando:logbook-spring-boot-autoconfigure:jar:3.7.0:compile
[INFO] |  |  +- org.zalando:logbook-core:jar:3.7.0:compile
[INFO] |  |  |  +- org.zalando:logbook-api:jar:3.7.0:compile
[INFO] |  |  |  \- org.zalando:logbook-common:jar:3.7.0:compile
[INFO] |  |  +- org.zalando:logbook-json:jar:3.7.0:compile
[INFO] |  |  +- org.zalando:logbook-spring:jar:3.7.0:compile
[INFO] |  |  \- org.zalando:logbook-servlet:jar:3.7.0:compile
[INFO] |  +- org.apiguardian:apiguardian-api:jar:1.1.2:compile
[INFO] |  +- org.zalando:faux-pas:jar:0.9.0:compile
[INFO] |  |  \- com.google.code.findbugs:jsr305:jar:3.0.2:compile
[INFO] |  \- org.slf4j:slf4j-api:jar:2.0.9:compile
[INFO] \- org.springframework.boot:spring-boot-starter-test:jar:3.2.0:test
[INFO]    +- org.springframework.boot:spring-boot-test:jar:3.2.0:test
[INFO]    +- org.springframework.boot:spring-boot-test-autoconfigure:jar:3.2.0:test
[INFO]    +- com.jayway.jsonpath:json-path:jar:2.8.0:compile
[INFO]    +- jakarta.xml.bind:jakarta.xml.bind-api:jar:4.0.1:test
[INFO]    |  \- jakarta.activation:jakarta.activation-api:jar:2.1.2:test
[INFO]    +- net.minidev:json-smart:jar:2.5.0:runtime
[INFO]    |  \- net.minidev:accessors-smart:jar:2.5.0:runtime
[INFO]    |     \- org.ow2.asm:asm:jar:9.3:runtime
[INFO]    +- org.assertj:assertj-core:jar:3.24.2:test
[INFO]    |  \- net.bytebuddy:byte-buddy:jar:1.14.10:test
[INFO]    +- org.awaitility:awaitility:jar:4.2.0:test
[INFO]    +- org.hamcrest:hamcrest:jar:2.2:test
[INFO]    +- org.junit.jupiter:junit-jupiter:jar:5.10.1:test
[INFO]    |  +- org.junit.jupiter:junit-jupiter-api:jar:5.10.1:test
[INFO]    |  |  +- org.opentest4j:opentest4j:jar:1.3.0:test
[INFO]    |  |  \- org.junit.platform:junit-platform-commons:jar:1.10.1:test
[INFO]    |  +- org.junit.jupiter:junit-jupiter-params:jar:5.10.1:test
[INFO]    |  \- org.junit.jupiter:junit-jupiter-engine:jar:5.10.1:test
[INFO]    |     \- org.junit.platform:junit-platform-engine:jar:1.10.1:test
[INFO]    +- org.mockito:mockito-core:jar:5.7.0:test
[INFO]    |  +- net.bytebuddy:byte-buddy-agent:jar:1.14.10:test
[INFO]    |  \- org.objenesis:objenesis:jar:3.3:test
[INFO]    +- org.mockito:mockito-junit-jupiter:jar:5.7.0:test
[INFO]    +- org.skyscreamer:jsonassert:jar:1.5.1:test
[INFO]    |  \- com.vaadin.external.google:android-json:jar:0.0.20131108.vaadin1:test
[INFO]    +- org.springframework:spring-core:jar:6.1.1:compile
[INFO]    |  \- org.springframework:spring-jcl:jar:6.1.1:compile
[INFO]    +- org.springframework:spring-test:jar:6.1.1:test
[INFO]    \- org.xmlunit:xmlunit-core:jar:2.9.1:test
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.747 s
[INFO] Finished at: 2023-12-06T22:23:10+01:00
[INFO] ------------------------------------------------------------------------
```
