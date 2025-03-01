# S3-Static-Website-Hosting-Setup


# S3 Static Website Hosting

This project demonstrates how to configure and host a static website using AWS S3. The website consists of static files (HTML, CSS, JS) and is publicly accessible.

## Project Structure
- **index.html**: The landing page of the website.
- **error.html**: A custom error page shown when an invalid page is accessed (optional).
- **assets/**: Folder containing CSS, JavaScript, and image files for the website.
- **s3-configuration/**: AWS-specific configuration files, including S3 bucket policies and website hosting configuration.

## Setup Instructions

### 1. Create an S3 Bucket
- Name the bucket the same as your website domain name (e.g., `example.com`).
- Choose a region for your bucket.

### 2. Enable Static Website Hosting on S3
- In the S3 console, enable "Static website hosting" and set `index.html` as the index document.
- Optionally, set `error.html` as the error document.

### 3. Upload Static Files
- Upload all static website files (HTML, CSS, JS, images) to the S3 bucket.
- Ensure all files are publicly accessible via a bucket policy.

### 4. Configure Permissions (Bucket Policy)
- Use the following bucket policy to allow public access to the files:
  
  ```json
  {
      "Version": "2012-10-17",
      "Statement": [
          {
              "Sid": "PublicReadGetObject",
              "Effect": "Allow",
              "Action": "s3:GetObject",
              "Resource": "arn:aws:s3:::example.com/*"
          }
      ]
  }
