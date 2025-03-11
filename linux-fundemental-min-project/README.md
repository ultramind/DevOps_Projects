# AWS EC2 Installation and Connection Guide

This guide provides a step-by-step walkthrough for setting up an Amazon EC2 instance and connecting it to your local system.

## Prerequisites

1. **AWS Account**: Ensure you have an active AWS account.
2. **SSH Client**: Install an SSH client (e.g., OpenSSH, PuTTY) on your local machine.
3. **IAM Permissions**: Ensure you have the required permissions to create and manage EC2 instances.

---

## Step 1: Log in to the AWS Management Console

1. Navigate to the [AWS Management Console](https://aws.amazon.com/console/).
2. Log in with your AWS credentials.

---

## Step 2: Launch an EC2 Instance

1. In the AWS Management Console, search for "EC2" in the search bar and select **EC2** under "Services."
2. Click on the **Launch Instance** button.
3. Configure the following settings:
   - **Name and Tags**: Enter a name for your instance (e.g., "MyEC2Instance").
   - **Amazon Machine Image (AMI)**: Select an appropriate AMI (e.g., Amazon Linux 2 or Ubuntu).
   - **Instance Type**: Choose an instance type (e.g., `t2.micro` for free-tier eligibility).
   - **Key Pair**: Create a new key pair or select an existing one (download the `.pem` file if creating a new key pair).
   - **Network Settings**: Configure the security group to allow SSH (port 22).
   - **Storage**: Adjust the storage settings if needed.

4. Click **Launch Instance** and wait for the instance to start.

---

## Step 3: Retrieve the Public IP Address

1. In the EC2 dashboard, navigate to the "Instances" section.
2. Locate your instance and copy the **Public IPv4 address**.

---

## Step 4: Configure Local System for SSH Access

### For Linux/Mac:

1. Open a terminal.
2. Navigate to the directory where your key pair (`.pem` file) is located.
3. Run the following command to set permissions for the key file:
   ```bash
   chmod 400 your-key-name.pem
   ```

### For Windows:

1. If using PuTTY, convert the `.pem` file to a `.ppk` file using PuTTYgen.
2. Open PuTTY and configure the following:
   - **Host Name**: Enter `ec2-user@<Public-IP>` (replace `<Public-IP>` with the instance's public IP address).
   - **SSH Authentication**: Load the `.ppk` file under "SSH > Auth."

---

## Step 5: Connect to the EC2 Instance

### Using SSH (Linux/Mac):

1. Run the following command:
   ```bash
   ssh -i your-key-name.pem ec2-user@<Public-IP>
   ```
   - Replace `your-key-name.pem` with the name of your key file.
   - Replace `<Public-IP>` with the instance's public IP address.

2. If prompted, type "yes" to continue connecting.

### Using PuTTY (Windows):

1. Click **Open** in PuTTY to initiate the connection.
2. Log in with the default username for your AMI (e.g., `ec2-user` for Amazon Linux 2).

---

## Step 6: Verify the Connection

1. Once connected, you should see the terminal of your EC2 instance.
2. Test basic commands like `ls`, `pwd`, or `uname -a` to verify the environment.

---

## Troubleshooting

- **Connection Timeout**: Ensure that the security group allows inbound SSH traffic on port 22.
- **Permission Denied**: Verify that the key file permissions are correct and that you are using the correct username for the AMI.
- **Public IP Not Accessible**: Ensure the instance is in a public subnet and has an associated Elastic IP if necessary.

---

You have now successfully set up and connected to an EC2 instance from your local system. Happy coding!

