# 🎮 Number Rush – Guess The Number Game

**Number Rush** is a fun and interactive web game where players try to guess the correct number in the shortest time possible.  
This project demonstrates hands-on experience in **AWS cloud architecture**, using a **serverless approach** to build, secure, and deploy an application at scale. It also demonstrates the power of excellent AI prompt engineering to generate code to serve business objectives.

---

## 🚀 Features
- Web-based game built with **HTML, CSS, and JavaScript**.
- **Real-time leaderboard** where players can submit and view scores.
- Fully serverless backend powered by **AWS Lambda, DynamoDB, and API Gateway**.
- **CloudFront distribution** for low-latency, globally accessible content.
- **CORS-enabled APIs** to securely allow communication between frontend and backend.
- **AI Prompt Engineering** used to accelerate development and debugging.

---

## 🚀 Live Demo

Play the game: https://d3hcutenmgefoj.cloudfront.net/

---

## 🏗️ Architecture

The architecture follows a **serverless and event-driven design**:

[User Browser]
⬇️
[Amazon CloudFront] → [Amazon S3 (Static Website Hosting)]
⬇️
[Amazon API Gateway (REST API)]
⬇️
[AWS Lambda Functions]
⬇️
[Amazon DynamoDB (Leaderboard Storage)]


- **Amazon S3** → Hosts the static web assets (HTML, CSS, JS).  
- **Amazon CloudFront** → Provides a fast, cached, globally distributed version of the game.  
- **Amazon API Gateway** → Exposes REST endpoints for score submission & leaderboard retrieval.  
- **AWS Lambda** → Handles business logic (submit score, fetch leaderboard).  
- **Amazon DynamoDB** → Stores and retrieves leaderboard data.  
- **Amazon CloudWatch** → Logs and monitors Lambda/API activity.  
- **IAM Roles & Policies** → Enforce least-privilege access and secure integration between services.

---

## ⚙️ Tech Stack
- **Frontend:** HTML, CSS, JavaScript  
- **Backend:** AWS Lambda (Python)  
- **Database:** Amazon DynamoDB  
- **Cloud Services:** S3, CloudFront, API Gateway, IAM, CloudWatch  
- **Other Skills:** Python scripting, AI prompt engineering  

---

## 🔧 Setup Instructions

### 1. Clone the Repository
git clone https://github.com/Trevor-Sone/number-rush.git
cd number-rush
### 2. Frontend Deployment
Upload the index.html, style.css, and script.js files to an S3 bucket.

Enable static website hosting in S3.

Set bucket policy to allow public read access (or serve privately through CloudFront).

### 3. CloudFront Distribution
Create a CloudFront distribution pointing to the S3 bucket as origin.

Configure default root object → index.html.

Optional: Add custom domain (Route 53) and SSL certificate (ACM).

### 4. Backend Deployment
Create DynamoDB table for storing scores (e.g., Leaderboard with PlayerName and Score attributes).

Create Lambda functions:

submitScore → Writes player score to DynamoDB.

getLeaderboard → Reads and returns leaderboard data.

Connect functions to API Gateway REST endpoints (/score, /leaderboard).

Enable CORS for both endpoints.

### 5. Testing
Access the CloudFront distribution URL.

Play the game, submit scores, and check the leaderboard updates in real-time.

### 📚 Lessons Learned
Gained hands-on experience with serverless architecture on AWS.

Learned how to configure CORS policies in API Gateway.

Practiced troubleshooting Lambda → DynamoDB → API Gateway integrations.

Improved development efficiency by leveraging AI prompt engineering for code generation, debugging, and design ideas.



### 👨‍💻 Author
**Emmanuel Trevor Chieh Sone**

Aspiring AWS Solutions Architect Associate

Passionate about Cloud Computing, Serverless Solutions, and AI Integration

LinkedIn: https://www.linkedin.com/in/trevor-sone-8a7b28340
