<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="System_Design_Interview_Approach_Template_0"></a>System Design Interview Approach Template</h2>
<h3 class="code-line" data-line-start=1 data-line-end=2 ><a id="FEATURE_EXPECTATIONS_5_min_1"></a>FEATURE EXPECTATIONS [5 min]</h3>
<pre><code>    (1) Use cases
    (2) Scenarios that will not be covered
    (3) Who will use
    (4) How many will use
    (5) Usage patterns
</code></pre>
<h3 class="code-line" data-line-start=7 data-line-end=8 ><a id="ESTIMATIONS_5_min_7"></a>ESTIMATIONS [5 min]</h3>
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
<h3 class="code-line" data-line-start=19 data-line-end=20 ><a id="DESIGN_GOALS_5_min_19"></a>DESIGN GOALS [5 min]</h3>
<pre><code>    (1) Latency and Throughput requirements
    (2) Consistency vs Availability  [Weak/strong/eventual =&gt; consistency | Failover/replication =&gt; availability]
</code></pre>
<h3 class="code-line" data-line-start=22 data-line-end=23 ><a id="HIGH_LEVEL_DESIGN_510_min_22"></a>HIGH LEVEL DESIGN [5-10 min]</h3>
<pre><code>    (1) APIs for Read/Write scenarios for crucial components
    (2) Database schema
    (3) Basic algorithm
    (4) High level design for Read/Write scenario
</code></pre>
<h3 class="code-line" data-line-start=27 data-line-end=28 ><a id="DEEP_DIVE_1520_min_27"></a>DEEP DIVE [15-20 min]</h3>
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
<h3 class="code-line" data-line-start=64 data-line-end=65 ><a id="JUSTIFY_5_min_64"></a>JUSTIFY [5 min]</h3>
<pre><code>(1) Throughput of each layer
(2) Latency caused between each layer
(3) Overall latency justification
</code></pre>
<p class="has-line-data" data-line-start="69" data-line-end="70">Credit: <a href="https://leetcode.com/discuss/career/229177/My-System-Design-Template">https://leetcode.com/discuss/career/229177/My-System-Design-Template</a></p>
