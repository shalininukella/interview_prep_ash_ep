# Fault Tolerant Microservices

#### Circuit Breaker

If a timeout is happening then services may keep hanging making all threads occupied. We should break asap if the service is going to return unsuccessful response.

Can be implemented using a sidecar that tracks % of failed requests, once %failed > threshold then return failed response immediately.

Accept -> _(threshold breached) -> Stop -> (timeout expired) ->_ Allow Partial -> (_threshold reset_) -> Accept again

#### Bulkhead Pattern

One slow proxied service can hog all threads.

Do not allow more than `threads_count/service_count`

{% embed url="https://www.youtube.com/watch?v=R2FT5edyKOg" %}

{% embed url="https://www.youtube.com/watch?t=249s&v=ADHcBxEXvFA" %}
