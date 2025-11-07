# Deploy EC2 in AWS Lab

## Introduction to Amazon EC2

This lab demonstrates the process of deploying and managing an Amazon EC2 instance.
You can watch the demo of this lab here: [Deploy EC2 in AWS Lab](https://www.youtube.com/watch?v=4s5FQI4r9oE)



Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers.

Through Amazon EC2, users can deploy and manage virtual machines (VMs) on AWS infrastructure, including support for both **Microsoft Windows** and **Linux** environments.  
EC2 instances are categorized into various instance types, each offering different combinations of CPU, memory, storage, and networking capacity.

Amazon EC2 also provides flexible pricing models that allow users to pay only for the compute resources they use, making it an efficient and cost-effective solution for running applications in the cloud.

---

## Overview

### Topics Covered
- Launch a web server with termination protection enabled  
- Monitor EC2 instance  
- Modify the security group to allow HTTP access  
- Resize EC2 instance to scale  
- Test termination protection  
- Terminate EC2 instance  

---

## Task 1: Launching EC2 Instance

### Step 1: Open the Amazon EC2 Console
- In the AWS Management Console, choose **EC2** from the **Services** menu.

### Step 2: Launch an Instance
- From the **EC2 Dashboard**, select **Launch Instance**.

### Step 3: Naming Instance
- In the **Name and tags** pane, enter **Web Server** as the instance name.

### Step 4: Choosing an Amazon Machine Image (AMI)
- Select **Amazon Linux 2023 AMI**.

### Step 5: Choosing an Instance Type
- Choose **t3.micro** (2 vCPU, 1 GiB memory).

### Step 6: Configuring a Key Pair
- Select **Proceed without a key pair** (not recommended for production).

### Step 7: Configuring Network Settings
- For **VPC**, select **Lab VPC**.
- Configure the **Web Server Security Group** and remove existing inbound rules.

### Step 8: Adding Storage
- Select an **8 GiB** disk volume.

### Step 9: Configuring Advanced Details
- Enable **Termination Protection**.
- Enter a **User Data Script** to execute upon instance startup.

### Step 10: Launching the Instance
- Launch the instance and verify that both **Status Checks** have passed.

---

## Task 2: Monitor Instance
- Verify that **System reachability** and **Instance reachability** checks have passed.
- Capture a screenshot of the running instance for monitoring verification.

---

## Task 3: Update Security Group and Access the Web Server
- Add an **Inbound Rule**:
  - Type: HTTP  
  - Port: 80  
  - Source: Anywhere (IPv4)
- Open a web browser and access the **Public IPv4 Address**.  
  You should see the message:  
  **“Hello From Web Server!”**

---

## Task 4: Resize Instance (Instance Type and EBS Volume)

### Step 1: Stop Instance  
Before resizing, stop the instance.

### Step 2: Change Instance Type  
- Change from **t3.micro** to **t3.small** (2× memory).

### Step 3: Resize the EBS Volume  
- Increase root volume size from **8 GiB → 10 GiB**.

### Step 4: Start the Resized Instance  
- Start the instance again with the new configuration.

---

## Task 5: Test Termination Protection
- Attempt to terminate the instance — a red error message will appear:  
  **“Failed to terminate an instance: The instance may not be terminated.”**
- Disable termination protection, then terminate the instance.

---

## Conclusions

### Launching EC2 Instance
The launch instance wizard enables you to quickly create an EC2 instance with customizable parameters tailored for optimal performance.

### Monitoring Instance
AWS monitoring tools provide visibility into instance health and reachability for faster troubleshooting.

### Security Groups
Security groups act as firewalls, controlling inbound and outbound traffic for EC2 instances to enhance security.

### Resizing Instance
You can easily modify instance type, disk space, and network settings as compute requirements change.

### Termination Protection
This feature prevents accidental instance deletion, ensuring service stability and cost management.

---

## YouTube Presentation
🎥 Watch the lab demo here: [Deploy EC2 in AWS](https://www.youtube.com/watch?v=4s5FQI4r9oE)

🎥 Presentation of the theories behind the concepts covered in the lab. [Cloud Fondation](https://www.youtube.com)


---

## Repository Information
This repository contains the documentation and reference files for the practical lab.  

