# Static Website Hosting on AWS S3 using Terraform  

This project automates the deployment of a static website on AWS S3 using Terraform. The infrastructure is fully automated, allowing seamless hosting and management of the static website.

## 🚀 Project Overview  
- **Goal**: Host a static website on AWS S3 with automated provisioning using Terraform.  
- **Technology Stack**:  
  - **Terraform** – Infrastructure as Code (IaC)  
  - **AWS S3** – Static website hosting  
  - **AWS Route 53** (Optional) – For custom domain routing  

---

## 📂 Project Structure  
```
├── .terraform/              # Terraform provider plugins (ignored by .gitignore)  
├── terraform/  
│   ├── main.tf              # Main Terraform configuration  
│   ├── variables.tf         # Variable definitions  
│   ├── outputs.tf           # Output values  
│   └── s3.tf                # S3 bucket and policy configuration  
├── website/  
│   ├── index.html           # Main HTML page  
│   ├── styles.css           # CSS for styling  
│   └── assets/              # Images, JS files, etc.  
└── README.md                # Project documentation  
```

---

## 📋 Prerequisites  
Ensure the following are installed:  
- **Terraform** (v1.5.0 or higher) – [Install Terraform](https://developer.hashicorp.com/terraform/downloads)  
- **AWS CLI** – [Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)  
- AWS Account with **S3 and IAM permissions**  

---

## ⚙️ Terraform Setup  
1. **Clone the repository**:  
   ```bash
   git clone https://github.com/keerthana1106gsk/MY_TERRAFORM-projects.git
   cd MY_TERRAFORM-projects
   ```  

2. **Initialize Terraform**:  
   ```bash
   terraform init
   ```  

3. **Review and customize** the `variables.tf` file to match your configuration.  

4. **Validate the configuration**:  
   ```bash
   terraform validate
   ```  

5. **Apply the Terraform plan**:  
   ```bash
   terraform apply
   ```  
   - Confirm the changes by typing `yes` when prompted.  

---

## 🌐 Upload and Deploy Website  
1. **Upload the static website files** (HTML/CSS/JS) to the S3 bucket:  
   ```bash
   aws s3 cp ./website s3://<YOUR_BUCKET_NAME>/ --recursive
   ```  

2. **Enable public access** to the S3 bucket (Terraform automates this).  

3. **Access the website**:  
   - Find the S3 website endpoint in the Terraform outputs or AWS console.  
   - Open the URL in your browser.  

---

## 🎯 Outputs  
After deployment, the following information will be provided:  
- **Website URL**: Public S3 bucket URL for the website.  
- **Bucket Name**: Name of the created S3 bucket.  

---

## 🔄 Managing Changes  
- To update the website, modify files in the `/website` directory and re-upload to S3:  
   ```bash
   aws s3 cp ./website s3://<YOUR_BUCKET_NAME>/ --recursive
   ```  
- To **destroy** the infrastructure:  
   ```bash
   terraform destroy
   ```  

---

## 🛡️ Security  
- The S3 bucket policy allows public read access only to website files.  
- Sensitive data should not be stored in the public bucket.  

---

## 🛠️ Troubleshooting  
- **403 Forbidden** – Ensure S3 bucket policies allow public read access.  
- **Website not loading** – Confirm that `index.html` exists at the root level.  

---

## 👩‍💻 Author  
**Sree Keerthana G**  
- **Email**: [gsreekeerthana001@gmail.com]  
- **GitHub**: [keerthana1106gsk](https://github.com/keerthana1106gsk)  
