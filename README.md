# Install Docker on Ubuntu EC2 (AWS)

## 📌 Prerequisites
- An AWS EC2 instance running Ubuntu (20.04/22.04)
- SSH access to the instance

## 🚀 Step 1: Update System Packages
```bash
sudo apt update && sudo apt upgrade -y
```

## 🐳 Step 2: Install Docker
```bash
sudo apt install -y docker.io
```

## 🔥 Step 3: Enable and Start Docker Service
```bash
sudo systemctl enable docker
sudo systemctl start docker
```

## 🔄 Step 4: Add User to Docker Group (Optional)
To run Docker without `sudo`, add your user to the `docker` group:
```bash
sudo groupadd docker  # Create docker group if not exists
sudo usermod -aG docker $USER
newgrp docker  # Apply changes immediately
```

## ✅ Step 5: Verify Installation
```bash
docker --version
sudo docker run hello-world
```

## ⚡ Troubleshooting
If you get `permission denied` errors:
```bash
sudo chmod 666 /var/run/docker.sock
```
If Docker service is missing:
```bash
sudo apt remove -y docker.io && sudo apt install -y docker.io
```

## 🎯 Next Steps
- Deploy containers using `docker run`
- Use `docker-compose` for multi-container applications
- Learn about Kubernetes for container orchestration

---
📖 **Maintained by:** Priyanshu Kumar Sharma
