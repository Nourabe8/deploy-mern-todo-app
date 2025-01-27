# MERN TODO List App - DevOps Edition

This is a fork and extension of the MERN TODO List App originally created by Atharva Kulkarni. And this project automates the deployment of a MERN (MongoDB, Express, React, Node.js) TODO List application using Jenkins, Docker Compose, Ansible, and Terraform. It simplifies the entire process, from provisioning the infrastructure to deploying the application, ensuring consistency and efficiency.

## **Features**

- Infrastructure provisioning using Terraform.
- Configuration management and deployment using Ansible.
- Application containerization using Docker Compose.
- Fully automated deployment pipeline with Jenkins.



## **Project Workflow**

1. **Provision Infrastructure**:

   - Use Terraform to create the virtual machine (VM) in Proxmox Virtual Environment for deployment.

2. **Automate Configuration**:

   - Use Ansible to install Docker, Git, configure the environment, and set up Jenkins on the VM.

3. **Continuous Integration/Continuous Deployment (CI/CD) Pipeline**:

   - Jenkins pulls the latest code from the GitHub repository.
   - Build Docker images for the frontend and backend locally on the target VM.
   - Deploy the application using Docker Compose.

## **Setup Instructions**

### **Prerequisites**

Before running this project, ensure you have the following installed:

- Terraform
- Ansible
- Jenkins
- Docker and Docker Compose
- Git

### **Steps to Deploy**

1. **Clone the Repository**:

   ```bash
   git clone <your-repository-url>
   cd <your-repository-folder>
   ```

2. **Provision Infrastructure**:

   - Use Terraform to create the target VM:
     ```bash
     terraform init
     terraform apply
     ```

3. **Configure the VM**:

   - Use Ansible to install necessary tools and configure the environment:
     ```bash
     ansible-playbook -i inventory install-tools.yml
     ```

4. **Run the CI/CD Pipeline**:

   - Access Jenkins and trigger the build job to:
     - Pull the latest code from GitHub.
     - Build Docker images locally for the frontend and backend.
     - Deploy the application using Docker Compose.

### **Access the Application**

Once the deployment is complete, access the application in your browser:

- **Frontend**: `http://<vm-ip>:3000`
- **Backend**: `http://<vm-ip>:5000`

## **Technologies Used**

- **Jenkins**: Automates the CI/CD pipeline.
- **Terraform**: Provisions infrastructure.
- **Ansible**: Manages configurations and automates deployments.
- **Docker Compose**: Orchestrates multi-container applications.
- **GitHub**: Hosts the application code.

## **License**

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

