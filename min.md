# Minimum requirements for being a good software engineer

This is intended for an engineer before a first professional job.
I am writing this because I find junior engineers lacking basic knowledge and skills
and this lack projects years into their careers leading to career slowdown.

## Knowledge

A good engineer should know how things work inside. 
If you write code and do not know how it is compiled and executed, 
you will not be able to design efficient products. 
To rely on the designers of languages, libraries, containers and operating systems, clouds to do the best job, 
you must know how these products are designed and structured in order to choose a correct produst and use it efficiently.
For example, every language has concurrency but their design goals and correspondingly implementations are so different. We'll get to this below.

I prefer to learn from bottom up and therefore I'll start with hardware.

Keep in mind that in order to know something, you have to do it. 
Therefore most sections describe not only what you should know but also what you should try.

### Hardware

At the end of the day, whatever you write runs on hardware and if you want to be methodical in learning engineering, start with hardware.

Take a simple controller, such as Arduino, with 1 sensor and 1 output device and write a loop that does something simple.

No need to dive deeper unless you want to go into firmware engineering 
which actually is a great field due to the rapid development of robotics, automation, AI

### C

Learn C which is the foundation for today's mostly used languages. If you take Arduino route described above, you'll learn basic C.

### Languages

Learn what types of computer languages there are. What considerations go into the design of languages.

### Compilation

There are several approaches to parsing and compiling programming languages. 
Learn about them.
Design a simple language that has int, float, conditions, loops and functions.
Then implement it. There are online articles that explain how to build your own lexer, parser, interpreter or compiler both from scratch and using existing products.
Building anything from scratch in C is better for understanding how things work.

### Linux

Learn how Linux manages
- multiple processes and threads. Process and thread priority. Core affinity. How Linux handles a process & thread when it's doing IO. What hyperthreading is.
- memory
- IO (devices and data)
- file systems

Learn basic shell commands that show information about and manage processors, memory, file systems and files, network, devices, processes and threads.

Extra points for looking at the source of these shell commands, and of Linux core.

### Concurrency

Learn:
- how Linux manages processes and threads as described above in Linux section.
- how to use processes & threads in Rust or in Java, or in any language that uses real OS threads (not Dart, JS, Python, Go, Erlang)
- how processes exchange data
- how to decide when to use processes and when threads (hint: % of IO, size of exchanged data)
- concept of threads pools and why they are needed (hint: % of IO + number of cores)
- difference between parallelism and concurrency
- how concurrency is implemented in JS and Python. Important: not how to use it but 
  - what happens to your Python code when you run it in multiple threads (hint: GIL and why this design was chosen originally)
  - what happens to your JS code when you create a callback (hint: event loop and why this design was chosen by creators of V8)
- concept of "green threads" and how concurrnecy is implemented in Go. Important: not how to use goroutines but how Go executes them, queues them, switches among them.

Exercise: calculate the total size of all files on a disk without recursion (hint: use a queue) and using concurrency in JS, Python, Rust/Java and Go/Erlang (they implement concurrency differently). In each of the 4 languages: what was faster: threads or processes and why.

### Networking

Learn IP4 and TCP protocols. There are many more commonly used protocols but these 2 are the base for reliable exchange of data over the internet.

Exercise: write a packet sniffer in C

### Security

Learn TLS. Security goes beyond encrypting traffic but learning about TLS covers multiple topics in security and serves as a good base.

Exercise: implement an HTTPS client in C

