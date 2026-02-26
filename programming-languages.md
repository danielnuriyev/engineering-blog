---
layout: page
title: "Useful Programming Languages"
permalink: /programming-languages/
---

# Useful Programming Languages

There are multiple programming languages because they were designed for different uses and because languages evolve.

I will list them by the area of use or you can skip to the conclusion in the bottom.

## Mobile Apps

Dart is a language by Google for cross platform native mobile apps. 
It is compiled and executed directly on top of an OS avoiding a bridge between the OS and the code.
Dart can also be compiled to run as JavaScript in a browser and for backend applications.

In some cases you may need functionality not implemented in Dart.
For this use Kotlin on Android and Swift on iOS. 
If you need to go lower in stack use C++ on Android and Objective C on iOS.

## Web Apps

JavaScript is the language of browser.

## Desktop Apps

- Windows: The language of choice is C# but you have more options as explained [here](https://learn.microsoft.com/en-us/windows/apps/get-started/?tabs=net-maui%2Ccpp-win32)
- MacOS: Swift
- Linux: depends on the desktop environment. Since the two mostly used ones are Xfce and GNOME, C is a safe bet. They have bindings for other languages that you may prefer depending on what you are developing.

For all Operating Systems, you may need to go lower in stack for some interactions with the OS and use Rust, C++, C or on Mac Objective C

## Backend

Developing a robust backend requires fault tolerance, high concurrency, speed of start-up and execution, memory efficiency and management.

The ideal candidate is BEAM with Erlang/Elixir/Gleam.

But practically the ideal platform is not always needed and some of the listed requirements can be addressed by the environment (lambdas, k8s, loadbalancing, pre-warming, faster hardware with more memory etc.)

As long as you are smart about the choices, testing, contingency plans etc., you should be fine.

## Data

Python is the default.

## Scripting

Scripting requires simple code. Usually performance is not required. Python is the best.

For Shell scripting I prefer zsh as it has more features.

## OS and Hardware

C, C++ (Objective C on Apple devices) are used for hardware, kernels and code running in kernel space.

Rust is being used more instead of C++.

Zig is starting to be used instead of C.

## How to pick a language

Important to pick a language that is suitable for a given task but also think about scaling out the performance, environments, size of code, size of the team.
Keep an eye on languages, their features, implementations, usage but keep in mind that using multiple languages is an extra effort.
Using rare languages may be a challenge for other engineers who will work with you, after you, for expanding a project, for making a project open source or even for selling it.

## Which languages cover most use cases

With JavaScipt, Python and Rust you can cover most common areas of coding.

So I would master these 3 as reference and go-to but then still pick the best language for a project.

Have fun!

