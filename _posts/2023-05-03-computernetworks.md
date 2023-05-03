---
toc: true
comments: true
layout: post
title: Computers and Networks (Unit 4)
description: Add Definitions from Unit 4 Computer Systems and Networks
categories: []
---

## Requirements
> Work through College Board Unit 4... blog, add definitions, and pictures.  Be creative, for instance make a story of Computing and Networks that is related to your PBL experiences this year.


### How a Computer Works
> As we have learned, a computer needs aa program to do something smart.  The sequence of a program initiates a series of actions with the computers Central Processing Unit (CPU). This component is essentially a binary machine focussing on program instructions provided.  The CPU retrieives and stores the data it acts upon in Random Access Memory (RAM). Between the CPU, RAM, and Storage Devices a computer can work with many programs and large amounts of data.

List specification of your Computer, or Computers if working as Pair/Trio
- Processor GHz: **2.60**
- Memory in GB: **26.4**
- Storage in GB: **500**
- OS: **Microsoft Windows 11 Home**

Define or describe usage of Computer using Computer Programs. Pictures are preferred over a lot of text.  Use your experience.
- Input devices - **hardware components used to enter data and commands into a computer or other electronic device.**
- Output devices - **hardware components used to display or present data, information, or results produced by a computer or other electronic device.**
- Program File - **computer files containing instructions and code that are executed by a computer to perform specific tasks or functions.**
- Program Code - **set of instructions written in a programming language that are used to create computer programs and software.**
- Processes - **refers to a program or task that is being executed by a computer's operating system, which includes the instructions, data, and resources needed to complete the task.**
- Ports - **a communication endpoint used to identify a specific process or application running on a computer or network and enable data exchange between different devices or software applications.**
- Data File - **a computer file that contains information or data, such as text, images, audio, or video, which can be accessed and manipulated by software applications.**
- Inspect Running Code - **involves examining the live state and behavior of a running program or application in real-time to debug errors, optimize performance, or gather information about its execution.**
- Inspect Variables - **can be used to programmatically access and retrieve information about variables, functions, classes, and other objects during runtime.**


![]({{site.baseurl}}/images/mcq2020.PNG "Pic")


### The Internet
> Watch/review College Board Daily Video for 4.1.1

- Essential Knowledge
    - A computing device is a physical artifact that can run a program. Some examples include computers, tablets, servers, routers, and smart sensors.
    - A computing system is a group of computing devices and programs working together for a common purpose.
    - A computer network is a group of interconnected computing devices capable of sending or receiving data.
    - A computer network is a type of computing system. 
    - A path between two computing devices on a computer network (a sender and a receiver) is a sequence of directly connected computing devices that begins at the sender and ends at the receiver.
    - Routing is the process of finding a path from sender to receiver.
    - The bandwidth of a computer network is the maximum amount of data that can be sent in a fixed amount of time.
    - Bandwidth is usually measured in bits per second

- Complete Vocabulary Matching Activity.  Incorporate this into your learnings from year.  To analyze measure path and latency use `traceroute` and `ping` commands from Linux Terminal.  
    - Path 
    - Route
    - Computer System
    - Computer Device
    - Bandwidth
    - Computer Network

> Watch/review College Board Daily Video 4.1.2

- Complete True of False Questions

**TRUE: Open standards and protocols enable different manufacturers and developers to build hardware and software that can communicate with hardware and software on the rest of the internet.**

**FALSE: IETF is a task force used to enforce laws to keep manufacturers out of the internet.**

**FALSE: Routes are determined in advance and are not flexible.**

**TRUE: A protocol is an agreed-upon set of rules that specify the behavior of a system.**

**FALSE: UDP guarantees transfers and is faster.**

**FALSE: The World Wide Web is the internet.**

**TRUE: HTTP is a protocol used by the World Wide Web.**

- Essential Knowledge
    - The internet is a computer network consisting of interconnected networks that use standardized, open (nonproprierary) communication protocols.
    - Access to the internet depends on the ability to connect a computing device to an internet connected device.
    - A protocol is an agreed-upon set of rules that specify the behavior of a system.
    - The protocols used in the internet are open, which allows users to easily connect additional computing devices to the internet.
    - Routing on the internet is usually dynamic; it is not specified in advance
    - The scalability of a system is the capacity for the system to change in size and scale to meet new demands.
    - The internet was designed to be scalable
    - Information is passed through the internet as a data stream. Data streams contain chunks of data, which are encapsulated in packets. 
    - Packets contain a chunk of data and metadata used for routing the packet between the origin and the destination on the internet, as well as for data reassembly.
    - Packets may arrive at the destination in order, out of order, or not at all
    - IP, TCP and UDP are common protocols used on the internet.
    - The world wide web is a system of linked pages, programs, and files.
    - HTTP is a protocol used by the world wide web
    - The world wide web uses the internet