In addition, read about [cryptographic hashing](https://en.wikipedia.org/wiki/Cryptographic_hash_function). It is commonly used and not only for protecting data.

### Docker

Docker is used to create an environment for coding and running stuff. For example, on your Mac or Windows machine you can code something in a Linux environment and then deploy it onto a "cloud" (AWS, Azure, GCP, Oracle etc.). This creates consistency among engineers and environments (development, testing, staging, production). Nowadays it's a must.

### Storage

Learn about the most commonly used Linux filesystems: their design, their purpose, when to use which.

Learn about the types databases: 
- relational (MariaDB) 
- key/value (Memcached) 
- document (MongoDB) 
- data structures (Redis) 
- columnar (Cassandra) 
- query engines (PrestoDB) 
- graph (Neo4J)
- search (ElasticSearch)

Answer these questions for each:
- how they store and retrieve
- how they scale with 
  - concurrent inserts, updates, deletes, retrievals and why
  - size of data for inserts, updates, deletes, retrievals and why

It is good to get a hands-on experience with each of them: install, insert data, retrieve data;

It is good to do the same for their cloud-based serverless analogs. AWS is the most widely used cloud.

[Global DB ranking](https://db-engines.com/en/ranking). You can also rank them by type. They classify Radis and PrestoDB differently than I do, so follow my list.

At your current and next job you will not use all these database types but knowing the types and their strong/weak sides is good to be able to choose the best when you need.

### Horizontal scaling

Learn the difference between vertical and horizontal scaling.

Vertical scaling is done by 
- hardware that better addresses the performance bottlenecks
- choice of software and its configuration
- code optimimizations if you are writing it

Learn how the database technologies listed above implement horizontal scaling, how they decide on which node to store which part of data etc. They are quite different. Even through we code on Clouds, knowing how clouds scale is useful because you may work on one of them, not all technologies are on your cloud, it is useful to know how your technology of choice scales for your efficient use of it.

### Cloud

Create an AWS account and do everything above on AWS as if your local computer is just a terminal.

AWS because it is the default. If you need to work on another cloud, it will be similar.

### Kubernetes

Now when we are on AWS, learn Kubernetes: what it is, why it was created, its components, how to run it locally. Create a basic echo server and deploy it locally into 2 pods with a load balancer and try to use it.

Learn Helm Charts for K8s and do the same ^ using Helm.

Then deploy it onto AWS EKS.

### GPU

[GPU](https://en.wikipedia.org/wiki/Graphics_processing_unit) is a part of most phones and laptops. It is good to know how GPU architecture is different from CPU. Due to GPU availability and GPU's ability to process [matrices]([https://en.wikipedia.org/wiki/Matrix_(mathematics)](https://www.mathsisfun.com/algebra/matrix-introduction.html)), whether to use GPU for parts of code should be a consideration in your software design.

Before learning about GPU, it is useful to learn about [matrices]([https://en.wikipedia.org/wiki/Matrix_(mathematics)](https://www.mathsisfun.com/algebra/matrix-introduction.html)) and [vectors]([https://en.wikipedia.org/wiki/Vector_calculus](https://www.mathsisfun.com/algebra/vectors.html)). 

Also read about [General-Purpose computing on Graphics Processing Units](https://en.wikipedia.org/wiki/General-purpose_computing_on_graphics_processing_units), [OpenCL](https://en.wikipedia.org/wiki/OpenCL) and take a look at [this Python example](https://web.archive.org/web/20170907175053/http://enja.org:80/2011/02/22/adventures-in-pyopencl-part-1-getting-started-with-python)

### Extra

#### Web UI

You need to know how to build a Web UI in a few cases:
- this is your specialization
- your current/next role requires this skill, often as a part of a "full stack" role

Otherwise, knowing how to build a Web UI is frequently needed to visualize what you work on, especially if the data is dynamic.

Nowadays most Web Applications are built using frameworks such as [ReactJS](https://reactjs.org) but I am not sure that one can build anything using a framework without knowing the following building blocks:
- [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript), including [NodeJS](https://nodejs.org/en/)
- [WebSocket](https://github.com/websockets/ws), also [this](https://socket.io/) and [this](https://www.npmjs.com/package/react-use-websocket)

## Statistics

Statistics helps us analyze data. For example, data coming from logs. That's why it is useful to know basic statistics definitions and tools.

**Terms**:

- [histogram](https://en.wikipedia.org/wiki/Histogram)
- [types of mean/average](https://towardsdatascience.com/on-average-youre-using-the-wrong-average-geometric-harmonic-means-in-data-analysis-2a703e21ea0)
- [standard definition](https://www.mathsisfun.com/data/standard-deviation.html)
- [normal distribution](https://en.wikipedia.org/wiki/Normal_distribution)
- [covariance](https://www.mathsisfun.com/data/covariance.html)
- [r-squared](https://www.investopedia.com/terms/r/r-squared.asp)
- [correlation](https://machinelearningmastery.com/how-to-use-correlation-to-understand-the-relationship-between-variables/)
- [enthropy](https://www.analyticsvidhya.com/blog/2020/11/entropy-a-key-concept-for-all-data-science-beginners/)
- normality test

**Tools**

The commonly used languages should have these statistical functions ether as a part of the standard library or as an open source library.

These languages are commonly used by data engineers, analysts, scientists and mathematicians:
- Python. To work with tabular data use Pandas/Dask. Also, they have statistical functions. If you need more statistics, use statsmodels.
- R
- Julia

## Computer science

+TPU/NPU
+Jupyter

## Approach to engineering

## Social skills

## Approach to work

## Workflow

## Beyond engineering

