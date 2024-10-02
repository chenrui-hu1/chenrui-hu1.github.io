---
title: "Penn-Chord Distributed Hash Table"
date: 2023-12-15
excerpt: "Built peer-to-peer distributed hash table (DHT) based on the Chord protocol in a team of three. <br/><img src='/images/portforlio/penn-chord/diagram.png' width='60%'>"
location: "University of Pennsylvania"
collection: portfolio
---

_This is a course project for CIS553 Computer Network(Fall 2023) at University of Pennsylvania._

Our team built a peer-to-peer Penn Chord Distributed Hash Table with self-built routing protocol at Network Layer, supporting the key-value pair storage.

Here is the [Github Repo](https://github.com/AkoZhu/penn-search).

The diagram is as follows:
<p align="center">
  <img src="/images/portforlio/penn-chord/diagram.png">
</p>

# Components

## Routing Protocol
Our team implemented the traditional **Distance Vector** and **Link State** routing protocol at network layer to facilitate efficient nodes communication, with the help of Bellman-Ford algorithm and Dijkstra algorithm. This implementation leverages C++ and **NS-3** network simulator to model and test the system's performance.
- **Distance Vector**: Utilized the Bellman-Ford algorithm, which is more suitable for large scale distributed and peer-to-peer environment. More privacy. 
- **Link State**: Utilized the Dijkstra algorithm, which is more efficient in small-to-middle scale distributed and more centrialized environment. More efficient but less privacy.

## Penn Search
Based on the Routing protocol in Network Layer, our team built a Chord-based search system that integrates consistent hashing and data replication mechanisms. 
- **Efficient lookup and storage**: Utilized the chord-based protocol and finger table to reduce time complexity from $$O(N)$$ to $$O(logN)$$ in large scale fully distributed environment. 
- **Dynamic membership**: Leveraged the data transfer mechanism to handle the dynamic addition and removal of nodes, maintaining the balanced and resilient distributed hash table(DHT).
