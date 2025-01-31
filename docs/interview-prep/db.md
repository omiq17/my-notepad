---
layout: default
title: Database
parent: Interview
---

1. Optimizing an heavyload db table

   Like oder table in an e-commerce project.

   a. Indexing - Primary key, foreign key, composite index.

   b. Partitioning -

   Range partioning- like split orders based on data_range.
   List partitioning- separate data by oder status (pending, shipped).
   Has partitioning- Distribute orders evenly across partitions using customer_id.

   c. Archiving old data - keep only the latest 3 months data in the table.

   d. Caching - using Redis library.

   e. Backgroud processing for heavy tasks - Use message queues like AWS SQS. Make scheduler.
