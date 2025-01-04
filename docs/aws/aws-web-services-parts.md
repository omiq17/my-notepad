---
layout: default
title: Parts of AWS
parent: AWS
nav_order: 3
---

## Parts of AWS

### 1. Lambda

    Just a function, Amazone take all the responsibility to execute it.

### 2. ECS

**Elastic Container Service**

Background:

    In Vitualization, we need to handle the hardware, OS and applaction dependencies. Containerization is two step ahead of it. We just need to take care of application dependencies (via docker image) .

Core:

    Amazon ECS does the containarization for us. We just need to provide the docker image to it.

### 3. Lightsail

    One step further of EC2. We do not need to configure ourself. It is like a builder for our cloud computer.

### 4. S3

**Simple Storage Service**

    It is like a bucket. We can store any kind of data like file, video, json etc., mostly unstructured data. It includes log files, videos, backup data etc.

    Retrieve data by exact key.

    Act as a Data Lake. We can utilize this data for AI, ML etc.
