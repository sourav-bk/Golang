# ⚡ Cache and Its Types

---

## ✅ What is Cache

Cache is a **small, fast storage layer** used to store frequently accessed data so it can be retrieved quickly instead of fetching it from slower sources like databases or disks.

---

## 🎯 Why Cache is Used

- Improves application **performance and speed**  
- Reduces **database load**  
- Decreases **response time**  
- Enhances **user experience**  

---

# 🧠 Types of Cache

---

## 📌 1. In-Memory Cache

### ✅ What is
Cache stored in **RAM (memory)**.

### ⚙️ Characteristics
- Very fast access  
- Temporary storage  
- Data lost on restart  

### 💡 Examples
- Redis  
- Memcached  

### 🚀 Use Case
- Session storage  
- Frequently accessed data  
- Real-time applications  

---

## 📌 2. CPU Cache

### ✅ What is
Cache inside the **CPU** storing frequently used data and instructions.

### ⚙️ Characteristics
- Extremely fast  
- Hardware-level cache  
- Multiple levels (L1, L2, L3)  

### 🚀 Use Case
- Improves processing speed of programs  

---

## 📌 3. Disk Cache

### ✅ What is
Cache stored on **disk (HDD/SSD)**.

### ⚙️ Characteristics
- Slower than RAM  
- Persistent storage  
- Larger capacity  

### 🚀 Use Case
- File caching  
- OS-level caching  

---

## 📌 4. Browser Cache

### ✅ What is
Cache stored in the **user’s browser**.

### ⚙️ Characteristics
- Stores static files (images, CSS, JS)  
- Reduces load time  
- Stored locally  

### 🚀 Use Case
- Web applications  
- Faster page loading  

---

## 📌 5. Application Cache

### ✅ What is
Cache managed by the **application itself**.

### ⚙️ Characteristics
- Controlled by application logic  
- Can use in-memory or distributed storage  

### 🚀 Use Case
- API responses  
- Database query results  

---

## 📌 6. Distributed Cache

### ✅ What is
Cache shared across **multiple servers**.

### ⚙️ Characteristics
- Scalable  
- Shared access across systems  
- High availability  

### 💡 Examples
- Redis Cluster  
- Hazelcast  

### 🚀 Use Case
- Microservices  
- Large-scale distributed applications  

---

## 📌 7. CDN Cache

### ✅ What is
Cache stored in **global servers close to users**.

### ⚙️ Characteristics
- Reduces latency  
- Faster content delivery  
- Globally distributed  

### 💡 Examples
- Cloudflare  
- AWS CloudFront  

### 🚀 Use Case
- Static content delivery  
- Video streaming  
- Websites  

---

## ⚡ Quick Summary

| Cache Type        | Speed        | Storage     | Use Case                     |
|------------------|-------------|------------|------------------------------|
| CPU Cache        | 🚀 Fastest   | Hardware   | Program execution            |
| In-Memory Cache  | 🚀 Very Fast | RAM        | APIs, sessions               |
| Disk Cache       | ⚡ Medium    | Disk       | File storage                 |
| Browser Cache    | ⚡ Fast      | Local      | Web assets                   |
| Application Cache| ⚡ Fast      | App-level  | Queries, API responses       |
| Distributed Cache| ⚡ Fast      | Multiple   | Scalable systems             |
| CDN Cache        | ⚡ Fast      | Global     | Content delivery             |

---

## ✅ Summary

- Cache improves **performance and speed**  
- Reduces the need to fetch data repeatedly  
- Different cache types are used at different levels (CPU, app, network)  

---

✅ **Tip:** Modern applications often use **Redis (in-memory) + CDN + Browser cache** together for best performance.
