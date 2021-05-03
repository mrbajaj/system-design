## System Design Basics
* Key Characteristics and Fundamentals of Distributed Systems
* Monolithic VS Microservice (Service Discovery, Resiliency)
* Vertical vs horizontal scaling
* CAP theorem
* ACID vs BASE
* Redundancy and Replication
* Partitioning/Sharding 
* Consistent Hashing
* Optimistic vs pessimistic locking
* Strong vs eventual consistency
* SQL vs NoSQL
* Types of NoSQL (Key value, Wide column, Document-based, Graph-based)
* Caching
* Data center/racks/hosts
* CPU/memory/Hard drives/Network bandwidth
* Random vs sequential read/writes to disk
* HTTP vs HTTP2 vs WebSocket
* Long-Polling vs WebSockets vs Server-Sent Events
* TCP/IP model
* IPv4 vs IPv6
* TCP vs UDP
* DNS lookup
* HTTP & TLS
* Public key infrastructure and certificate authority(CA)
* Symmetric vs asymmetric encryption
* Load Balancing
* Consistent Hashing
* CDNs & Edges
* Data Partitioning
* Indexes
* Master-Slave, Master-Master
* Active-Passive, Active-Active
* Leader election
* Design patterns and Object-oriented design
* Virtual machines and containers
* Pub-sub architecture 
* REST, GraphQL
* MapReduce
* Bloom filters and Count-Min sketch
* Paxos 
* Multithreading, locks, synchronization, CAS(compare and set)
* Proxies

## Tools and Technologies
* Cassandra
* MongoDB/Couchbase
* RabbitMQ / Azure Service Bus
* Mysql / PostgreSQL
* Memcached
* Redis
* Zookeeper
* Kafka
* NGINX
* HAProxy
* Solr, Elastic search
* Amazon, EC2, S3
* Docker, Kubernetes
* Hadoop/Spark and HDFS
* Eureka, Hysterix
* Heroku / Azure DevOps
* Jenkins CI/CD
    
## System Design Problems (HLD + LLD)
* TinyURL
* Instagram | Photo hosting platform
* Timeline | Newsfeed | Twitter
* Dropbox | Google Drive
* Whatsapp | Facebook Messenger [NL](https://www.youtube.com/watch?v=L7LtmfFYjc4&t=690s) [GS](https://www.youtube.com/watch?v=vvhC64hQZMk&t=1267s)
* MakeMyTrip | BookMyShow
* Amazon | Flipkart
* Youtube | Netflix
* Uber | IRCTC
* Swiggy | Zomato
* Yelp | Nearby
* Twitter Search
* Google Search
* SplitWise
* Zerodha
* API Rate Limiter
* Web Crawler
* Rate limiting system 
* Distributed cache 
* Typeahead Suggestion | Auto-complete system
* Recommendation System

## Low Level Design Problems (Class diagram)
* Elevator system 
* Snake and Ladder game
* Tic Tac Toe
* ATM machine
* Traffic Control System
* Vehicle Parking System
* Online Coding Platform [problem-statement](https://github.com/hocyadav/leetcode-lld-flipkart-coding-blox)

## System Design Interview Approach Template
### THINGS TO CONSIDER [5 min]
<pre><code>    (1) Features
    (2) API
    (3) Availability
    (4) Latency
    (5) Scalability
    (6) Durability
    (7) Class Diagram
    (8) Security and Privacy
    (9) Cost-effective
</code></pre>
### FEATURE EXPECTATIONS [5 min]
<pre><code>    (1) Use cases
    (2) Scenarios that will not be covered
    (3) Who will use
    (4) How many will use
    (5) Usage patterns
</code></pre>
### ESTIMATIONS [5 min]
<pre><code>    (1) Throughput (QPS for read and write queries)
    (2) Latency expected from the system (for read and write queries)
    (3) Read/Write ratio
    (4) Traffic estimates
            - Write (QPS, Volume of data)
            - Read  (QPS, Volume of data)
    (5) Storage estimates
    (6) Memory estimates
            - If we are using a cache, what is the kind of data we want to store in cache
            - How much RAM and how many machines do we need for us to achieve this ?
            - Amount of data you want to store in disk/ssd
</code></pre>
###  DESIGN GOALS [5 min]
<pre><code>    (1) Latency and Throughput requirements
    (2) Consistency vs Availability  [Weak/strong/eventual =&gt; consistency | Failover/replication =&gt; availability]
</code></pre>
### HIGH LEVEL DESIGN [5-10 min]
<pre><code>    (1) APIs for Read/Write scenarios for crucial components
    (2) Database schema
    (3) Basic algorithm
    (4) High level design for Read/Write scenario
</code></pre>
### DEEP DIVE [15-20 min]
<pre><code>    (1) Scaling the algorithm
    (2) Scaling individual components: 
            -&gt; Availability, Consistency and Scale story for each component
            -&gt; Consistency and availability patterns
    #### Think about the following components, how they would fit in and how it would help
            a) DNS
            b) CDN [Push vs Pull]
            c) Load Balancers [Active-Passive, Active-Active, Layer 4, Layer 7]
            d) Reverse Proxy
            e) Application layer scaling [Microservices, Service Discovery]
            f) DB [RDBMS, NoSQL]
                    &gt; RDBMS 
                        &gt;&gt; Master-slave, Master-master, Federation, Sharding, Denormalization, SQL Tuning
                    &gt; NoSQL
                        &gt;&gt; Key-Value, Wide-Column, Graph, Document
                            Fast-lookups:
                            -------------
                                &gt;&gt;&gt; RAM  [Bounded size] =&gt; Redis, Memcached
                                &gt;&gt;&gt; AP [Unbounded size] =&gt; Cassandra, RIAK, Voldemort
                                &gt;&gt;&gt; CP [Unbounded size] =&gt; HBase, MongoDB, Couchbase, DynamoDB
            g) Caches
                    &gt; Client caching, CDN caching, Webserver caching, Database caching, Application caching, Cache @Query level, Cache @Object level
                    &gt; Eviction policies:
                            &gt;&gt; Cache aside
                            &gt;&gt; Write through
                            &gt;&gt; Write behind
                            &gt;&gt; Refresh ahead
            h) Asynchronism
                    &gt; Message queues
                    &gt; Task queues
                    &gt; Back pressure
            i) Communication
                    &gt; TCP
                    &gt; UDP
                    &gt; REST
                    &gt; RPC
