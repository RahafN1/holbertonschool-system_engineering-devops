# Web infrastructure design

Whiteboard project: designing web infrastructures and explaining what each
component does, how the system is made redundant, and what its weaknesses are.

## Concepts

- Network basics
- Server
- Web server
- DNS
- Load balancer
- Monitoring
- Acronyms: LAMP, SPOF, QPS

## Requirements

- Each task is designed on a whiteboard (or paper / software), then a
  screenshot of the diagram is taken and its link is put in the answer file.
- Everything is written in English.
- The project is manually reviewed and each task is also whiteboarded in
  front of a mentor, staff or student.

## Tasks

### 0. Simple web stack

- File: `0-simple_web_stack`
- One-server infrastructure hosting `www.foobar.com` (`www` A record pointing
  to `8.8.8.8`): 1 Nginx web server, 1 application server, application files
  (code base) and 1 MySQL database.
- Explains: what a server is, the role of the domain name, the type of the
  `www` DNS record, the role of the web server, the application server and the
  database, how the server communicates with the user's computer
  (TCP/IP, HTTP/HTTPS).
- Issues: SPOF, downtime during maintenance, cannot scale with traffic.

### 1. Distributed web infrastructure

- File: `1-distributed_web_infrastructure`
- Three-server infrastructure with a load balancer (HAproxy), two servers
  running the web server, application server and code base, and a database.
- Explains: why each element is added, the load balancer distribution
  algorithm, active-active vs active-passive, and the database
  Primary-Replica cluster.

### 2. Secured and monitored web infrastructure

- File: `2-secured_and_monitored_web_infrastructure`
- Adds 3 firewalls, an SSL certificate to serve `www.foobar.com` over HTTPS,
  and 3 monitoring clients (data collectors, e.g. Sumo Logic or New Relic).
- Explains: what the firewalls are for, why HTTPS is used, what monitoring is
  used for, how the collectors gather data, and how to monitor the web server
  QPS.

### 3. Scale up

- File: `3-scale_up`
- Splits the components onto separate servers: a cluster of load balancers
  (HAproxy), a web server, an application server and a database server.
- Explains: why each element is added.

## Repository

- GitHub repository: `holbertonschool-system_engineering-devops`
- Directory: `web_infrastructure_design`

## Author

Rahaf Alabdalh
