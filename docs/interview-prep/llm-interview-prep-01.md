---
layout: default
title: Clarify Topics After Micro1 Interview
parent: Interview
nav_order: 3
---

# Technical Interview Prep Master Summary

This document summarizes key concepts across DevOps, Algorithm Complexity, Security, and Backend Architecture.

## 1. DevOps & Deployment Strategies

Strategies to update applications, focusing on zero-downtime and risk mitigation.

* **Blue-Green Deployment:** Two identical environments (Blue=Live, Green=New). Traffic is flipped instantly at the router/load balancer level. Excellent for immediate rollbacks.
* **Canary Deployment:** Rolling out the new version to a small percentage of users (e.g., 5%) to test stability before a full rollout.
* **Rolling Deployment:** Gradually replacing instances one by one (or batch by batch) within the same environment. Cost-effective but slower to roll back.
* **Shadow Deployment:** Deploying the new version and sending a cloned copy of live traffic to it. The response is ignored/logged, allowing real-world load testing without user risk.
* **AWS Implementation:** Achieved using Application Load Balancers (Target Groups & Weighted Routing), AWS CodeDeploy (for ECS/Lambda), or Amazon Route 53 (Weighted DNS).

## 2. Big O & Algorithm Complexity

A framework for measuring the **rate of growth** of an algorithm. **Crucial distinction:** Big O does *not* measure exact execution time (in seconds) or exact memory used (in bytes). Instead, it measures how the number of operations or required space *scales* relative to the input size ($N$).

* **The Golden Rules:** Identify the scaling input ($N$), drop constant multipliers (e.g., $O(2N) \rightarrow O(N)$), and drop non-dominant terms (e.g., $O(N^2 + N) \rightarrow O(N^2)$).
* **Common Time Complexities:**
  * $O(1)$ **Constant:** Object/Map key lookups, basic math.
  * $O(\log N)$ **Logarithmic:** Halving the search space on each step (e.g., Binary Search).
  * $O(N)$ **Linear:** Standard loops, two-pointer techniques, `map()`, `forEach()`.
  * $O(N \log N)$**:** Highly optimized native sorting algorithms (like `Array.prototype.sort()`).
  * $O(N^2)$ **Quadratic:** Nested loops, or running $O(N)$ native methods (like `indexOf`) inside another $O(N)$ loop (like `filter`).
  * $O(2^N)$ **Exponential:** Naive branching recursion (e.g., standard Fibonacci sequence).
* **Multiple Inputs:** Sequential loops are added ($O(A + B)$), nested loops are multiplied ($O(A \times B)$).
* **Space Complexity:** Focuses strictly on *newly created memory* that scales with the input (e.g., mapping to a new array is $O(N)$, accumulating a `total` number variable is $O(1)$).

## 3. Application Security (AppSec)

Protecting the application against malicious user inputs executing as code.

* **SQL Injection (SQLi):** * **Target:** The Database.
  * **Attack:** Injecting malicious SQL into an input field (e.g., `admin' OR 1=1 --`) to bypass auth or dump data.
  * **Defense:** Always use **Parameterized Queries** (Prepared Statements) or an ORM to treat input purely as data, never as executable code.
* **Cross-Site Scripting (XSS):**
  * **Target:** The User's Browser.
  * **Attack:** Injecting malicious JavaScript (e.g., via a blog comment) that executes in other users' browsers to steal cookies or session tokens.
  * **Defense:** **Output Encoding/Escaping** (converting `<` to `&lt;`), implementing a **Content Security Policy (CSP)**, and marking session cookies as **HttpOnly**.

## 4. Backend Architecture & Distributed Systems

Handling multi-step processes across different services safely.

* **ACID Transactions:** Used in a monolithic architecture (single database). Guarantees "All or Nothing" execution (Atomicity, Consistency, Isolation, Durability).
* **Saga Pattern:** Used in Microservices. Since you can't wrap multiple databases in one ACID transaction, you emit events. If a downstream service (like Payment) fails, it triggers a **Compensating Transaction** in the upstream service (like Inventory) to manually undo the previous step.
* **Idempotency Keys:** A unique token (usually a UUID) passed with a request to ensure a retry (due to network drops) doesn't duplicate an action (like double-charging a card).
  * *Pro-Tip:* Generating the UUID on the **Frontend** enables "Offline-First" capabilities and ensures perfect idempotency if the network fails before the success response returns.
* **Transactional Outbox Pattern:** Solves the "Dual Write" problem. To safely save to a database *and* send a message to a queue (like RabbitMQ) without one failing, you save the event payload to an `outbox` table in the exact same database transaction. A background worker then reliably pushes the outbox events to the queue.