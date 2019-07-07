Final: Question 6
=================

**Problem:**

Suppose a client application is sending writes to a replica set with three nodes, but the primary node stops responding:

![](https://s3.amazonaws.com/edu-static.mongodb.com/lessons/M220/notebook_assets/replica_set_primary_down.png?raw=true "")

Assume that none of the connection settings have been changed and that the client is only sending insert statements with write concern **w: 1** to the server.

<details>
  <summary>After 30 seconds, the client still cannot connect to a new primary. Which of the following errors will be thrown by the Node.js driver, and how should it be handled?</summary>
   Answer: (X) a Timeout error, resolved by wrapping the call in a try/catch block
</details>
