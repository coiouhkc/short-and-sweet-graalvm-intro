---
marp: true
title: Short and sweet intro to GraalVM
theme: uncover
paginate: true
_paginate: false
header: "**Alexei Bratuhin** Short and Sweet intro to GraalVM"



---

# Short and sweet

## GraalVM

---

# Intro, reason & background

We don't need no full JVM to run "Hello World!"

(or a microservice)

---

# Definition

GraalVM is a high-performance JDK for Java and other JVM languages while also providing runtimes for JavaScript, Python, and a number of other popular languages which can run Java applications on the HotSpot JVM with Graal just-in-time (JIT) compiler or as an ahead-of-time (AOT) compiled native executable. 


see https://www.graalvm.org/latest/docs/introduction/

---

# Demo: preparation & setup

<!--

sdk install java 22.3.r19-grl

java -version

gu install native-image

-->

---

# Demo: native executable

HelloWorld.java

see https://www.graalvm.org/latest/reference-manual/native-image/

<!--

javac HelloWorld.java

javap -v HelloWorld.class

native-image HelloWorld

file HelloWorld.class

file helloworld

./helloworld

-->

---

# Demo: native executable (reflection)

ReflectionExample.java

see https://www.graalvm.org/latest/reference-manual/native-image/guides/configure-with-tracing-agent/

<!--

javac ReflectionExample.java

java ReflectionExample StringReverser reverse "hello"

java ReflectionExample StringCapitalizer capitalize "hello"

native-image --no-fallback --gc=epsilon ReflectionExample

mkdir -p META-INF/native-image

java -agentlib:native-image-agent=config-output-dir=META-INF/native-image ReflectionExample StringReverser reverse "hello"

cat META-INF/native-image/reflect-config.json

native-image ReflectionExample

./reflectionexample StringReverser reverse "hello"
-->

---

# Demo: microservices

see https://github.com/coiouhkc/short-and-sweet-quarkus-intro
see https://quarkus.io/guides/building-native-image

---

# Demo: microservices (reflection)

## ~~(Don't)~~ Do it at home!

--- 

# Q&A

---

# Links

* https://www.graalvm.org/
* https://www.graalvm.org/latest/docs/introduction/
* https://www.graalvm.org/latest/docs/getting-started/
* https://github.com/graalvm/graalvm-demos
* https://github.com/shelajev/workshop
* https://www.graalvm.org/22.1/reference-manual/native-image/MemoryManagement/
* https://en.wikipedia.org/wiki/GraalVM
* https://openjdk.org/jeps/295