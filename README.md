# Angular Web App Deployment

Deployment of my personal portfolio website using AWS services, as part of my transition from systems administration to cloud infrastructure.

🌐 **Live website:** [diegosommier.com](https://diegosommier.com)

## 📖 Overview

This project covers the deployment of my personal portfolio, built with Angular and hosted on AWS.

The application is compiled into static files and stored in Amazon S3, with Amazon CloudFront delivering the website content. Amazon Route 53 manages DNS for the custom domain, and AWS Certificate Manager (ACM) provides the SSL/TLS certificate for HTTPS access.

## 🏗️ Architecture

![Angular Web App Deployment Architecture](assets/angular-web-app-deployment.png)

### Request Flow

1. A visitor accesses `diegosommier.com`.
2. Amazon Route 53 resolves the domain to the CloudFront distribution.
3. Amazon CloudFront delivers the website content over HTTPS.
4. The compiled Angular application files are stored in Amazon S3.

## ☁️ AWS Services

| Service | Purpose |
|---|---|
| **Amazon S3** | Stores the compiled Angular application files. |
| **Amazon CloudFront** | Distributes website content through AWS edge locations. |
| **Amazon Route 53** | Manages DNS records for the custom domain. |
| **AWS Certificate Manager (ACM)** | Provides the SSL/TLS certificate for HTTPS. |

## 🚀 Deployment & Troubleshooting

### Build

The Angular application is compiled into static production files before deployment.

```bash
npx ng build
```

The generated files are located in the `dist/` directory. Depending on the Angular build configuration, the deployable files may be inside a nested `browser/` directory.

### Deployment Process

1. Build the Angular application locally.
2. Upload the generated build files to Amazon S3.
3. Configure CloudFront to deliver the website content.
4. Configure the custom domain using Route 53.
5. Validate and configure the SSL/TLS certificate through ACM.
6. Verify that the website is accessible over HTTPS.

### CloudFront Cache Invalidation

After updating the website, the previous version continued to appear because CloudFront was serving cached content.

I resolved this by creating a CloudFront cache invalidation for the path:

```text
/*
```

This forced CloudFront to fetch the updated content rather than continue serving the previous cached version.

## 📚 Key Learnings

This project provided practical experience with:

- Hosting a static web application on AWS.
- Understanding how Amazon S3 and CloudFront work together.
- Configuring DNS for a custom domain with Route 53.
- Using AWS Certificate Manager to enable HTTPS.
- Understanding CDN caching and invalidation during deployments.

## 🎓 Training Context

This project was developed as part of the **Cloud Computing and DevOps Bootcamp by [BlockStellart](https://learn.blockstellart.com/bootcamp/)**.

It applies concepts covered during the training to the deployment of my personal portfolio website.

## 📖 References

- [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/)
- [Amazon CloudFront Documentation](https://docs.aws.amazon.com/cloudfront/)
- [Amazon Route 53 Documentation](https://docs.aws.amazon.com/route53/)
- [AWS Certificate Manager Documentation](https://docs.aws.amazon.com/acm/latest/userguide/acm-overview.html)
- [Angular Documentation](https://angular.dev/)
- [BlockStellart — Cloud Computing and DevOps Bootcamp](https://learn.blockstellart.com/bootcamp/)

---

**Author:** Diego Sommier  
**Focus:** Cloud Computing · AWS · Infrastructure  
**Year:** 2026