- Go over AP videos, vocabulary, and essential knowledge.  Draw a diagram showing the internet and its many levels. A preferred diagram would using your knowledge of frontend, backend, deployment, etc.  Picture would highligh vocabulary by illustration. The below illustration have some ideas

![]({{site.baseurl}}/images/Drawing2.PNG "Pic 2")


- Often we draw pictures of machines communicating over the Internet with arrows.  However, the real communication goes through protocol layers and the machine and then is trasported of the network.   For College Board and future Computer Knowledge you should become familiar with the following ...

```
     User Machine  <---> Frontend Server <---> Backend Server
    +-----------+         +-----------+         +-----------+
    |  Browser  |         |  GH Page  |         |   Flask   |
    +-----------+    ^    +-----------+    ^    +-----------+
    |    HTTP   |    |    |    HTTP   |    |    |    HTTP   |
    +-----------+    |    +-----------+    |    +-----------+
    |    TCP    |    |    |    TCP    |    |    |    TCP    |   
    +-----------+    |    +-----------+    |    +-----------+
    |     IP    |    V    |     IP    |    V    |     IP    |
    +-----------+         +-----------+         +-----------+
    |  Network  |  <--->  |  Network  |  <--->  |  Network  |
    +-----------+         +-----------+         +-----------+
```

The "http" layer is an application layer protocol in the TCP/IP stack, used for ***communication between web browsers and web servers***. It is the protocol used for transmitting data over the World Wide Web.

The "transport" layer (TCP) is responsible for providing reliable data transfer between applications running on different hosts.  The TCP protocol segments the data into smaller ***chunks called "segments"***. Each segment contains a sequence number that identifies its position in the original stream of data, as well as other control information such as source and destination port numbers, and checksums for error detection.

The "ip" layer is responsible for packetizing data received from the TCP layer of the protocol stack, and then ***encapsulating the data into IP packets***. The IP packets are then sent to the lower layers of the protocol stack for transmission over the network.

The "network" layer is responsible for ***routing data packets between networks*** using the Internet Protocol (IP). This layer handles tasks such as packet addressing and routing, fragmentation and reassembly, and ***network congestion*** control.


### Fault Tolerance
> Watch both Daily videos for 4.2

- Complete the network activity, summarize your understanding of fault tolerance.

**The network operation was a very good practical method to analyze the networks of  certain  tens of lines and check their malfunction. Basically, fault tolerance means that in a network of many different sources and destinations, if one route goes down, there is still redundancy and the network can go from the  source to the destination. There is not only one path from A to B, so if that one path goes down,  A can take several paths to eventually reach B.**


### Parallel and Distributed Computing
> Review previous lecture on Parallel Computing and watch Daily vidoe 4.3.  Think of ways to make something in you team project to utilize Cores more effectively.  Here are some thoughts to add to your story of Computers and Networks...

- What is naturally Distributed in Frontend/Backend archeticture?

**In a frontend/backend architecture, the user interface is naturally distributed to the frontend layer while the data storage is handled by the backend layer. The frontend layer is responsible for presenting the user interface and handling user interactions, while the backend layer is responsible for storing and managing data. This division of responsibilities allows for more efficient development and easier maintenance of the overall system.**

- Analyze this command in Docker: ```ENV GUNICORN_CMD_ARGS="--workers=1 --bind=0.0.0.0:8086"```.   Determine if there is options are options in this command for parallel computing within the server that runs python/gunicorn.  Here is an [article](https://medium.com/building-the-system/gunicorn-3-means-of-concurrency-efbb547674b7)


**The command ENV GUNICORN_CMD_ARGS="--workers=1 --bind=0.0.0.0:8086" sets an environment variable named GUNICORN_CMD_ARGS with two options. The --workers=1 option specifies that only one worker process should be used, which means that parallel computing within the server is not being utilized. The --bind=0.0.0.0:8086 option specifies the IP address and port that Gunicorn should bind to.**


> Last week we discussed parallel computing on local machine.  There are many options.  Here is something to get parallel computing work with a tool called Ray.
- Review this [article](https://www.anyscale.com/blog/writing-your-first-distributed-python-application-with-ray)...  Can you get parallel code on images to work more effectively?  I have not tried Ray.

- Code example from ChatGPT using squares.  This might be more interesting if nums we generated to be a lot bigger.

```python
import ray

# define a simple function that takes a number and returns its square
def square(x):
    return x * x

# initialize Ray
ray.init()

# create a remote function that squares a list of numbers in parallel
@ray.remote
def square_list(nums):
    return [square(num) for num in nums]

# define a list of numbers to square
nums = [1, 2, 3, 4, 5]

# split the list into two parts
split_idx = len(nums) // 2
part1, part2 = nums[:split_idx], nums[split_idx:]

# call the remote function in parallel on the two parts
part1_result = square_list.remote(part1)
part2_result = square_list.remote(part2)

# get the results and combine them
result = ray.get(part1_result) + ray.get(part2_result)

# print the result
print(result)

```
