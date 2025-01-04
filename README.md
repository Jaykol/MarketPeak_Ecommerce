# MarketPeak E-commerce Platform

## Project Overview
MarketPeak is an e-commerce platform featuring product listings, shopping cart functionality, and user authentication. This project demonstrates the deployment of a web application using Git version control and AWS cloud infrastructure.

## Features
- Product listings and catalog management
- Shopping cart functionality
- User authentication
- Responsive web design
- Cloud-based deployment

## Technical Stack
- Version Control: Git
- Web Server: Apache HTTP Server (httpd)
- Hosting: AWS EC2
- Operating System: Amazon Linux
- Development Environment: Linux
- Deployment: SSH/HTTPS-based deployment

## Prerequisites
- Git installed locally
- AWS account with EC2 access
- Basic understanding of Linux commands
- SSH key pair for secure deployment

## Installation & Setup

### 1. Local Development Setup
```bash
# Clone the repository
git clone https://github.com/your-username/MarketPeak_Ecommerce.git

# Navigate to project directory
cd MarketPeak_Ecommerce

# Set up Git configuration
git config --global user.name "YourUsername"
git config --global user.email "youremail@example.com"
```

### 2. AWS Deployment Steps

#### 2.1. Set Up EC2 Instance
1. Log in to AWS Management Console
2. Launch an EC2 instance using Amazon Linux AMI
3. Connect to the instance using SSH

#### 2.2. Clone Repository
Choose either SSH or HTTPS method:

SSH Method:
```bash
# Generate SSH keypair
ssh-keygen
# Add the SSH public key to GitHub account
# Clone using SSH
git clone git@github.com:yourusername/MarketPeak_Ecommerce.git
```

HTTPS Method:
```bash
# Clone using HTTPS
git clone https://github.com/yourusername/MarketPeak_Ecommerce.git
```

#### 2.3. Install and Configure Web Server
```bash
# Update system packages
sudo yum update -y

# Install Apache web server
sudo yum install httpd -y

# Start and enable Apache
sudo systemctl start httpd
sudo systemctl enable httpd

# Prepare web directory
sudo rm -rf /var/www/html/*
sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/

# Reload Apache configuration
sudo systemctl reload httpd
```

## Continuous Integration and Deployment Workflow

### Step 1: Development Process
1. Create development branch:
```bash
git branch development
git checkout development
```
2. Implement new features or fixes
3. Stage and commit changes:
```bash
git add .
git commit -m "Add new features or fix bugs"
```

### Step 2: Version Control
1. Push changes to development branch:
```bash
git push origin development
```

### Step 3: Code Review and Merging
1. Create Pull Request (PR) on GitHub
2. Review changes
3. Merge to main branch:
```bash
git checkout main
git merge development
```
4. Push merged changes:
```bash
git push origin main
```

### Step 4: Production Deployment
1. SSH into EC2 instance
2. Pull latest changes:
```bash
git pull origin main
```
3. Restart web server if necessary:
```bash
sudo systemctl reload httpd
```

### Step 5: Testing
- Access the website using EC2 instance's public IP
- Verify new features and fixes
- Test functionality in live environment

## Project Structure
```
MarketPeak_Ecommerce/
├── assets/
│   ├── css/
│   ├── js/
│   └── images/
├── templates/
├── config/
└── README.md
```

## Contributing
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Security Considerations
- Keep AWS credentials secure
- Regularly update dependencies
- Use HTTPS for production deployment
- Implement proper authentication mechanisms
- Regular security audits


Project on usage of git and deployment of a website.
I created a git repository,
cloned the repository,
performed git add, git commit, git --config and git push to the repository.
created a git branch for development and performed a pull request and merge on the git repository.
I created an EC2 instance to deploy and host the website on AWS and also updated the website on AWS server.
