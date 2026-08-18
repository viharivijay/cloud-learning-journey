#  Cloud CDN & Content Delivery Networks

##  Overview

Day 35 of my Cloud Learning Journey focused on **Content Delivery Networks (CDNs)**.

I learned how CDNs use geographically distributed edge locations to deliver content faster, reduce latency, decrease origin-server load, and improve application scalability and availability.

---

##  Topics Covered

* What is a CDN?
* CDN architecture
* Origin servers
* Edge locations
* Points of Presence (PoPs)
* CDN caching
* Cache hit
* Cache miss
* CDN request flow
* Static content delivery
* Dynamic content delivery
* Cache invalidation
* CDN security
* DDoS protection
* CDN use cases
* Popular cloud CDN services

---

##  CDN Request Flow

```text
User
  ↓
CDN
  ↓
Nearest Edge Location
  ↓
Cache Hit?
 ┌───────┴───────┐
YES              NO
 ↓                ↓
Cache          Origin Server
Content            ↓
 ↓              Response
User               ↓
              Edge Cache
                   ↓
                  User
```

---

##  Why Use a CDN?

A CDN can help:

* Reduce latency
* Improve website speed
* Reduce origin-server requests
* Handle high traffic
* Improve global performance
* Improve availability
* Deliver static content efficiently
* Add security capabilities

---

##  Popular CDN Services

| Cloud Provider  | CDN               |
| --------------- | ----------------- |
| AWS             | Amazon CloudFront |
| Microsoft Azure | Azure Front Door  |
| Google Cloud    | Cloud CDN         |
| Cloudflare      | Cloudflare CDN    |
| Akamai          | Akamai CDN        |

---

##  Key Learnings

> A CDN brings content closer to users by caching and delivering content from geographically distributed edge locations.

The most important concepts learned today were **origin server, edge location, caching, cache hit, cache miss, latency, and cache invalidation**.

---

## Folder Structure

```text
Day-35-Cloud-CDN/
│
├── README.md
└── notes.md
```

---

##  Learning Progress

**Cloud Learning Journey: Day 35/50**

Progress: `██████████████████░░ 70%`

---

