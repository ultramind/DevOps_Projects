# Security-and-NACL

## 1. Project Overview
This project explores the configuration and implications of Security Groups and Network Access Control Lists (NACLs) in a cloud environment. The objective is to understand how inbound and outbound rules affect network traffic and security in AWS.

## 2. Objectives
- Learn how to create and configure Security Groups and NACLs.
- Analyze the effect of different security settings on access control.
- Test security rules by modifying inbound and outbound settings.
- Ensure secure communication between instances while maintaining necessary accessibility.

## 3. Purpose
The purpose of this project is to enhance understanding of cloud security mechanisms by implementing and testing Security Groups and NACLs. This will help in securing cloud applications and ensuring proper network traffic flow.

## 4. Requirements
- AWS Account with administrative access.
- Basic knowledge of cloud networking and security.
- An EC2 instance for testing.
- Access to AWS Management Console or AWS CLI.

## 5. Use Case
This project is applicable in scenarios where organizations need to regulate access to cloud-based services while maintaining security. For example, an e-commerce application may require open access to users but restrict unauthorized internal communication.

## 6. Performance Goals
- Successfully configure Security Groups and NACLs.
- Demonstrate how changes in security rules impact accessibility.
- Achieve secure yet functional access to cloud-based applications.
- Document troubleshooting steps for resolving security-related issues.

---


# Security-and-NACL

## 7. Project Steps and Commands

### 7.1. Go to Subnet Page

