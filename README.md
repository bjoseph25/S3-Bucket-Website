#  🌐 My S3 Bucket Static Website

This project hosts a static website using **Amazon S3 (Simple Storage Service)**. The website is publicly accessible and designed for high availability, scalability, and low latency.

## 📁 Bucket Details

**Bucket Name**: `your-bucket-name`
- **Region**: `your-region` (e.g., `us-east-1`)
- **Hosting Type**: Static website hosting
- **URL**: [http://your-bucket-name.s3-website-your-region.amazonaws.com](http://your-bucket-name.s3-website-your-region.amazonaws.com)
  
## 🛠 Features

- Fully static site (HTML, CSS, JS)
- Public-read access for website content
- Optional HTTPS via CloudFront
- Custom domain support (optional)

## 🚀 Getting Started

### 1. Set Up AWS CLI (if not already)

```bash
aws configure
```
```bash
aws s3 mb s3://your-bucket-name --region your-region
```

### Enable static website hosting
```bash
aws s3 website s3://your-bucket-name/ --index-document index.html --error-document error.html
```

### Make content public (use with caution)
```bash
aws s3api put-bucket-policy --bucket your-bucket-name --policy file://bucket-policy.json
```

### 2. Deploy Your Website
```bash
aws s3 sync ./public s3://your-bucket-name --acl public-read
```

