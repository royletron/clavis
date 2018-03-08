---
layout: term
title:  "Database"
alternatives: [Datastore]
tags: [Application]
comments: true
---

A _database_ is a type of application that provides connecting `clients` with the ability to read and modify data through an appropriate interface. In many cases a database would follow a standard `querying language` which provides the language required for the `client` to perform whatever operation, or `query`, it wants on the database. Databases are great at storing user or run time data that is needed to be held for a long time.

## Basic premise

The basic usage of a database is that there is a running application that operates as the `server` which any number of `clients` can connect to and start `querying` the data.

## Relationships

Keeping data about things quickly escalates in terms of complexity as the data becomes more rich and the way that you want to search and manage that data becomes more detailed. Imagine a simple website that users can log in to and buy items from a catalogue. Already in that sentence we have mentioned 'users', 'catalogue items' and 'orders' - and each of these things needs storing with the right links to each thing. By a link I mean the 'user' needs to be linked to their 'orders' and the 'orders' need to be linked to the 'items' that they have contained inside it. 