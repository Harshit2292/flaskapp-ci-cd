
# 🚀 Flask CI/CD Pipeline using GitHub Actions

This project demonstrates a **complete CI/CD automation setup** for a containerized Python Flask application using **GitHub Actions**, **Docker**, and **AWS EC2**.

---

## 🧠 What You’ll Learn

✅ Build a real-world DevOps pipeline  
✅ Automate tests and Docker builds  
✅ Push Docker images to Docker Hub  
✅ Auto-deploy to AWS EC2 via SSH  
✅ Manage secrets securely in GitHub  

---

## 🧩 Tech Stack

- **Backend:** Python (Flask)
- **Containerization:** Docker
- **CI/CD:** GitHub Actions
- **Deployment:** AWS EC2 (via SSH)
- **Registry:** Docker Hub

---

## ⚙️ Pipeline Overview

1. **Trigger:** On every `push` or `pull_request`
2. **Test:** Runs unit tests with `pytest`
3. **Build:** Builds Docker image on success
4. **Push:** Pushes image to Docker Hub (`abdulraheem381/flask-ci-cd`)
5. **Deploy:** SSHs into EC2 and pulls the latest image

---

## 📁 Project Structure

```

flaskapp-ci-cd/
│
├── app/                     # Flask source code
│   ├── **init**.py
│   └── routes.py
│
├── tests/                   # Unit tests
│   └── test_routes.py
│
├── Dockerfile               # Builds Flask image
├── requirements.txt         # Python dependencies
├── .github/
│   └── workflows/
│       └── deploy.yml       # GitHub Actions CI/CD workflow
├── deploy.sh                # Deployment script for EC2
└── README.md

````

---

## 🔧 Setup & Configuration

### 1. Clone the Repository
```bash
git clone https://github.com/abdulraheem381/flaskapp-ci-cd.git
cd flask-ci-cd
````

### 2. Add GitHub Secrets

| Secret Name          | Description                       |
| -------------------- | --------------------------------- |
| `DOCKERHUB_USERNAME` | Your Docker Hub username          |
| `DOCKERHUB_TOKEN`    | Docker Hub Access Token           |
| `AWS_EC2_HOST`       | Public IP of your EC2 instance    |
| `AWS_PRIVATE_KEY`    | Private key for SSH access to EC2 |

---

### 3. Run Locally

```bash
docker build -t flask-ci-cd .
docker run -d -p 80:5000 flask-ci-cd
```

Visit → [http://localhost](http://localhost)

---

### 4. Deployment on AWS EC2

When a new commit is pushed to `main`:

* GitHub Actions runs tests
* Builds and pushes the Docker image
* SSHs into EC2
* Pulls and runs the latest container

---

## 🚨 Rollback Strategy

If deployment fails:

* The workflow automatically exits before replacing the old container
* The previous running version stays active

---

## 🏁 Final Result

You get:

* **Continuous Integration:** Tests and builds on every push
* **Continuous Delivery:** Auto deployment to EC2
* **Real DevOps pipeline** for your resume 🎯

---

## 👨‍💻 Author

**Abdul Raheem**
DevOps Engineer | Building Cloud & CI/CD Solutions
Docker Hub: [abdulraheem381](https://hub.docker.com/u/abdulraheem381)

---

## 🌟 Support

If you find this useful, give it a ⭐ on GitHub and tag [@the expert’s X handle] when you share your completed project!

=
