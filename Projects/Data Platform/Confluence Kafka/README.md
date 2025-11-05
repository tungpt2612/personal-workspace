## Why Kafka?
- Because RDBMS could be ultilized for storing events/messages but isn't optimized for it.
- Kafka is created to handle event streaming and process streaming the moment events/messages arrive.
## What Kafka?
- Kafka is a **LOG** not a QUEUE. Meaning events/messages go into it will be immutable and will stay there unless there is configurations that cut off events/messages.
- Events/Messages structure have 2 main part:
    - **Key** - Could be blank
    - **Value** - Could be any format Avro, JSON, not limited to anything.
    - Additional part to provide context of the event/message like timestamp,etc
- Since the log is immutable so in case Topic have only one partition then events and message will come in ordered.
- Kafka Topic could also be partitioned using **KEY** to make sure all of the event/messages that has the same key will be put into 1 partition only without scattered every partitions without knowing what ordered is it.

## Where Kafka
- Could be host on bare metal or container named **BROKER** that could store all the topic as well as the background processes.
- A group of broker form a kafka cluster and requires ZooKeeper to manage and message between broker but with **KAFKA 4.0** there is only 1 method for manage the cluster called **KRAFT**

## How Kafka
- Kafka can also configure replica for topic to make sure it have redundancy, number of replica for topic/partition depended on **FACTOR NUMBER** and are scattered all broker.
- So there are Main topic and replica topic, the write operations will be perform on Main one and default to also read from main one.
- But can be configured to read from replica instead of main one to offload or optimized connection for consumer.