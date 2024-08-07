subject:: [[subject/cs]] 
parent:: [[data engineering]]
status:: active

- An open source, distributed, fault-tolerant streaming framework for high availability and low latency that follows a pub-sub model. The framework follows a master/workers relationship, where the master node keeps track of all the meta information regarding the setup, such as which topics are available, its consumers, and the replication factor and number of partitions for the topics (or maybe that's done by ZooKeeper).
- Concepts
	- Cluster
		- A group of containers that work together to handle incoming and outgoing streams.
	- Producers and Consumers
		- Producers write to a topic.
		- Consumers receive message published on a topic.
		- A consumer group distributes the load of processing messages by guaranteeing only one consumer from a consumer group will receive a message (to avoid duplication of processing).
	- Topics and Partitions
		- Topics are a way of logically grouping messages. For instance, all messages about a specific sensor could be written to the `/<sensor_name>` topic.
		- Partitions in kakfa are how the messages are physical grouped. They can be thought of as folders for simplicity. If a topic has 3 partitions, this means that each message on that topic can be written to one of three "folders". Which folder a message goes into depends on the value of the `partition_key` field for the message. The benefit of using partitions is that it distributes the load of both writing and reading messages. For this reason, you would ideally want messages to have `partition_key` values equally distributed.
	- Replication factor
		- This can be thought of as the number of backups for a topic. While this does not distribute write load, it does help distribute read load, and is useful if the original node is corrupted.
- Strengths
	- Low Write Latency
		- Writing to a Kafka topic is essentially writing to an append only log file (ignoring replication). This is a highly optimized operation and allows for very low latency when writing to Kafka.
			- "With Kafka, instead of maintaining as much as possible and flushing it to the file system when memory space runs out, all data is immediately written to a persistent log on the file system without flushing to disk. This means the data is essentially transferred into the kernel’s page cache. All logic for maintaining coherency between the cache and file system is in the OS, which tends to do so more efficiently and more correctly than one-off in-process attempts." - [source](https://docs.confluent.io/kafka/design/file-system-constant-time.html).
	- Distributed Nature
		- The ability for Kafka to scale horizontally is key to its widespread adoption. More producers and consumers can be easily added as separate compute nodes and connected to Kafka. Similarly, more Kafka worker nodes can be provisioned to allow for spreading the load of writing and reading messages.
	- Active community
- Weaknesses
	- Complicated Setup
	-
	-