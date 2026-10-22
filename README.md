# Angular Web App Deployment

> A personal portfolio web application built with Angular and deployed on AWS using Amazon S3 and Amazon CloudFront.

🌐 **Live Website:** [https://diegosommier.com](https://diegosommier.com)

## 📖 Overview

This project focuses on building and deploying a personal portfolio website using Angular and AWS cloud services.

The application showcases my professional background, systems administration experience and ongoing transition toward Cloud infrastructure and architecture.

The main objective was to deploy a working web application from local development to a publicly accessible website, using AWS services for storage, content delivery, DNS resolution and HTTPS.

The project combines frontend development with cloud deployment, content delivery, certificate management and cache invalidation.

## 🏗️ Architecture

The application is built with Angular and deployed as a static web application. Amazon S3 stores the compiled application files, while Amazon CloudFront distributes the content to visitors.

![Angular Web App Deployment Architecture](assets/angular-web-app-deployment.png)

### Architecture Components

- **Amazon Route 53:** Resolves the custom domain `diegosommier.com` to the CloudFront distribution.
- **Amazon CloudFront:** Acts as the content delivery layer, handling HTTPS requests and caching static assets.
- **AWS Certificate Manager (ACM):** Provides the SSL/TLS certificate associated with CloudFront.
- **Amazon S3:** Stores the compiled Angular production build and serves as the CloudFront origin.
- **Angular:** Provides the frontend application, compiled into static HTML, JavaScript, CSS and other assets.

### Request Flow

1. The user accesses `https://diegosommier.com`.
2. Amazon Route 53 resolves the domain name to the CloudFront distribution.
3. Amazon CloudFront receives the HTTPS request using the associated certificate managed through ACM.
4. If the requested content is not available in the CloudFront cache, CloudFront retrieves it from the Amazon S3 origin.
5. CloudFront delivers the application content to the user over HTTPS.

## 🔧 Infrastructure & Implementation

### Angular Application

The portfolio was developed using Angular and TypeScript, with HTML, CSS and JavaScript supporting the frontend.

The application is developed and tested locally before generating a production build using Angular CLI.

The build process compiles the application and generates the static files required for deployment.

### Amazon S3

Amazon S3 is used to store the compiled frontend application.

The production build is uploaded to the bucket, preserving the directory structure and ensuring that `index.html` and its referenced assets are available to CloudFront.

This separates the application source code from the files served in the deployed environment.

### Amazon CloudFront

Amazon CloudFront distributes the website content through a content delivery network.

The distribution provides HTTPS delivery and caching for static resources.

CloudFront cache invalidations are used when necessary after updates to ensure that the latest version of the website is served.

### DNS & HTTPS

Amazon Route 53 manages DNS resolution for the custom domain, while AWS Certificate Manager provides the TLS certificate used by CloudFront.

This enables access to the portfolio through its custom domain over HTTPS.

## 🛠️ Technologies & Tools

| Area | Technologies |
|---|---|
| Frontend Framework | Angular |
| Programming Language | TypeScript |
| Web Technologies | HTML, CSS, JavaScript |
| Cloud Storage | Amazon S3 |
| Content Delivery Network | Amazon CloudFront |
| DNS Management | Amazon Route 53 |
| Certificate Management | AWS Certificate Manager (ACM) |
| Version Control | Git, GitHub |

## 🚀 Deployment

The deployment workflow consists of the following steps:

1. Developing and testing the application locally.
2. Generating the Angular production build.
3. Uploading the compiled output to Amazon S3.
4. Serving the application through Amazon CloudFront.
5. Invalidating cached content when required after updates.

### Build the Application

Install the project dependencies:

```bash
npm install
```

Start the local development server:

```bash
npx ng serve
```

Generate the production build:

```bash
npx ng build
```

Angular generates the production files in the configured output directory under `dist/`.

Only the compiled output is deployed to Amazon S3, rather than the original TypeScript source files.

## 📚 Documentation

The repository includes the Angular application source code, this README and the architecture diagram located at `assets/architecture-diagram.png`.

The diagram provides a visual overview of the AWS services involved and their relationships within the deployment architecture.

## ⚠️ Project Context

This is a personal project developed to gain practical experience with Angular and AWS cloud infrastructure.

It provides hands-on experience with frontend production builds, cloud storage, content delivery, DNS resolution, HTTPS and deployment updates.

The project is intended as a learning and demonstration environment rather than a business-critical application architecture.

## From Systems Administration to Cloud

This project represents a step in my transition from traditional systems administration toward Cloud infrastructure and architecture.

My experience in operating systems, infrastructure management, troubleshooting and enterprise environments provides a foundation for understanding the operational aspects of cloud services.

Deploying this application extends that experience into AWS, combining frontend deployment with cloud storage, content delivery, HTTPS and cache management.

It also provides a foundation for future improvements involving deployment automation and CI/CD.

---

**Year:** 2026 · **Focus:** Cloud Infrastructure · AWS · Angular · Amazon S3 · Amazon CloudFront · DNS · HTTPS
