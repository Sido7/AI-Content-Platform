# 🧠 AI Content Platform — Microservices Architecture

This repository serves as the **entry point (face repo)** for the **AI Content Platform**, a distributed microservices-based system designed to automate **content aggregation, analysis, and publishing** using AI.

The platform is built with **Node.js**, **TypeScript**, and **modern backend technologies** like **Kafka**, **Redis**, **MongoDB**, and **Cloud Workers**, emphasizing **scalability**, **modularity**, and **performance**.

---

## 🚀 Overview

The **AI Content Platform** is composed of multiple services, each responsible for a specific domain function.  
Together, they form a robust ecosystem capable of:

- 📰 Fetching and aggregating articles from multiple sources  
- 🤖 Summarizing and analyzing content using AI  
- 🧩 Managing users, vendors, and permissions  
- ⚡ Processing data asynchronously using queues and streams  
- 📤 Exposing APIs for web and mobile clients  

---

## 🧩 Architecture at a Glance

```mermaid
flowchart TD
  A[Aggregator Service] --> B[AI Processing Service]
  B --> C[Article Service]
  C --> D[User Service]
  C --> E[Notification Service]
  E --> F[Redis Queue]
  B --> G[(MongoDB)]
  C --> G
  D --> G
  E --> G
  subgraph infra[Infrastructure]
    G
    F
    H[(Kafka Bus)]
  end
  H <--> B
  H <--> A
| Service                      | Description                                                                                | Repository                                                                        |
| ---------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| 📰 **Aggregator Service**    | Crawls and aggregates articles from HTML/RSS websites, cleans data, and publishes events.  | [Aggregator Service Repo](https://github.com/yourusername/aggregator-service)     |
| 🤖 **AI Processing Service** | Uses AI APIs (e.g., Gemini, OpenAI) to summarize, extract keywords, and analyze sentiment. | [AI Service Repo](https://github.com/yourusername/ai-service)                     |
| 📚 **Article Service**       | Stores processed articles and exposes REST APIs for client apps.                           | [Article Service Repo](https://github.com/yourusername/article-service)           |
| 👤 **User Service**          | Handles authentication, user profiles, roles, and permissions.                             | [User Service Repo](https://github.com/yourusername/user-service)                 |
| 🔔 **Notification Service**  | Sends real-time notifications and updates via queues or pub/sub.                           | [Notification Service Repo](https://github.com/yourusername/notification-service) |
| 🧱 **Common Library**        | Shared utilities, DTOs, and interfaces used across services.                               | [Common Lib Repo](https://github.com/yourusername/common-lib)                     |
