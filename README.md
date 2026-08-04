<div align="center">
    <img src="frontend/images/mirotalk-icon.png" width="180">
</div>

<h1 align="center">MiroTalk C2C Deployment Project</h1>

<h3 align="center">
Deploying the MiroTalk C2C video conferencing platform using Docker, Containerlab, Proxmox VE, Ubuntu Server, and Ngrok.
</h3>

<br />

<div align="center">

![Project](https://img.shields.io/badge/Project-MiroTalk%20C2C-blue)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker&logoColor=white)
![Containerlab](https://img.shields.io/badge/Containerlab-Virtual%20Network-orange)
![Proxmox](https://img.shields.io/badge/Proxmox-VE-E57000?logo=proxmox&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-E95420?logo=ubuntu&logoColor=white)
![Ngrok](https://img.shields.io/badge/Ngrok-Public%20Tunnel-1F1F1F)

</div>

<br />

<p align="center">
This repository contains my university deployment project for <strong>MiroTalk C2C</strong>. The project demonstrates how to deploy a secure peer-to-peer WebRTC video conferencing platform using modern virtualization, containerization, and networking technologies.
</p>

<p align="center">
The deployment environment includes Docker containers, Containerlab virtual networking, Proxmox VE virtualization, Ubuntu Server hosting, and Ngrok for secure public access.
</p>

<br />

<p align="center">
    <img src="frontend/images/ui.png" alt="MiroTalk C2C">
</p>

---

# 📌 Project Overview

This project demonstrates the complete deployment of **MiroTalk C2C** from source code into a virtualized infrastructure.

The environment consists of:

- Ubuntu (WSL)
- Docker
- Containerlab
- Proxmox VE
- Ubuntu Server Virtual Machine
- Ngrok
- GitHub

The application was successfully deployed, tested locally, and published through a secure HTTPS tunnel using Ngrok.

---

# 🏗 Project Architecture

```
             Client
                │
                │
          Internet / HTTPS
                │
              Ngrok
                │
                │
         Ubuntu Server VM
           (Proxmox VE)
                │
          Docker Container
          MiroTalk C2C
                │
      -----------------------
      │                     │
   Router               Server
 (Containerlab)     (Containerlab)
```

---

# 🖥 Technologies Used

- Ubuntu (WSL)
- Ubuntu Server
- Docker
- Containerlab
- Proxmox VE
- VirtualBox
- Ngrok
- Git
- GitHub
- MiroTalk C2C

---

# ⚡ Deployment Steps

## 1. Clone Repository

```bash
git clone https://github.com/miroslavpejic85/mirotalkc2c.git
cd mirotalkc2c
```

---

## 2. Configure Environment

```bash
cp .env.template .env
```

---

## 3. Deploy using Docker

```bash
docker compose up -d
```

---

## 4. Deploy Containerlab Topology

```bash
cd containerlab

sudo containerlab deploy -t lab.clab.yml
```

---

## 5. Verify Running Containers

```bash
docker ps
```

Expected containers:

- mirotalkc2c
- clab-mirotalk-project-router
- clab-mirotalk-project-server

---

## 6. Publish Using Ngrok

```bash
ngrok http 8080
```

Ngrok generates a secure public HTTPS URL that forwards traffic to:

```
http://localhost:8080
```

---

# 📂 Containerlab Topology

```yaml
name: mirotalk-project

topology:
  nodes:

    router:
      kind: linux
      image: ubuntu:24.04

    server:
      kind: linux
      image: ubuntu:24.04

  links:
    - endpoints:
      - router:eth1
      - server:eth1
```

---

# ✅ Project Features

- Dockerized Deployment
- Virtual Networking with Containerlab
- Ubuntu Server hosted on Proxmox VE
- Public HTTPS access using Ngrok
- WebRTC Peer-to-Peer Video Calls
- Screen Sharing
- End-to-End Encryption

---

# 📷 Project Screenshots

Screenshots included in the report demonstrate:

- Ubuntu WSL
- Docker Installation
- Containerlab Deployment
- Proxmox VE
- Ubuntu Server
- Docker Containers
- Ngrok Tunnel
- Running MiroTalk Interface

---

# 🎯 Project Result

The project successfully demonstrates a complete deployment pipeline using virtualization, containers, virtual networking, and secure remote access.

---


**Mohammed Daraghmeh**

Computer Science Student

