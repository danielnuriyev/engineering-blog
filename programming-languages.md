# Useful Programming Languages

There are multiple programming languages because they were designed for different uses and because languages evolve: better languages replace older languages.

I will list by the area of use.

## Mobile Apps

Dart is a language by Google for cross platform native mobile apps. 
It is compiled and executed directly on top of an OS avoiding a bridge between the OS and the code.
Dart can also be compiled to run as JavaScript in a browser and for backend applications.

In some cases you may need functionality not implemented in Dart.
For this use Kotlin on Android and Swift on iOS. 
If you need to go lower in stack use C++ on Android and Objective C on iOS.

## Web Apps

JavaScript is the language of a browser.

## Desktop Apps

- Windows: The language of choice in C# but you have more options as explained [here](https://learn.microsoft.com/en-us/windows/apps/get-started/?tabs=net-maui%2Ccpp-win32)
- MacOS: Swift
- Linux: depends on the desktop environment. Since the two mostly used ones are Xfce and GNOME, C is a safe bet. They have bindings for C++ which I recommend because small and simple projects sometimes grow in complexity and this is one of the reasons why C++ was invented. There are bindings for Python and JavaScript but once you learn how to code for Xfce and GNOME in C, you'll be able to do anything which is not necessarily the case for other languages.

For all Operating Systems, you may need to lower in stack and use C++ or even C.

## Backend

Backend APIs and workers can be developed in all languages listed above but they have inherent flaws:
- Dart is the best choice for cross platform mobile apps but the language runs within JavaScript constraints, so why not just use JavaScript
- JavaScipt is a good choice. A single nodejs process can handle multiple concurrent requests by placing them on a queue. The queue is handled by a single OS thread. This works well if you have access to multiple 1-2 core machines, otherwise it's worth spawning 1 nodejs process per core + you can keep one core free. The flaw of JavaScript/NodeJs is that if for whatever reason a single request takes much of CPU (non-IO) time, the whole queue will wait. To be on the safe side it is better to use languages that utilize multiple cores and identify stuck functions, like Go does. More about this later. Another flaw is that a nodejs process is limited to 1.5GB of memory. If you need more, JavaScript is not for you.
- Kotlin runs on JVM whose flaws are: impossible to kill a stuck Thread, the amount of memory it uses is orders of magnitude greater than the actual data. But it does utilize multiple cores, so in this respect it is better than NodeJS.
- Swift is designed of Apple OSes. Most probably your backend API will be on a Linux. There is a way to run Swift on Linux but why.
- C++ and C are too low level. You will have to code things that JavaScript, Kotlin and other engineers are not even aware of.
- .NET languages is a story similar to Swift.

Now let's pick a good language for the backend.

Ideally, tt should:
- handle spikes
- utilize multiple cores
- handle stuck code
- use little memory, not get stuck on garbage collection, not be limited in memory size
- be fast
- have extensibility, like OO
- be simple, with mechanisms that prevent production surprises, for example, typed
- cross platform

There are more features but these are the ones that differentiate backend languages.

Above I did not filter out JavaScript and Kotlin but they have flaws. Let's a look at more languages.

The only language that matches these requirements is Go but although it has interfaces and a way to extend them, practically, after having used OO languages mentioned above, I found it clumsy to implement an extensible design. 

Next candidates are Julia and Rust. Their only flaw is that like JavaScript and Kotlin they do not handle a stuck thread but 
- compared to JavaScript, they are not limited in memory
- compared to Kotlin, they do not use too much memory

So what do we have:
- JavaScript is good for microservices where each event queue can use up to 1.5GB of memory. Beware of unexpected CPU (non-IO) bottlenecks.
- Go for massively concurrent code but low complexity.
- Julia is generally good but not as popular, and you may need to programmatically prevent hang-ups using `yield`
- Rust is generally good, not so popular but more popular for backend than Julia, and unlike Julia it was designed for the backend, but you may need to programmatically prevent hang-ups using `yield`
- Kotlin is generally good but you need to keep an eye on the memory and programmatically prevent hang-ups using `yield`.
- Python
  - if you want to code quickly
  - do not need concurrency inside a single process, for example, when you use AWS Lambda
  - code that uses CPU does not need to be blazingly fast

I think that generally best option is Rust. But look at the specific considerations of your project. Don't be a "I am a JavaScript programmer" type of person.

## Data

Python is the default. If you need concurrency and speed, consider Julia.

## OS and Hardware

To interact directly with an OS or with hardware, a language of your choice needs to support this functionality. 
Otherwise you will have to use C++. On Apple OSes it is Objective C.

In some cases you will need C and Assembley, depending on an existing code and tools of an OS or hardware.

## How to pick a language

Important to pick a language that is suitable for a given task but also think about scaling out the performance, environments, size of code, size of the team.
Keep an eye on languages, their features, implementations, usage but keep in mind that using multiple languages is an extra effort.
Using rare languages may be a challenge for other engineers who will work with you, after you, for expanding a project, for making a project open source or even for selling it.

## Which languages cover most use cases

With JavaScipt, Python and C++ you can have a Web UI that can be accessed from mobile and desktop with a backend 
+ you can work on data + you can do desktop/OS/hardware level stuff (you might still need to dive into Objective C, C, Assembley)

So I would master these 3 as reference and go-to but then still pick the best language for a project.

Have fun!

