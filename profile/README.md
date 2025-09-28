# 🎮 Welcome to PibbleTV

PibbleTV is a **gaming livestreaming platform** that enables users to broadcast their gameplay in real time to an online audience.  
This is a **personal project** created to explore livestreaming technology and deepen my skills as a software developer.  
The application supports **real-time screen broadcasting** with **high-quality video delivery** and a scalable, microservices-based backend.

---

## 📑 Table of Contents

- [📺 Project Description]
- [🗂️ Project Structure]
- [🛠️ Tech Stack]
- [⚙️ Livestreaming Logic]
- [✅ Result & Learnings]

---

## 📺 Project Description

PibbleTV was designed to replicate the core functionality of platforms like **Twitch** or **YouTube Live**, including:

- Real-time gameplay streaming  
- Stream category management  
- User accounts and authentication  
- Follow system  
- Donation support for streamers  

> ⚠️ Since this is a personal project, it is not publicly hosted online.

---

## 🗂️ Project Structure

All repositories are organized within a single GitHub organization for easier navigation.  

### 📁 Repositories

| Repository | Purpose |
|------------|---------|
| **react-app** | Frontend user interface |
| **api-gateway** | Routes and authorizes frontend → backend requests |
| **service-registry** | Eureka service registry for microservice discovery |
| **user-service** | Business logic for user management |
| **streaming-service** | Handles livestream functionality |
| **follows-service** | Follower system between users |
| **category-service** | Category creation and management |
| **donations-service** | Donation handling and processing |

Each microservice has its **own database**, ensuring loose coupling and scalability.

---

## 🛠️ Tech Stack

- 🖥️ **Frontend:** React (TypeScript)  
- ⚙️ **Backend Microserices:** Spring Boot (WebFlux)
- 🗄️ **Database:** MySQL  

---

## ⚙️ Livestreaming Logic

Here’s how the livestreaming flow works end-to-end:

OBS (or other recorder)
-> (SRT: secure, low-latency ingest)
SRS (receives SRT, outputs HLS)
-> (HLS: chunked stream)
NGINX (serves HLS playlists + segments)
->
Cloudflare (CDN to distribute globally)
->
Video.js (player for users)

- **SRT**: Used as the ingest protocol for low-latency and secure transmission.  
- **SRS**: Media server that converts streams to HLS format.  
- **HLS**: Chunked delivery for scalable and reliable distribution.  
- **Cloudflare CDN**: Ensures low-latency playback globally.  
- **Latency (10–30s)**: A deliberate design choice to reduce issues like **stream sniping** common in gaming streams.

---

## ✅ Result & Learnings

This project gave me hands-on experience with:

- ⚡ **Spring WebFlux** — Reactive backend programming  
- 🧩 **Microservice Architecture** — Service discovery, gateway routing, database isolation  
- ☁️ **Kubernetes** — Orchestrating scalable backend deployments  

I deployed the system to a **managed Kubernetes cluster on DigitalOcean**, which taught me about:

- Cloud deployment and DevOps fundamentals  
- Infrastructure provisioning and management  
- Scalable microservices and streaming architecture  

Additionally, I gained deeper insight into how platforms like **Twitch** and **YouTube Live** implement and manage their **live video infrastructure** at scale.
