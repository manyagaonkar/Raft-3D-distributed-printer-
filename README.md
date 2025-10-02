This project demonstrates a distributed 3D printing job management system built using the Raft consensus algorithm. The system simulates multiple nodes, where one acts as the leader to manage printers and print jobs. It ensures leader election, fault tolerance, and replication of state across all nodes.

Tech Stack

Language: Go (Golang)

Frameworks/Libraries: Raft implementation in Go, HTTP APIs (net/http)

Tools: cURL for API testing, Linux terminals for multi-node simulation

Concepts: Distributed Systems, Consensus Protocols, Leader Election, Replication

 Features

1. Leader Election: Automatically elects a new leader when the current leader node fails.

2. Fault Tolerance: Ensures continuity of operations even during node crashes.

3. Printer Management API: Add and manage 3D printers via REST API.

4. Job Management API: Submit and track print jobs through the leader node.

5. Replication Across Nodes: Printer and job data is consistently replicated across all nodes.

 How It Works

Multiple nodes (node1, node2, node3) are started using Go.

One node is elected as the leader.

API requests (e.g., adding printers, adding jobs) are sent to the leader node.

The state is replicated across all follower nodes.

If the leader fails, Raft ensures a new leader is elected automatically.

 Demo Example

Initially, Node 1 is the leader.

After terminating Node 1, Node 2 is re-elected as the new leader.

Verified via /status endpoints and replicated data consistency checks.
