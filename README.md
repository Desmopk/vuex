# 🎬 Vuex — Full Stack Video Streaming App

Vuex is a powerful and scalable **video streaming platform** (like YouTube) built with a modern microservice architecture. It uses **Flutter** for the frontend and **FastAPI**, **AWS**, **Docker**, **PostgreSQL**, **Redis**, and **FFmpeg** for the backend.



---

## 🧰 Tech Stack

### 🔙 Backend
- **FastAPI** (Python)
- **PostgreSQL** with SQLAlchemy
- **Redis** (Caching)
- **AWS S3** (Video & Thumbnail Storage)
- **AWS SQS + ECS** (Video Processing Workers)
- **AWS Cognito** (Authentication)
- **Docker + Docker Compose**
- **FFmpeg** (Video Transcoding)
- **CloudFront CDN** (Video & Thumbnail Distribution)

### 📱 Frontend
- **Flutter** (Cross-platform)
- **Bloc & Cubit** (State Management)
- **Flutter Secure Storage** (Token persistence)
- **DASH Playback** via video player

---

## 🔥 Key Features

- 📦 Dockerized backend with FastAPI, PostgreSQL, Redis
- 📷 Secure video and thumbnail uploads using AWS S3
- 🎞️ Server-side video transcoding (HLS/MPEG-DASH)
- 🐳 Microservices architecture for scalability
- 🔐 Secure signup/login using AWS Cognito
- 🔁 Token refresh and auth state persistence
- 📱 Beautiful Flutter frontend
- 🚀 Hosted with AWS ECS, ECR, CloudFront

---

## 🚀 Getting Started

### 📦 Prerequisites
- Docker & Docker Compose
- AWS Account with S3, SQS, Cognito, ECS access
- Flutter SDK
- Python 3.9+

---

### 🐳 Backend Setup

```bash
# Clone the repo
git clone https://github.com/Desmopk/vuex.git
cd vuex/backend

# Create .env file from example and configure
cp .env.example .env

# Build and start Docker containers
docker-compose up --build
```
### 📱 Frontend Setup
```bash
cd ../frontend

# Get dependencies
flutter pub get

# Run the app (use emulator or device)
flutter run
```
### 🎥 Backend Architecture
- Upload Video → AWS S3 Presigned URL
- Notify SQS → Consumer pulls from SQS
- FFmpeg → Transcodes video (ABR: HLS / DASH)
- ECS Tasks → Perform heavy compute (segmentation, thumbnail generation)
- Video Metadata API → FastAPI + PostgreSQL
- Auth → AWS Cognito for signup, login, refresh

### 🛡️ Authentication Flow
- AWS Cognito signup/login
- Secure storage using Flutter Secure Storage
- Access + Refresh token system
- Auto-refresh with Bloc state persistence
### 📦 Deployment
- Backend: Dockerized containers deployed to AWS ECS
- Media: Stored in S3 and distributed via CloudFront
- Video Processing: Done in ECS worker containers using FFmpeg

