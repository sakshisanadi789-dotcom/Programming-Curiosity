# Server

## WHY?
A server provides data or performs work for clients over a network. It lets an application centralize shared state and capabilities instead of requiring every client to implement them independently.

## WHAT?
“Server” can mean a computer, a process, or software that listens for and responds to requests. A web server may serve files or forward requests to application code; one physical computer can run many servers, and one service can span many computers.

## HOW?
A server process listens on a network address and port, accepts connections, handles requests, and sends responses. A production application may put a load balancer or reverse proxy in front of several application processes, which then use databases, caches, and storage.

## WHERE?
Servers run in homes, offices, data centers, or cloud-provider facilities. After deployment, an application usually runs on virtual machines, containers, managed runtimes, or serverless infrastructure hosted on physical machines in data centers.

## WHEN?
Use a server when clients need shared or centrally controlled functionality. The deployment model should match availability, security, latency, and operational needs rather than assuming every application needs a large distributed system.

## WHO?
Clients send requests; server software handles them; infrastructure operators maintain machines and networks; application teams deploy and monitor code. In managed cloud services, provider and customer responsibilities are shared.

## WHAT IF?
If a server process crashes, a supervisor or orchestrator can detect the exit and restart it; health checks and monitoring help detect failures that do not cause an exit. A single server is a single point of failure unless the system has redundancy and recovery plans.