subject:: [[subject/cs]] 
parent:: [[data engineering]]
status:: active

- An open source distributed streaming framework for high availability and low latency that follows a pub-sub model.
- Architecture
	- The framework follows a master/workers relationship, where the master node keeps track of all the meta information regarding the setup, such as which topics are available, its consumers, and the replication factor and number of partitions for the topics (or maybe that's done by ZooKeeper).
	- Publishers and Consumers
		- Publishers write to a topic.
		- Consumers receive message published on a topic.
		- A consumer group distributes the load of processing messages by guaranteeing only one consumer from a consumer group will receive a message (to avoid duplication of processing).
	- Topics and Partitions
		- Topics are a way of logically grouping messages. For instance, all messages about a specific sensor could be written to the `/<sensor_name>` topic.
		- Partitions are how the messages are physical grouped. They can be thought of as folders for simplicity. If a topic has 3 partitions, this means that each message on that topic can be written to one of three "folders".