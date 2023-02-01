# Useful Programming Languages

There are multiple programming languages because they were designed for different uses and because languages evolve: better languages replace older languages.

I will list by the area of use

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

## Backend APIs

Backend APIs can be developed in all languages listed above but they have inherent flaws:
- Dart is the best choice for cross platform mobile apps but the language runs within JavaScript constraints, so why not just use JavaScript
- JavaScipt is a good choice. A single nodejs process can handle multiple concurrent requests by placing them on a queue. The queue is handled by a single OS thread. This works well if you have access to multiple 1-2 core machines, otherwise it's worth spawning 1 nodejs process per core + you can keep one core free. The flaw of JavaScript/NodeJs is that if for whatever reason a single request takes much of CPU (non-IO) time, the whole queue will wait. To be on the safe side it is better to use languages that utilize multiple cores and identify stuck functions, like Go does. More about this later. Another flaw is that a nodejs process is limited to 1.5GB of memory. If you need more, JavaScript is not for you.
- Kotlin runs on JVM whose flaws are: impossible to kill a stuck Thread, the amount of memory it uses is orders of magnitude greater than the actual data. But it does utilize multiple cores, so in this respect it is better than NodeJS.
- Swift is designed of Apple OSes. Most probably your backend API will be on a Linux. There is a way to run Swift on Linux but why.
- C++ and C are too low level. You will have to code things that JavaScript, Kotlin and other engineers are not even aware of.
- .NET languages is a story similar to Swift.

Now let's pick a good language for backend APIs.

Ideally, tt should:
- handle spikes
- utilize multiple cores
- handle stuck code
- use little memory, not get stuck on garbage collection, not be limited in memory size
- be fast
- have extensibility, like OO
- be simple, brief with mechanisms preventic production surprises, for example, typed

There are more features but these are the ones that differentiate backend API languages.

Above I did not filter out JavaScript and Kotlin but they have flaws. Let's a look at more languages.

TBC

## Backend Workers

## OS and Hardware

## Which languages cover most use cases

## Best order for learning programming languages

