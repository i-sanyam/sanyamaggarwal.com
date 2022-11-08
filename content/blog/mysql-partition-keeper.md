---
date: '2021-12-07'
title: How to automatically maintain a MySQL Table’s Partitions?
tags: [mysql, partition, nodejs, time series data]
author: Sanyam Aggarwal
link: https://sanyamaggarwal.medium.com/how-to-automatically-maintain-a-mysql-tables-partitions-with-mysqlpartitionkeeper-f9923f973135
post_type: medium
description: How I automated the manually maintaining MySQL Partitions

---

A lot of data in applications is time-stamped and is it is sequenced in that manner. Only the data of a defined time range will be really required in the active working of the application and the rest will just be historical data available for downloads, reports etc. A great example of this can be order history of a user. Only the past 1 month order data may be relevant and available for the user to perform some actions.

Time series data is usually best managed in partitions and since there cannot be a infinite number of partitions, periodic maintenance of partitions - dropping old partitions and creating new ones - is required. Manual maintenance is prone to delays and errors. Read on to know how I created a script for automatic maintenance for partitions. 