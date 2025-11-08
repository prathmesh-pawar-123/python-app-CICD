# 🚀 Python Application CI/CD Pipeline Project

This project demonstrates a *Continuous Integration and Continuous Deployment (CI/CD)* pipeline for a Python web application using *Jenkins* and *GitHub* on *AWS EC2*.

---

## 📘 Project Overview

The goal of this project is to automate the deployment process of a Python application using a Jenkins pipeline.  
Whenever new code is pushed to GitHub, Jenkins automatically builds, tests, and deploys the app on an EC2 instance.

---

## ⚙ Tools and Technologies Used

- *Python* – Application backend
- *GitHub* – Source code management
- *Jenkins* – CI/CD automation tool
- *AWS EC2* – Deployment server
- *Webhooks* – For GitHub-Jenkins integration

---

## 🧩 CI/CD Pipeline Flow

1. *Launch EC2 Instance*  
   Configure and install Jenkins on the EC2 instance.  
 -  choose ubuntu server,
  - select instance type (e.g.,t2.micro),
  - create a key pair and download it,
  -  Allow inbound ports:
    8080 for jenkins,
    5000 for python,
   - connect to EC2 using SSH:
    ssh -i your-key-pem ubuntu@ec2-public-ip
   - - sudo apt update
   - - sudo apt install openjdk-11-jdk -y
   - - sudo apt install jenkins -y
   - - sudo systemctl start jenkins
   - - sudo systemctl enable jenkins
    

   ![] (./img/![alt text](<img/Screenshot (7).png>))

2. *Create GitHub Repository* 
 -create a new repository on github (e.g python-app-CICD)
  - Push your Python application code to a GitHub repository. 

 - - git init
 - - git add .
- - git commit -m "Initial commit"
- -  git remote add origin https://github.com/your-username/python-app-cicd.git
- - git push -u origin main 

   ![] (./img/![alt text](<img/Screenshot (8).png>))

3. *Create New Item in Jenkins*  
   Create a new Jenkins pipeline job and connect it to your GitHub repo.
- - Open jenkins dashboard - Click on "New item".
- - Enter a project name - python-app-CICD.
- - In pipeline configuration,select pipeline script from SCM.
- - choose Git,and paste your repository URL.
- - Add branch name as main.
- - save the configuration and click Build now.          
   ![] (./img/![alt text](<img/Screenshot (9).png>))
   ![] (./img/![alt text](<img/Screenshot (10).png>))

4. *Successful Build and Deployment*  
   Jenkins automatically builds and deploys the application after every push.
   - - pull the latest code from Github.
   - - Build and test python application.
   - - Deploy the app on your EC2 instance
   - - you can monitor each stage in jenkins console output.  
   ![] (./img/![alt text](<img/Screenshot (11).png>))
   ![] (./img/![alt text](<img/Screenshot (12).png>))

5. *Final Output on Browser*  
   The Python application runs successfully on the browser after deployment.
- - you should see your python web app running successfully.  
   ![] (./img/![alt text](<img/Screenshot (13).png>))

---

## 🧠 Key Learnings

- How to connect *GitHub Webhooks* with *Jenkins*
- Automating build and deployment using *Jenkinsfile*
- Setting up a *Python app* on an *EC2 instance*
- Managing continuous integration and delivery pipelines

---

## 📄 Author

*Prathmesh Pawar*  
💼 DevOps | Cloud | Python Enthusiast  
🔗 [GitHub Profile](https://github.com/prathmesh-pawar-123)

---

## 🏁 Conclusion

This project helped me understand real-time CI/CD workflow and automation using Jenkins, GitHub, and AWS.  
It ensures faster development cycles and reliable deployments.

