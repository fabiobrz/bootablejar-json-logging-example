# Bootable JAR JSON logging example

Demonstrates configuring JSON logging for Bootable JAR.

## Build
```text
mvn clean package
```

## Run
```text
mvn wildfly-jar:run
```

## Verify
1. Call the app `Hello World` endpoint
```text
curl http://localhost:8080/hello
Hello from XP bootable jar!
```
2. Check the console logs to be in JSON format, e.g.:
```text
...
{"@timestamp":"2021-03-16T10:44:27.665+01:00","sequence":36,"loggerClassName":"org.jboss.logging.Logger","loggerName":"com.example.logging.HelloWorldEndpoint","level":"DEBUG","message":"HelloWorldEndpoint.doGet called","threadName":"default task-1","threadId":102,"mdc":{},"ndc":"","hostName":"fburzigo.remote.csb","processName":"logging-bootable.jar","processId":30244,"version":"1"}
```

## JBoss EAP profile
Add `-Peap` or `-Deap` to the above mentioned `mvn` command to build and run the app with JBoss EAP artifacts (Bootable 
JAR Maven plugin and WildFly Feature Pack), e.g.: 
```text
mvn clean package -Deap
```
