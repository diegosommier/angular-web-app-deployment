# Angular Web App Deployment

> A personal portfolio web application built with Angular and deployed on AWS using Amazon S3 and Amazon CloudFront.

## 📖 Overview

This project focuses on building and deploying a personal portfolio website using Angular and AWS cloud services.

The application showcases my professional background, systems administration experience and ongoing transition toward Cloud infrastructure and architecture.

The main objective was to deploy a working web application using cloud infrastructure, moving from local development to a publicly accessible website delivered through Amazon CloudFront.

The project combines frontend development with cloud deployment, content delivery, HTTPS configuration and cache management.

## 🏗️ Architecture

The application is built with Angular and deployed as a static web application.

The architecture uses Amazon S3 to store the compiled application files and Amazon CloudFront to distribute the content to visitors.

The deployment follows this request flow:

```text
User
  │
  ▼
Amazon CloudFront
  │
  ▼
Amazon S3
  │
  └── Angular Production Build
       ├── HTML
       ├── JavaScript
       ├── CSS
       └── Static Assets
```

Angular handles the application build process, generating the static files required for deployment.

Amazon CloudFront serves the application over HTTPS and retrieves its content from the S3 origin.

## 🔧 Infrastructure & Implementation

### Angular Application

The portfolio was developed using Angular and TypeScript, with HTML, CSS and JavaScript supporting the frontend.

The application is developed and tested locally before generating a production build.

Angular CLI is used to compile the application and generate the deployment-ready files.

### Amazon S3

Amazon S3 is used to store the compiled frontend application.

The production build is uploaded to the bucket, preserving the directory structure and ensuring that `index.html` and its referenced assets are available to CloudFront.

This approach separates application development from the infrastructure used to serve the website.

### Amazon CloudFront

Amazon CloudFront distributes the application content through a content delivery network.

The distribution provides HTTPS access and caching for the website's static resources.

CloudFront cache invalidation is used when necessary after deploying updates, ensuring that visitors receive the latest version of the application.

### Deployment Workflow

The deployment process consists of several stages:

1. Developing and testing the application locally.
2. Generating the Angular production build.
3. Uploading the compiled files to Amazon S3.
4. Serving the application through Amazon CloudFront.
5. Invalidating cached content when required after updates.

The workflow demonstrates the relationship between frontend compilation, cloud storage and content delivery.

## 🛠️ Technologies & Tools

| Area | Technologies |
|---|---|
| Frontend Framework | Angular |
| Programming Language | TypeScript |
| Web Technologies | HTML, CSS, JavaScript |
| Cloud Storage | Amazon S3 |
| Content Delivery | Amazon CloudFront |
| HTTPS & Certificates | AWS Certificate Manager (ACM) |
| DNS Management | Amazon Route 53 |
| Version Control | Git, GitHub |

## 📚 Documentation

The README documents the application architecture, technologies used and deployment workflow.

The repository also provides the application source code required to understand how the portfolio is built and prepared for deployment.

Additional architecture diagrams and deployment documentation can be maintained in the `docs/` directory.

## ⚠️ Project Context

This is a personal project developed to gain practical experience with Angular and AWS cloud infrastructure.

The application serves as a portfolio website while providing an opportunity to work with production builds, object storage, content delivery and deployment updates.

The project focuses on learning and demonstrating cloud deployment concepts rather than implementing a complex application backend.

## From Systems Administration to Cloud

This project represents a step in my transition from traditional systems administration toward Cloud infrastructure and architecture.

My previous experience with operating systems, infrastructure management, troubleshooting and enterprise environments provides the foundation for understanding the operational aspects of cloud services.

Deploying this application introduced practical experience with AWS hosting, content delivery, HTTPS and cache management, extending that foundation into cloud-based infrastructure.

It also provides a starting point for future improvements involving deployment automation and CI/CD.

---

Year: 2026 · Focus: Cloud Infrastructure · AWS · Angular · Amazon S3 · Amazon CloudFront · Web Application Deployment
