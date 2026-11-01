# Raspberry Pi Cybersecurity Home Lab

A standalone cybersecurity learning environment built using a Raspberry Pi 3B+, Docker and intentionally vulnerable web applications.

## Project Overview

This project provides an isolated environment for learning:

- Linux administration
- Networking and TCP/IP
- Docker and containerisation
- Web application security
- Vulnerability assessment
- Network traffic analysis
- Cybersecurity fundamentals

The lab is intended to complement my ongoing CompTIA studies and practical cybersecurity training through TryHackMe.

## Hardware and Software

| Component | Configuration |
|---|---|
| Hardware | Raspberry Pi 3B+ |
| Operating System | Raspberry Pi OS Legacy Lite 64-bit |
| Container Platform | Docker |
| Container Management | Docker Compose |
| Wireless Network | Apple AirPort Express Gen 2 |
| Network SSID | PenTest_Lab |

## Network Design

The lab uses a dedicated wireless network named:

`PenTest_Lab`

The intention is to keep the lab completely separate from the normal home network and internet.

Network isolation will be verified before security testing begins.

## Docker Project

Project name: `homeLab`

Project directory:

`/home/user1/homeLab/`

Docker Compose file:

`/home/user1/homeLab/docker-compose.yml`

## Running Containers

| Container | Image / Build | Port | Purpose |
|---|---|---:|---|
| basic-web-server | nginx:alpine | 8080 | Basic web server |
| uptime-kuma | louislam/uptime-kuma:2 | 3001 | Service monitoring |
| juice-shop | bkimminich/juice-shop:latest | 3000 | Vulnerable web application |
| dvwa-target | Local build | 31337 | Vulnerable web application |
| dvwp-db | mariadb:10.5 | 3306 internal | Database service |

All five containers have been confirmed running.

## Applications

### Nginx

A basic web server used to understand HTTP services and web hosting.

Persistent/local content directory:

`./html`

### Uptime Kuma

A monitoring application used to monitor service availability.

Persistent data directory:

`./uptime-kuma`

### OWASP Juice Shop

An intentionally vulnerable web application used for practical web security learning.

Areas for exploration include:

- Authentication weaknesses
- Access control
- SQL injection
- Cross-site scripting
- Security misconfiguration

### DVWA

Damn Vulnerable Web Application provides a controlled environment for learning common web application vulnerabilities.

Local build directory:

`./dvwa-src`

Planned exercises include:

- SQL injection
- Cross-site scripting
- Command injection
- File inclusion
- Input validation

### MariaDB

Database service supporting DVWA.

Database port:

`3306` (internal container service)

## Useful Docker Commands

Check running containers:

```bash
docker ps


## Project Screenshots

### Docker Compose Configuration

The Docker Compose configuration used to deploy and manage the home lab services.

![Docker Compose](images/IMG_0778.jpg)

### Container Configuration

The Docker environment showing the deployed applications and their configuration.

![Container Configuration](images/IMG_0779.jpg)

### Running Containers

Confirmation that all five Docker containers are running successfully.

![Running Containers](images/IMG_0780.jpg)

### Service Status

Additional evidence of the deployed services and their availability.

![Service Status](images/IMG_0781.jpg)
