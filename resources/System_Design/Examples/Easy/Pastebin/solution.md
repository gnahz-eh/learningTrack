# Design a Pastebin-like service

## Introduction
Pastebin.com like services enable users to store plain text or images over the network (typically the Internet) and generate unique URLs to access the uploaded data. Such services are also used to share data over the web quickly, as users would need to pass the URL to let other users see it.

## Features
- What should be the limit on the amount of text a user can paste at a time?
  - We can limit users not to have Pastes bigger than 10MB to stop the abuse of the service.
- Should we impose size limits on custom URLs?
  - Since our service supports custom URLs, users can pick any URL they like, but providing a custom URL is not mandatory. However, it is reasonable (and often desirable) to impose a size limit on custom URLs to have a consistent URL database.

## Requirements
### Functional Requirements
- Users should upload or "paste" their data and get a unique URL to access it.
- Users will only be able to upload text.
- Data and links will automatically expire after a specific timespan; users should also specify expiration time.
- Users should optionally be able to pick a custom alias for their paste.

### Non-Functional Requirements
- The system should be highly reliable, any data uploaded should not be lost.
- The system should be highly available. This is required because if our service is down, users will not access their Pastes.
- Users should be able to access their Pastes in real-time with minimum latency.
- Paste links should not be guessable (not predictable).

## Capacity Estimation

| Category           | Metric                 | Value        | Calculation                                        |
|--------------------|------------------------|--------------|----------------------------------------------------|
| **Traffic**        | Read/Write Ratio       | 100:1        | Assumed                                            |
|                    | New Pastes per day     | `1m`         |                                                    |
|                    | New Pastes per secomd  | `10/s`       | 1M / (24 hours * 3600 seconds) ~= 10 pastes/sec    |
|                    | Read per secomd        | `1200/s`     | 100M / (24 hours * 3600 seconds) ~= 1200 reads/sec |
| **Storage**        | Max size per paste     | `10MB`       | Assumed                                            |
|                    | Avg size per paste     | `100KB`      | Assumed                                            |
|                    | Storage per day        | `100 GB/day` | 1M * 10KB = 100 GB/day                             |
|                    | Storage lifttime       | 5 years      | Assumed                                            |
|                    | Storage totally        | 180TB        | 100 GB * 365 days * 5 years ~= 180 TB              |
|                    | Total Pastes count     | `2b`         | 1M * 365 * 5 ~= 2 Billion                          |
|                    | Latters needed for URL | `6`          | Base64 encoding: 64^6 ~= 68.7 billion              |
| **BandWidth**      | Ingress per second     | 1MB/s        | 10 * 100 KB = 1 MB/s                               |
|                    | Egress per second      | 100MB/s      | 1000 * 100 KB = 100 MB/s                           |
| **Memory & Cache** | Cache principle        | 80:20 rule   | Pareto Principle (80% requests for 20% data)       |
|                    | Cache size per day     | 2TB          | 0.2 * 100 M * 100 KB ~= 2 TB                       |


## High Level Design

## Detail Design
### API Design

---

### Database Design

---

### Database Choice

---

### Scaling (Data Partitioning and Replication)

---

### Cache

---

### Load Balancer (LB)

---

### Purging or DB cleanup

## Architecture

## FAQs

## Resources