# Distributed Logging System

#### Requirements

1. Collect logs for system metrics
2. Collect service logs
3. Logs should be searchable
4. Fault tolerant and highly available system

#### Solution

Put a kafka for queueing log events sent by file beats and prometheus, save metric logs to a TSDB and service logs to Elastic Search. Expose the whole thing on Kibana or Grafana.

![](https://2187286006-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FiQecqnXAxPpAqOy6q7mO%2Fuploads%2Flglul82i2fdVbzAJ2jlw%2Fimage.png?alt=media\&token=9b38f40e-05b0-47fe-ae2f-71eb4840b022)

#### Read This

{% content-ref url="notification-system.md" %}
[notification-system.md](notification-system.md)
{% endcontent-ref %}
