
# **Java CI/CD Pipeline with Jenkins, Docker, and Ansible** 🚀  

## **📌 Overview**  
This project automates the **CI/CD pipeline** for deploying a Java-based web application using **Jenkins**, **Docker**, and **Ansible**. The pipeline performs the following tasks:  
- **Pulls source code** from GitHub  
- **Builds a WAR file** using Maven  
- **Transfers the WAR file** to a remote server  
- **Deploys the application** using Docker  
- **Executes Ansible Playbook** for further setup  

---

## **🛠️ Tech Stack**  
- **Backend:** Java (Spring Boot)  
- **Build Tool:** Maven  
- **CI/CD Tool:** Jenkins  
- **Containerization:** Docker  
- **Configuration Management:** Ansible  
- **Cloud:** AWS EC2  

---

## **📂 Project Structure**  
```
📦 project-name
 ┣ 📂 src                 # Java application source code
 ┣ 📜 Dockerfile          # Docker configuration file
 ┣ 📜 Jenkinsfile         # Jenkins pipeline script
 ┣ 📜 ansible.yml         # Ansible playbook
 ┣ 📜 README.md           # Project documentation
 ┣ 📜 pom.xml             # Maven build configuration
 ┣ 📜 marcos.war          # Built WAR file
 ┗ 📜 application.properties  # Database & app configuration
```

---

## **🚀 Prerequisites**  
Before running the pipeline, ensure you have:  
✅ **Java 17+** installed  
✅ **Maven** installed (`mvn -version` to check)  
✅ **Docker** installed (`docker -v` to check)  
✅ **Jenkins** installed & running (`http://localhost:8080`)  
✅ **AWS EC2 instance** with SSH access  
✅ **DockerHub account** to push images  
✅ **Ansible installed** on the target server  

---

## **📝 Jenkins Pipeline (Jenkinsfile)**  
This pipeline performs the following:  
1. **Pulls the source code** from GitHub  
2. **Builds a WAR file** using Maven  
3. **Transfers the WAR file** to a remote EC2 instance  
4. **Builds & pushes** a Docker image  
5. **Runs Ansible Playbook** to configure the server  

---

## **🚀 Deploying to AWS EC2**  

### **1️⃣ Connect to EC2**  
```bash
ssh -i your-key.pem ec2-user@your-ec2-public-ip
```

### **2️⃣ Pull & Run Docker Image**  
```bash
docker pull your-dockerhub-username/portfolio
docker run -d --name tomcat -p 8081:8080 your-dockerhub-username/portfolio
```

### **3️⃣ Run Ansible Playbook** (If not automated in Jenkins)  
```bash
ansible-playbook ansible.yml
```



---

## **💡 Troubleshooting**  

### **🔴 Jenkins Pipeline Fails?**  
1️⃣ Check logs under **Jenkins → Console Output**  
2️⃣ Ensure Docker is installed & running on Jenkins  
3️⃣ Check if credentials are correctly set in Jenkins  

### **🔴 Deployment Issues?**  
1️⃣ Ensure **EC2 instance has Docker installed**  
```bash
docker -v
```
2️⃣ Check if the correct Docker image is pulled  
```bash
docker images
```
3️⃣ Ensure the app container is running  
```bash
docker ps -a
```

---

## **📝 To-Do**  
- [ ] Add unit tests with **JUnit**  
- [ ] Implement **rollback mechanism** for failed deployments  
- [ ] Automate **database migration**  

---

## **📜 License**  
This project is **MIT licensed**.  

---

### 🎯 **Contributing**  
Feel free to contribute! Open a pull request or report issues.  

---

### **🌍 Contact**  
📧 Email: revanthagastya12345@gmail.com 
🌐 GitHub: [your-username](https://github.com/Revanth-1707)  
🚀 Deployed App: [EC2-Public-IP:8080](http://your-ec2-public-ip:8081)  
=