- **Create subnet**  
  ![Create subnet](https://github.com/user-attachments/assets/c72dc682-7dea-4940-9042-758f9c2eca96)

- **Enter the details**  
  ![Enter the infos](https://github.com/user-attachments/assets/9590de1d-f4aa-495b-a01f-72a72329f5d9)

- **Set your inbound rules**  
  ![Set your inbound rules](https://github.com/user-attachments/assets/83c944ea-074d-4479-a317-bb9556125c96)

- **Set your outbound rules**  
  ![Set your outbound rules](https://github.com/user-attachments/assets/cb225703-b8fe-41fd-8b30-8bf3f7c3932b)

- **Created security group**  
  ![Created security group](https://github.com/user-attachments/assets/c2f75d23-4b55-48e1-8eef-a5f6c4a89f14)

### 7.2. Go to Instance

- **Go to your Instance section**  
  ![Instance section](https://github.com/user-attachments/assets/be7e17cc-f1f8-4f3e-ae36-dd33724f5e1b)

- **Go to change security groups**  
  ![Change security groups](https://github.com/user-attachments/assets/c3b2d3e9-3e9b-4905-ae20-08bf9d1caca7)

- **Select your security group and save**  
  ![Select security group](https://github.com/user-attachments/assets/e0e66897-f901-4d2c-b321-c4c92dba45ed)

- **You can navigate to the open address of the instance on your web browser**  
  ![Instance browser access](https://github.com/user-attachments/assets/f9102332-0ef1-49a5-a79d-58923dbea847)

## 7.3 Testing Implications of Security Group Rules

### 7.4. Remove the Outbound Rule and Save

- **Deleting the outbound rule**  
  ![Delete outbound rule](https://github.com/user-attachments/assets/6df80520-753d-43ed-8c13-0c31913aa08b)

- **Absence of outbound rules still has no effect on traffic from instance to the outside**  
  ![Traffic unaffected](https://github.com/user-attachments/assets/9a25cc4f-7b41-4242-8f51-cefd8aa7457e)

### 7.5. Remove the Inbound Rule and Save

- **Deleting inbound rule**  
  ![Delete inbound rule](https://github.com/user-attachments/assets/84c5f198-047a-447c-88fb-c104d203c5b5)

- **Attempt to access instance via browser**  
  ![No access](https://github.com/user-attachments/assets/f425eb88-767c-470d-95db-d31a2829eb78)

### 7.6. Allow HTTP on Outbound Rule

- **Adding HTTP to outbound rule**  
  ![Add HTTP](https://github.com/user-attachments/assets/c8e416b3-d381-4a18-bfd2-8995f6f09b01)

- **No inbound rules present**  
  ![No inbound rules](https://github.com/user-attachments/assets/d0d777e3-075c-4db8-95d6-6ff598975a09)

- **Attempt to access instance via browser (still no access)**  
  ![Still no access](https://github.com/user-attachments/assets/f425eb88-767c-470d-95db-d31a2829eb78)

## 7.7 Testing Implications of NACL Rules

- **Creating a Network ACL**  
  ![Create NACL](https://github.com/user-attachments/assets/1c99b24c-d764-4210-9e81-eaba1e3cbd59)

- **Modify outbound rules**  
  ![Modify outbound rules](https://github.com/user-attachments/assets/68592e65-b278-4d5a-9200-3ac5ad1962eb)

- **Modify inbound rules**  
  ![Modify inbound rules](https://github.com/user-attachments/assets/2e149294-1240-4602-80e2-06c9598aa626)

- **Go to the outbound rules**  
  ![Outbound rules](https://github.com/user-attachments/assets/0d6113b4-a461-4841-8791-d9ba2922a87a)

- **Make changes to the inbound rules and save**  
  ![Edit inbound rules](https://github.com/user-attachments/assets/ee29fa7d-666f-4c35-a54b-5e5609184686)

- **Go to actions and click on subnet associations**  
  ![Subnet associations](https://github.com/user-attachments/assets/988df6de-f4ee-47cd-957b-748d5621c9ad)

- **Select the subnet and save**  
  ![Select subnet](https://github.com/user-attachments/assets/6d1b8875-7496-4add-a27b-7d3383fe1c7f)

- **Test access to the instance (still no access due to outbound rules blocking traffic)**  
  ![No access](https://github.com/user-attachments/assets/2ec9c444-39e0-4112-9133-d95c860af62e)

- **Modify outbound rules**  
  ![Modify outbound rules](https://github.com/user-attachments/assets/933721e7-d793-4ec4-bb15-e30cd3ad4cbd)

- **Add rule and save**  
  ![Add rule](https://github.com/user-attachments/assets/1d85fca2-f2ea-4e25-99d0-b3e1b14eca8b)

- **Add the same rule for inbound**  
  ![Add inbound rule](https://github.com/user-attachments/assets/ea46c93b-7e05-4b40-9aa2-aabd763fff82)

- **You should now be able to access your site**  
  ![Access granted](https://github.com/user-attachments/assets/aa4b6e83-1326-4159-a4de-c9bf66c132a5)

## 7.8. Testing Implications of Both NACL and Security Group Rules

- **Go to your security group and set the inbound rules**  
  ![Set inbound security group rules](https://github.com/user-attachments/assets/5428e542-fe7d-43d3-ad2f-68524b3920f0)

- **Set your outbound rules in the security group**  
  ![Set outbound security group rules](https://github.com/user-attachments/assets/9537894c-9782-4e0a-89ab-9578ce67085a)

- **Go to NACL and set rules for both inbound and outbound**  

  **For inbound:**  
  ![Inbound NACL rules](https://github.com/user-attachments/assets/c321bfa7-faaa-453d-97bc-93d24542986c)

  **For outbound:**  
  ![Outbound NACL rules](https://github.com/user-attachments/assets/d603cd9a-6f67-4667-a4db-f0dbadd40c98)

- **Try to access the site, it is still inaccessible**  
  ![Still inaccessible](https://github.com/user-attachments/assets/8e13b5d1-70fd-4871-85af-c32beccffff4)

  




## 8. Troubleshooting (Common Issues and Solutions)

### 8.1. Trying to ensure the server was accessible
**Issue:** Could not get access to the server.
**Solution:**
- Ensure an Internet Gateway is attached.
- Verify route tables include a route to `0.0.0.0/0` via the Internet Gateway.

### 8.2. Subnet Routing Issues
**Issue:** Private instances are not communicating with public instances.
**Solution:**
- Confirm that the route table for private subnets has a NAT Gateway route.
- Ensure the correct subnet associations are applied.

### 8.3. Security Group Misconfigurations
**Issue:** The instance is not reachable over the expected ports.
**Solution:**
- Ensure the security group allows inbound traffic on required ports (e.g., 22 for SSH, 80 for HTTP, 443 for HTTPS).
- Check if outbound rules are restricting responses.

### 8.4. NACL Blocking Traffic
**Issue:** Some traffic is being blocked despite security group settings.
**Solution:**
- Verify that the NACL associated with the subnet allows inbound and outbound traffic for the required ports.
- Ensure there are no DENY rules overriding allow rules.

### 8.5. Instance Connectivity Issues
**Issue:** The instance is unable to connect to external services.
**Solution:**
- If using a private subnet, ensure there is a NAT Gateway for outbound internet access.
- Check the default route in the route table.

---

