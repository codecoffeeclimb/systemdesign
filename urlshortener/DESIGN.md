## Requirements and Goals
URL shorterner has following requirements
1. Create short URL from a regular URL
2. Redirect to original URL from short URL
3. Create user account

## Capacity Estimation and Constraints
Basic numbers:
1. 500 millions new url per month
2. read to write ratio is 100:1
3. average URL storage size is 500 bytes (URL and metadata)

Derived numbers:
1. Storage for 5 years:
  * 500M/month * 12 month * 5 year = 30B URLs
  * 30B * 500 byte = 15TB storage

2. QPS
  * Write: 500M/month / 30 days / 86400 second = 200/s
  * Read: 200/s * 100 = 20K/s

## System API
1. Shorten URL
```
POST /
body parameters:
 - url: [string][required] original url
 - ttl: [int] number of second until expire
```
2. Redict
```
GET /{short URL key}
```

## Database Design

## Core Design

## Scalability
