---
layout: term
title:  "Message Queues (MQ)"
tags: [Application, Development]
comments: true
---

A message queue is a type of application that deals with `publishing` messages to a `queue` which will later be `consumed`. Message queues help where lots of different applications or systems want to communicate to one another, but without knowing specifically where the message will end up. This is a typical problem in large distributed `service` based systems, where lots of `services` or applications run independantly but feed into one another. It is also a very useful tool when communication between `services` isn't neccesarily done in real time, and where requests for processing need to be managed into a queue.

## Premise

A message queue will act as a service that other applications can connect to, it will usually sit on a server within a network. Applications that connect to the message queue can usually do one of two things.

1. `publish` a message. This is effectively sending a message to a given queue. The `service` that `publishes` the message can then continue doing its task.
2. `consume` a message. This is where a `service` would request a number of messages from a given queue. The `service` that `consumes` would do some operation or computation with the message and mark the message as dealt with or `acknowledged`


For example if we look at an application like Youtube they have lots of independant `services` that are responsible for performing different tasks. There would be one service that can take a video and analyse it for copyrighted material. And another service that operates the website and allows a user to upload a video and tag it. The web service that the user connects to would `publish` a message to a queue named _'awaiting_analysis'_ that the analysing service will then `consume` and deal with. This underlines one of the primary use cases for message queues, which is where services have no understanding of the time required for the next service to perform it's task and the requesting service would rather not wait for a response. For Youtube the web application would have no idea how long the analyser service will take - which would be down to the length of the video, how much capacity the analysing service is currently using etc. And the web application wouldn't need to immedietely tell the user that the analysis has been done, just that it was 'pending'.

## Practical applications

Message queues are in use mostly in systems where the capacity of interdependant services is not mutually exclusive or linear. Again the service that requests the thing just wants to know that it will be done, not when, and the service that deals with the thing does not want to have to find the requesting service to inform it of its progress. The majority of applications that rely on message queues deal with any sort of processing that is requested as the result of something unmangeable - like a user. If a service knows it can deal with a users request instantaneously then message queues are not required.