</code></pre>
### JUSTIFY [5 min]
<pre><code>(1) Throughput of each layer
(2) Latency caused between each layer
(3) Overall latency justification
</code></pre>

#### More Resources: 
  * <a href="https://medium.com/javarevisited/25-software-design-interview-questions-to-crack-any-programming-and-technical-interviews-4b8237942db0"> 25 Interview Questions </a>
  * <a href="http://highscalability.com/all-time-favorites">High-Scalability</a>
  * <a href="https://www.hiredintech.com/classrooms/system-design/lesson/52">Hired In Tech </a>
  * <a href="https://workat.tech/system-design/article/best-resources-for-system-design-interview-i-dbv5ok8vtjya">workat.tech</a>
  * <a href="https://github.com/checkcheckzz/system-design-interview">System Design</a>
  * <a href="https://github.com/shashank88/system_design">SYSTEM DESIGN PREPARATION</a>
  * <a href="https://github.com/donnemartin/system-design-primer">The System Design Primer</a>
  * <a href="https://www.youtube.com/watch?v=xpDnVSmNFX0&list=PLMCXHnjXnTnvo6alSjVkgxV-VH6EPyvoX&index=1"> Gaurav Sen Playlist </a>
  * <a href="https://www.youtube.com/c/TechDummiesNarendraL/playlists"> Narendra L - Tech Dummies </a>
  * <a href="https://github.com/prasadgujar/low-level-design-primer"> low-level-design-primer </a>
  * [System Design Interesting Reads](https://docs.google.com/document/d/1iKk6vJbWtI02AllnIEZTrKWQb4dT2QthJdRt05vq6Hw/edit)
  * [Real Time Analytics on Big Data Architecture](https://docs.microsoft.com/en-us/azure/architecture/solution-ideas/articles/real-time-analytics)
  * [how-i-finally-got-some-awesome-offers](https://leetcode.com/discuss/interview-experience/1172461/how-i-finally-got-some-awesome-offers)
  * [Pragmatic Programming Techniques](http://horicky.blogspot.com/2010/10/scalable-system-design-patterns.html)
  * [Multithreading](http://www.albahari.com/threading/)
  
#### Credit: 
  * <a href="https://leetcode.com/discuss/career/229177/My-System-Design-Template">https://leetcode.com/discuss/career/229177/My-System-Design-Template</a>
  * <a href="https://www.youtube.com/watch?time_continue=1&v=UzLMhqg3_Wc&feature=emb_logo">https://www.youtube.com/watch?time_continue=1&v=UzLMhqg3_Wc&feature=emb_logo</a>
