subject:: [[subject/cs]] 
parent:: [[data engineering]]
status:: active

- An open source distributed streaming framework for high availability and low latency that follows a pub-sub model.
- Architecture
	- The framework follows a master/workers relationship, where the master node keeps track of all the meta information regarding the setup, such as which topics are available, its consumers, and the replication factor and number of partitions for the topics (or maybe that's done by ZooKeeper).
	- Publishers and Consumers
		- Publishers write to a topic.
		- Consumers receive message published on a topic.
		- A consumer group distributes the load of processing messages by g