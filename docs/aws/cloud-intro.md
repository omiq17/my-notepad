---
layout: default
title: Cloud Introduction
parent: AWS
nav_order: 1
---

## Evalution of Cloud

### 1. Virtual Machine

- Not a physical machine, exist inside a physical machine.
- Lease resources from the mother computer - virtualization.
- Communicate with mother computer for any task.
- Still exists, mostly used by Data Centers.

### 2. Internet & client-server model

- It was difficult to communicate/transfer data between two computers.
- Tim Berners-Lee invented WWW in 1989.
- HTTP Procol invented.
- Server-Client models gets popular. Server processes the request and Client sends the request.
- Internet and Website idea boomed. Born Amazon, Salesforce.

### 3. SAAS (Salesforce)

- Previously user bought CD/DVD from shop, install the software in their own PC and use it.
- Why don't we just make that software in Server, provide to user through interner? Publisher maaintain the software in server, fix bugs and upgrade version very easily by this.
- Salesforce, in 1999 first launced a web-based CRM.

### 4. IAAS (AWS)

- In special events, the website had huge traffics from users. But after the events the traffic gets low, the hardware and resources remains unused most of the time.
- Amazon got the idea to rent their unused hardware/infrastucuture to users.
- They introduced EC2 (Elastic Computer Cloud) where coustomer can create their own VM by HTTP request.
- At special events, I can rent more same configured VM/resource. Then can release when I don't need. Costing will be as per usage.
- Intoduced S3 for storage.

## Cloud Computing

### What is it?

    - Cloud computing is a On-Demand availibility of computer system resources.
    - Cloud is a combination of resource allocation software and hadrware by which an end user can create his own server.

### Cloud Computing Model

    - Private Cloud: Big companies use for their own employee and resources. They want to maintain their information secured.
    - Public Cloud: Comapnies that open up thier (unused) hardwares to end users.
    - Hybrid Cloud: Mix.

### Advantages

    - I can setup my servers in many continents so that the latency time can be very less.
    - Maintaining own data center/CPU is cumbersome hard nowadays.
    - I can pay only what I have used in Cloud.

## Cloud Computing Technologies

### 1. Computing

    1. Virtual Machines
    	- Owe hardwares from mother computer.
    2. Container
    	- No need to setup a new OS. The mother computer can create multiple blocks (by using Docker etc) within itself. Known as Containarization.
    3. Serverless Computing
    	- No need OS or container. Just deliver the code. It will run by the provider.

### 2. Storage

    1. Object Storage
    	- Store data as object. We have metadata to get details about the object. Based on the details we play, open, read the data. Like audio, video, document, email etc.
    	- Infinately scalable, no such bindings.
    2. Block Storage
    	- When we need to read, write data/content very fast. Like OS, Database.
    3. File Storage
    	- When we need to structure data into file/folders.
    	- Noramally used by Network admin/peoples.

### 3. Database

    - Cloud providers has utilized the open source codes and make their own version of databases. They also maintain/run these using their own hardware. They demand that these are very fast and performant.

    1. Relational DB
    	- Stores data like Excel, in row-column format.
    	- MySQL, Oracle, PostgresSQL. In cloud - AWS Aurora.
    2. NoSQL DB
    	- Stores data in JSON, key-value format.
    	- MongoDB. In cloud - AWS Dynamo DB.
    3. In-memory DB
    	- Redis. In cloud - AWS ElastiCache.

### 4. Network

    1. Virtual Private Cloud:
    	- Connect multiple devices by configuting IP/gateway.
    2. Load Balancing:
    	- When request comes in a high ammount to a single compouter, we create a request handler that connects to multiple computers. So, now the traffic gets divider in multiple computers.
    3. Content Delivery Network:
    	- Setup many (single purpose) server in different continents to serve static data like pdf, image, video etc.

### 5. Security

    1. Identity and Access Management:
    	- There will be a Super Admin, who will pay bill, manage subcribsions etc. He can manage the users also.
    	- To manage users and user roles, Super Admin can create multiple groups where each group has a set of roles. Then he can assing user to respective group.
    2. Firewall:
    	- Define who can access and who cannot access the resources of a computer.
    	- Such as Database. We can assing particular IPs who can access it.
    	- There will be a port (virtual) related to the DB and this needs to enabled to be accessed by (permitted) user.
    3. Encryption:
    	- Website encryption wih HTTPS secure certificate.
    	- Encryption at rest: when user upload a document from the application, we will encrypt it and then save to storage.
    	- KMS: Store all the passwords encrypted a Key Management Storage. Application at first (programatically) decrypt the password from KMS and use it to login to DB.
