# System Design

udemy.com/course/pragmatic-system-design

## Estimates
- https://colin-scott.github.io/personal_website/research/interactive_latency.html
- https://gist.github.com/jboner/2841832
- 

| Component         | Read per sec  | Write per sec |
|-------------------|---------------|---------------|
| RDBMS             | 10.000        | 5.000         |
| Distributed Cache | 100.000       | 100.000       |
| Message Queue     | 100.000       | 100.000       |
| NoSQL             | 20.000-50.000 | 10.000-25.000 |



| Component         | Maximum Effective Capacity |
|-------------------|----------------------------|
| RDBMS             | 3TB                        |
| Distributed Cache | 16-128GB                   |
| NoSQL             | Depends on Type            |

## Network

### Load Balancer
- Load balancer is a machine that runs a reverse proxy software
- Goal of the software is to distribute the requests between multiple servers that host the actual application.

#### Strategies (Most Usage)
- Round Robin
  - Directs to services sequentially
- Least connections
- Rsource based
- Weighted variants of the abose
- Random

#### Types
- Layer 4
  - Low level
- Layer 7
  - High Level
  - App level

https://www.nginx.com/resources/glossary/layer-4-load-balancing/

#### Benefits
- Resilience
- Scalailable

### CDN (Context Delivery Network)
https://cloudflare.com/en-gb/learning/cdn/what-is-a-cdn/
- CDN caching your static files for fast accessibility
- Your files uploades to the cdn servers.

#### Types
- Push
  - Push all files to the cdn servers from normal server without any request.
- Pull
  - When cdn server take a request, it looks static files. If it doesnt have, it pulls this file. (Lazy)

## Caching
- Caching Strategies
  - https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/Strategies.html
- Eviction Policies
  - https://www.codingninjas.com/studio/library/least-frequently-used-cache

## Queues
- Messaging
  - https://dzone.com/articles/comparing-publish-subscribe-messaging-and-message
- RabbitMQ
  - https://www.cloudamqp.com/blog/part1-rabbitmq-for-beginners-what-is-rabbitmq.html
  - https://www.cloudamqp.com/blog/the-relationship-between-connections-and-channels-in-rabbitmq.html
- Kafka
  - https://medium.com/@durgaswaroop/a-practical-introduction-to-kafka-storage-internals-d5b544f6925f
  - https://timothystepro.medium.com/visualizing-kafka-20bc384803e7
  - https://www.confluent.io/blog/how-choose-number-topics-partitions-kafka-cluster/
- 