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

### Docker

[TO CONTINUE]

### Storage

### Horizontal scaling

### Cloud

### GPU

### Specialized but useful

#### Web UI

#### Apps

#### 3D graphics

## Computer science

## Approach to engineering

## Social skills

## Approach to work

## Workflow

## Beyond engineering

