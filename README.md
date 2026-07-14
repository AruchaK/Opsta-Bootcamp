# Opsta Bootcamp: Bookinfo Microservices Workshop

This project is part of the **Opsta Bootcamp**, showcasing a complete DevSecOps lifecycle. It involves deploying the polyglot **Bookinfo** application on Google Kubernetes Engine (GKE) using modern CI/CD practices and automated security gates.

## 🏗 System Architecture

The **Bookinfo** application is a microservices-based system consisting of four services and a database backend:

* **Product Page (Python):** The entry point for users, aggregating data from other services.
* **Reviews (Java):** Provides book reviews and star ratings.
* **Details (Ruby):** Provides specific information about the book.
* **Ratings (Node.js):** Manages the rating system, persisted in the database.
* **Database (MongoDB):** Stores the rating data.

---

## 🛠 DevSecOps Platform Layer

Our infrastructure is built on **GKE** with a high focus on security, ensuring all services are accessible via **HTTPS**.

### Security & Tooling Compliance
| Tool Name            | Function                                    | Architecture |
| :------------------- | :------------------------------------------ | :----------- |
| **Jenkins**          | CI/CD Orchestration                         | on K8S       |
| **Gitlab**           | Source Code Repository                      | on SaaS      |
| **Harbor**           | Container Image Registry                    | on K8S       |
| **Trivy**            | Container Image Security                    | on Pipeline  |
| **Dependency Check** | Software Composition Analysis (SCA)         | on Pipeline  |
| **SonarQube**        | Static Application Security Testing (SAST)  | on K8S       |
| **OWASP Zap**        | Dynamic Application Security Testing (DAST) | on Pipeline  |
| **KICS**             | Infrastructure as Code Security             | on Pipeline  |

---

## CI/CD Pipeline

The pipeline is designed with **Security Gates**:
1. **SCA & SAST:** Check dependencies and code quality using **Dependency Check** and **SonarQube**.
2. **Container Security:** Scan Docker images in **Harbor** using **Trivy**.
3. **IaC Security:** Validate Kubernetes manifests/Helm charts using **KICS**.
4. **Automated Deployment:** Deploy to GKE using **Helm** across Dev, UAT, and PRD.
5. **DAST:** Run dynamic security scans with **OWASP Zap** on the running environment.

---

## Deployment

### DevSecOps Tools
| Tool          | Access URL                                                         |
| :------------ | :----------------------------------------------------------------- |
| **Jenkins**   | [https://cicd-ice.opsta.in.th](https://cicd-ice.opsta.in.th)         |
| **Harbor**    | [https://registry-ice.opsta.in.th](https://registry-ice.opsta.in.th) |
| **SonarQube** | [https://sast-ice.opsta.in.th](https://sast-ice.opsta.in.th)         |

### Application Environments
| Environment    | URL                                                                        |
| :------------- | :------------------------------------------------------------------------- |
| **Production** | [https://bookinfo-ice.opsta.in.th](https://bookinfo-ice.opsta.in.th)         |
| **UAT**        | [https://bookinfo-ice-uat.opsta.in.th](https://bookinfo-ice-uat.opsta.in.th) |
| **Dev**        | [https://bookinfo-ice-dev.opsta.in.th](https://bookinfo-ice-dev.opsta.in.th) |

^ down server หมดแล้ว

Bootcamp นี้ทำเมื่อเดือน มีนาคม 2026  

Migrate มาจาก Gitlab อีกทีหนึ่ง