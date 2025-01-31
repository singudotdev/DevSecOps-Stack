# 🚀 Open Source + Free DevSecOps Stack Compatible with TeamCity

Scenarios:  
1️⃣ **Docker Standalone / Swarm**  
2️⃣ **Docker + Kubernetes**  

---

## 🚀 1️⃣ Stack for Docker Standalone / Swarm  
This stack focuses on **deploying and securing applications in Docker** without Kubernetes.  

| **Category** | **Top Open Source & Free Application** | **Reason** |
|--------------|--------------------------------|----------------|
| **Source Code Repository and Version Control** | **Gitea** | Self-hosted Git, lightweight and secure. |
| **CI/CD Automation** | **TeamCity** | Powerful CI/CD with support for Docker and Swarm. |
| **Static Application Security Testing (SAST)** | **SonarQube Community Edition** | Static code analysis with vulnerability detection. |
| **Software Composition Analysis (SCA)** | **OWASP Dependency-Check** | Identifies vulnerabilities in third-party libraries. |
| **Dynamic Application Security Testing (DAST)** | **OWASP ZAP** | Automated web security scanning. |
| **Container Security** | **Trivy** | Vulnerability scanning for Docker images. |
| **Docker Registry and Image Security** | **Harbor + Trivy** | Secure container registry with built-in image vulnerability scanning. |
| **API Security and Identity Management** | **Keycloak** | Secure authentication with OAuth, OpenID, and LDAP. |
| **Infrastructure as Code (IaC) Security** | **Checkov** | Scanning Terraform and Ansible for cloud environments. |
| **Threat Monitoring and Detection** | **Wazuh** | Open-source SIEM for logs, threats, and compliance. |
| **Incident Management and Response** | **TheHive** | Platform for managing security incidents. |
| **Security Policies and Compliance** | **Open Policy Agent (OPA)** | Security policy enforcement in infrastructure. |
| **Artifact Repository** | **Sonatype Nexus Repository OSS** | Artifact storage for Maven, npm, PyPi, and Docker. |

### 🛠 Integration in TeamCity  
✅ **CI/CD with Security**  
- **Build and code analysis with SonarQube**.  
- **Dependency scanning with OWASP Dependency-Check**.  
- **API security testing with OWASP ZAP**.  
- **Docker image scanning with Trivy (Harbor) before deploying**.  
- **Store images in Harbor**.  

✅ **Deployment in Docker Standalone / Swarm**  
- Build Docker image and **publish in Nexus Repository OSS or Harbor**.  
- Deploy in Docker Swarm with `docker stack deploy` or standalone with `docker run`.  
- **Monitor with Wazuh to detect anomalies** in containers.  

✅ **Incident response with TheHive + Wazuh**  

---

## 🚀 2️⃣ Stack for Docker + Kubernetes  
This stack combines security for **Docker Standalone/Swarm + Kubernetes**.  

| **Category** | **Top Open Source & Free Application** | **Reason** |
|--------------|--------------------------------|----------------|
| **Source Code Repository and Version Control** | **Gitea** | Self-hosted Git, lightweight and secure. |
| **CI/CD Automation** | **TeamCity** | Powerful CI/CD with support for Docker and Kubernetes. |
| **Static Application Security Testing (SAST)** | **SonarQube Community Edition** | Static code analysis with vulnerability detection. |
| **Software Composition Analysis (SCA)** | **OWASP Dependency-Check** | Identifies vulnerabilities in third-party libraries. |
| **Dynamic Application Security Testing (DAST)** | **OWASP ZAP** | Automated web security scanning. |
| **Container Security** | **Trivy + Falco** | **Trivy** for image scanning, **Falco** for runtime threat detection. |
| **Docker Registry and Image Security** | **Harbor + Trivy** | Secure container registry with built-in image vulnerability scanning and Helm Chart storage. |
| **API Security and Identity Management** | **Keycloak** | Secure authentication with OAuth, OpenID, and LDAP. |
| **Infrastructure as Code (IaC) Security** | **Checkov** | Terraform, Kubernetes, and Ansible auditing. |
| **Threat Monitoring and Detection** | **Wazuh + Falco** | **Wazuh** for logs and events, **Falco** for Kubernetes security. |
| **Incident Management and Response** | **TheHive** | Platform for managing security incidents. |
| **Security Policies and Compliance** | **Open Policy Agent (OPA)** | Policy enforcement in Kubernetes and Docker. |
| **Artifact Repository** | **Sonatype Nexus Repository OSS** | Artifact storage for Maven, npm, PyPi, and Docker. |

### 🛠 Integration in TeamCity  
✅ **CI/CD with Security**  
- **Code scanning with SonarQube**.  
- **Dependency verification with OWASP Dependency-Check**.  
- **Docker image scanning with Trivy (Harbor) before publishing**.  
- **Store images in Harbor, including Helm Chart storage**.  

✅ **Deployment in Docker and Kubernetes**  
- **Docker:** Publish image in Nexus or Harbor and deploy in Standalone/Swarm.  
- **Kubernetes:**  
  - Create **Helm manifests** and store them in Harbor.  
  - Deploy in Kubernetes with `kubectl apply -f` or **Helm**.  
  - Enforce security policies with **OPA**.  

✅ **Monitoring and Security**  
- **Falco** for threat detection in Kubernetes.  
- **Wazuh** for log analysis and compliance.  

✅ **Incident response with TheHive + Wazuh**  

---

## 🚀 Comparison Between the Two Stacks  

| Feature | Docker Standalone/Swarm | Docker + Kubernetes |
|--------------|----------------------|----------------------|
| **CI/CD Automation** | ✅ TeamCity | ✅ TeamCity |
| **SAST** (Static Code Analysis) | ✅ SonarQube | ✅ SonarQube |
| **SCA** (Dependency Analysis) | ✅ OWASP Dependency-Check | ✅ OWASP Dependency-Check |
| **DAST** (Dynamic Security Testing) | ✅ OWASP ZAP | ✅ OWASP ZAP |
| **Docker Image Scanning** | ✅ Trivy + Harbor | ✅ Trivy + Harbor |
| **Runtime Security Scanning** | ❌ (Not applicable) | ✅ Falco (for Kubernetes) |
| **Log and Threat Monitoring** | ✅ Wazuh | ✅ Wazuh + Falco |
| **Artifact Management** | ✅ Nexus Repository OSS | ✅ Nexus Repository OSS |
| **Deployment** | ✅ Docker Standalone/Swarm | ✅ Docker + Kubernetes |
| **Infrastructure Security (IaC)** | ✅ Checkov | ✅ Checkov |
| **Compliance and Policies** | ✅ OPA (Optional) | ✅ OPA (Integrated with Kubernetes) |

---

## 🚀 Conclusion  
- **If you only use Docker (Standalone/Swarm)**: Focus on **image security, dependency scanning, and container monitoring**.  
- **If you use Docker + Kubernetes**: Add **runtime security with Falco, policy enforcement with OPA, and Helm Charts for deployments**.  
