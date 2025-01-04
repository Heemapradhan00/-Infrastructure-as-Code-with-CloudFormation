Infrastructure-as-Code-with-CloudFormation

## **Resources Created**

1. **EC2 Instance**
   - A t2.micro EC2 instance is created using the Amazon Linux 2 AMI.
   - SSH access (Port 22) and HTTP access (Port 80) are allowed through the security group.

2. **S3 Bucket**
   - A new S3 bucket is created with the name `my-demo-bucket-cloudformation`.

3. **Security Group**
   - A security group is created to allow SSH (port 22) and HTTP (port 80) access to the EC2 instance.

---

## **Prerequisites**

1. An AWS account.  
   You can sign up for one [here](https://aws.amazon.com/).
   
2. AWS CLI installed (optional, but helpful for deploying stacks from the command line).  
   You can follow the installation instructions [here](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html).

3. A key pair to connect to your EC2 instance.  
   If you don't have one, create it in the **EC2 Dashboard** and download the `.pem` file.

---

## **How to Deploy the CloudFormation Stack**

### **Step 1: Prepare the Template**
1. Download the `infrastructure.yml` template file from this repository or create a new file on your local machine and paste the CloudFormation template.

### **Step 2: Deploy Using AWS CloudFormation Console**

1. Login to the [AWS Management Console](https://aws.amazon.com/console/).
2. Go to **CloudFormation** and click **Create Stack**.
3. Choose **Upload a template file**, then upload the `infrastructure.yml` template.
4. Follow the steps to create the stack, provide a stack name, and review the settings.
5. Click **Create Stack**.

### **Step 3: Verify Resources**

- **S3 Bucket**: After the stack is created, you can check the **S3 Console** for the bucket named `my-demo-bucket-cloudformation`.
- **EC2 Instance**: Go to the **EC2 Dashboard** to see your running EC2 instance.
- **Security Group**: Verify the security group in the **EC2 Dashboard** → **Security Groups**.

### **Step 4: Connect to the EC2 Instance**

1. Go to the **EC2 Dashboard** and copy the **Public IPv4 address** of your running instance.
2. Open your terminal and run the following SSH command (replace `<Public-IP>` with the actual IP address):
   ```bash
   ssh -i "my-key-pair.pem" ec2-user@<Public-IP>
   ```

### **Step 5: Clean Up**

1. After you're done, go back to **CloudFormation** and select the stack.
2. Click **Delete** to remove all resources (EC2 instance, S3 bucket, and security group).

---

## **Contributing**

Feel free to open a pull request if you want to improve or extend the template. Any contributions are welcome!

---

## **License**

This project is licensed under the MIT License.

```

---

### **Instructions for Uploading to GitHub**

1. Go to [GitHub](https://github.com/) and create a new repository (e.g., `aws-cloudformation-demo`).
2. Upload the `README.md` and `infrastructure.yml` files to the repository.
3. Add a brief description of the project and how to deploy it using CloudFormation in the **README.md**.

