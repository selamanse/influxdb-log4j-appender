# influxdb-log4j-appender
InfluxDb Appenders for Log4j

## Motivation

Log4j is widely used as logging tool. 
As there was a lack of an proper Implementation of an InfluxDB Appender I tried my best here.

## InfluxDb support

This Appender uses the [influx-java 2.4 driver](https://github.com/influxdb/influxdb-java), supporting only Versions >0.9 of InfluxDb

## Usage with log4j.properties

How to add this appender to log4j.properties:

```properties
# InfluxDb Appender
log4j.appender.INFLUXDB=info.scheinfrei.log4j.InfluxDbAppender

# Optional settings. The current values are the default ones
#log4j.appender.INFLUXDB.host = localhost
#log4j.appender.INFLUXDB.port = 8086
#log4j.appender.INFLUXDB.username = "root"
#log4j.appender.INFLUXDB.password = ""
#log4j.appender.INFLUXDB.databaseName = "Logging"
#log4j.appender.INFLUXDB.measurement = "log_entries"
#log4j.appender.INFLUXDB.appName = "default"
#log4j.appender.INFLUXDB.retentionPolicy = "autogen"
#log4j.appender.INFLUXDB.consistencyLevelWrite = "ONE"
```

## Usage with log4j.xml

How to add this appender to log4j.xml:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE log4j:configuration SYSTEM "log4j.dtd">

<log4j:configuration xmlns:log4j="http://jakarta.apache.org/log4j/">
  <appender name="INFLUXDB" class="info.scheinfrei.log4j.InfluxDbAppender"> 
    <!-- Optional settings. The current values are the default ones -->
    <!--<param name="host" value="localhost"/>-->
    <!--<param name="port" value="8086"/>-->
    <!--<param name="username" value="root"/>-->
    <!--<param name="password" value=""/>-->
    <!--<param name="databaseName" value="Logging"/>-->
    <!--<param name="measurement" value="log_entries"/>-->
    <!--<param name="appName" value="default"/>-->
    <!--<param name="retentionPolicy" value="autogen"/>-->
    <!--<param name="consistencyLevelWrite" value="ONE"/>-->
  </appender> 

  <root> 
    <priority value ="info" /> 
    <appender-ref ref="INFLUXDB" /> 
  </root>
  
</log4j:configuration>
```

## How to build:

  `mvn install -DskipTests=true`

## Future plans

 * BatchPoint mode support
 * layout support
 
## License
 
  Licensed under the Apache License, Version 2.0 (the "License");
