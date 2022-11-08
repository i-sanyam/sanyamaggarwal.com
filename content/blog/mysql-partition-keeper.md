---
date: '2021-12-07'
title: How to automatically maintain a MySQL Table’s Partitions?
tags: [mysql, partition, nodejs, time series data]
author: Sanyam Aggarwal
link: https://sanyamaggarwal.medium.com/how-to-automatically-maintain-a-mysql-tables-partitions-with-mysqlpartitionkeeper-f9923f973135
post_type: medium
description: There cannot be an infinite number of partitions, so partitioning comes with the overhead of maintenance. Manual Partition Maintenance is prone to ...

---

We are going to talk here about time series data and Partitions in MySQL. If you are not familiar with these I highly recommend you read [the prevoius blog post](/blog/mysql-reduce-query-time-2000x)

Since there cannot be a infinite number of partitions, periodic maintenance of partitions - dropping old partitions and creating new ones - is required. Manual Partition Maintenance is prone to delays and errors. Read on to know how I created a script for automatic maintenance for partitions. 