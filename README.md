## How to send Windows EventLogs into Graylog

Windows cannot forward EventLog via the network to a central place like Graylog. You'll have to run an agent that can talk to Graylog. Good news is that there are two officially recommended agents:

### Graylog Sidecar

The [Graylog Collector Sidecar](https://github.com/Graylog2/collector-sidecar) is a supervisor process for 3rd party log collectors like NXLog or beats. The Sidecar program is able to fetch configurations from a Graylog server and render them as a valid configuration file for various log collectors. You can think of it like a centralized configuration management system for your log collectors.

Please [read the official documentation](http://docs.graylog.org/en/latest/pages/collector_sidecar.html) to learn how to use the Graylog Collector Sidecar.

### nxlog

The [NXLog Community Edition](http://nxlog.org/products/nxlog-community-edition) is suitable to forward Windows EventLog to Graylog natively. Please refer to their official documentation for more information.

### Graylog Collector (deprecated)

The Graylog Collector is a lightweight Java application that allows you to forward data from log files to a Graylog cluster. The collector can read local log files and also Windows Events natively, it then can forward the log messages over the network using the [GELF](https://www.graylog.org/resources/gelf/) format.

Please [read the official documentation](http://docs.graylog.org/en/latest/pages/collector.html#graylog-collector) to learn how to use the Graylog Collector to forward Windows EventLog.
