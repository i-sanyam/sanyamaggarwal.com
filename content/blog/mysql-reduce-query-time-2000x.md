---
date: '2021-11-08'
title: Partitioning — Reduce query time by 2000x in a MySQL table with 500M+ rows
tags: [mysql, partition, optimisation, time series data,]
author: Sanyam Aggarwal
link: https://sanyamaggarwal.medium.com/partitioning-optimising-query-time-by-2000x-in-a-table-with-500m-rows-80c16100fede
post_type: medium
description: There was one incident where the API which fetched the data for our homepage was very slow, leading to users restarting the application and ....

---

A lot of data in applications is time-stamped and is it is sequenced in that manner. Only the data of a defined time range will be really required in the active working of the application and the rest will just be historical data available for downloads, reports etc. A great example of this can be order history of a user. Only the past 1 month order data may be relevant and available for the user to perform some actions. Time series data is usually best managed in partitions. 

There was one incident where the API which fetched the data for our homepage was very slow, leading to users restarting the application and again calling the API and yes, the hell broke all loose, it really did. Read on to know how I was able to reduce the query time from 2.6 seconds to 1 millisecond by partitioning a MySQL table with 500 Million+ rows.