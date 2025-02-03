## Stack for Docker Standalone / Swarm

This stack focuses on **deploying and securing applications in Docker** without Kubernetes.

| **Category**                             | **Top Open Source & Free Application** | **Reason**                                                                                 |
|------------------------------------------|----------------------------------------|--------------------------------------------------------------------------------------------|
| **Source Code Repository and Version Control** | **Gitea**                              | Self-hosted Git, lightweight and secure.                                                   |
| **CI/CD Automation**                     | **TeamCity**                           | Powerful CI/CD with support for Docker and Swarm.                                          |
| **Static Application Security Testing (SAST)** | **SonarQube Community Edition**        | Static code analysis with vulnerability detection.                                         |
| **Software Composition Analysis (SCA)**  | **OWASP Dependency-Check**             | Identifies vulnerabilities in third-party libraries.                                       |
| **Dynamic Application Security Testing (DAST)** | **OWASP ZAP**                          | Automated web security scanning.                                                           |
| **Container Security & Image Storage**   | **Harbor**                             | Secure container registry with built-in image vulnerability scanning using Trivy.         |
| **API Security and Identity Management** | **Keycloak**                           | Secure authentication with OAuth, OpenID, and LDAP.                                        |
| **Infrastructure as Code (IaC) Security** | **Checkov**                            | Scanning Terraform and Ansible for cloud environments.                                     |
| **Threat Monitoring and Detection**      | **Wazuh**                              | Open-source SIEM for logs, threats, and compliance.                                        |
| **Incident Management and Response**     | **TheHive**                            | Platform for managing security incidents.                                                  |
| **Security Policies and Compliance**     | **Open Policy Agent (OPA)**            | Security policy enforcement in infrastructure.                                             |
| **Artifact Repository**                  | **Sonatype Nexus Repository OSS**      | Artifact storage for Maven, npm, PyPi, and Docker.                                         |

### Integration in TeamCity

✅ **CI/CD with Security**

- **Build and code analysis with SonarQube**.
- **Dependency scanning with OWASP Dependency-Check**.
- **API security testing with OWASP ZAP**.
- **Store and scan images in Harbor (Trivy integrated)**.

✅ **Deployment in Docker Standalone / Swarm**

- Build Docker image and **publish in Nexus Repository OSS or Harbor**.
- Deploy in Docker Swarm with `docker stack deploy` or standalone with `docker run`.
- **Monitor with Wazuh to detect anomalies** in containers.

✅ **Incident response with TheHive + Wazuh**

---

## Stack for Docker + Kubernetes

This stack combines security for **Docker Standalone/Swarm + Kubernetes**.

| **Category**                             | **Top Open Source & Free Application** | **Reason**                                                                                 |
|------------------------------------------|----------------------------------------|--------------------------------------------------------------------------------------------|
| **Source Code Repository and Version Control** | **Gitea**                              | Self-hosted Git, lightweight and secure.                                                   |
| **CI/CD Automation**                     | **TeamCity**                           | Powerful CI/CD with support for Docker and Kubernetes.                                     |
| **Static Application Security Testing (SAST)** | **SonarQube Community Edition**        | Static code analysis with vulnerability detection.                                         |
| **Software Composition Analysis (SCA)**  | **OWASP Dependency-Check**             | Identifies vulnerabilities in third-party libraries.                                       |
| **Dynamic Application Security Testing (DAST)** | **OWASP ZAP**                          | Automated web security scanning.                                                           |
| **Container Security & Image Storage**   | **Harbor + Falco**                     | **Harbor** for registry and Trivy-based scanning, **Falco** for runtime threat detection.  |
| **API Security and Identity Management** | **Keycloak**                           | Secure authentication with OAuth, OpenID, and LDAP.                                        |
| **Infrastructure as Code (IaC) Security** | **Checkov**                            | Terraform, Kubernetes, and Ansible auditing.                                               |
| **Threat Monitoring and Detection**      | **Wazuh + Falco**                      | **Wazuh** for logs and events, **Falco** for Kubernetes security.                          |
| **Incident Management and Response**     | **TheHive**                            | Platform for managing security incidents.                                                  |
| **Security Policies and Compliance**     | **Open Policy Agent (OPA)**            | Policy enforcement in Kubernetes and Docker.                                               |
| **Artifact Repository**                  | **Sonatype Nexus Repository OSS**      | Artifact storage for Maven, npm, PyPi, and Docker.                                         |

### Integration in TeamCity

✅ **CI/CD with Security**

- **Code scanning with SonarQube**.
- **Dependency verification with OWASP Dependency-Check**.
- **Store and scan images in Harbor (Trivy integrated)**.

✅ **Deployment in Docker and Kubernetes**

- **Docker:** Publish image in Nexus or Harbor and deploy in Standalone/Swarm.
- **Kubernetes:**
  - Create **Helm manifests** and store them in Harbor.
  - Deploy in Kubernetes with `kubectl apply -f` or **Helm**.
  - Enforce security policies with **OPA**.

✅ **Monitoring and Security**

- **Falco** for threat detection in Kubernetes.
- **Wazuh** for log analysis and compliance.

---
