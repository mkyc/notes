# how to move kafka consumer offset back in time

describe the consumer group

```bash 
> kafka-consumer-groups --bootstrap-server 127.0.0.1:32400,127.0.0.1:32401,127.0.0.1:32402  --group CONSUMER-GROUP-NAME-CASE-SENSITIVE --describe 
```

reset the offset

```bash
> kafka-consumer-groups --bootstrap-server 127.0.0.1:32400,127.0.0.1:32401,127.0.0.1:32402  --group CONSUMER-GROUP-NAME-CASE-SENSITIVE --topic TOPIC-NAME-CASE-SENSITIVE --reset-offsets --to-offset 123 --execute
```

Consumers have to be disconnected from topic to apply the offset change. Otherwise following error will be thrown:

```bash
Error: Assignments can only be reset if the group 'CONSUMER-GROUP-NAME-CASE-SENSITIVE' is inactive, but the current state is Stable.
```
