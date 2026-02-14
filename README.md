AWS Project Documentation  

Project Name  
Static Website Hosting using Amazon S3 and CloudFront  


Project Description  

This project demonstrates how to host a static HTML/CSS website using Amazon S3 and improve global performance using Amazon CloudFront (CDN).  

The website is stored in an S3 bucket and delivered securely and efficiently to users worldwide through CloudFront edge locations.


Problem Solved / Goal  

Traditional website hosting can suffer from:  

- Slow loading times for global users  
- Lack of HTTPS support  
- Poor scalability  
- Limited performance optimization  

Solution  

This project solves these problems by:  

- Hosting static content in Amazon S3  
- Distributing content globally using CloudFront CDN  
- Enabling HTTPS secure access  
- Reducing latency using caching at edge locations  

---

AWS Services Used  

- Amazon S3 – Static website hosting  
- Amazon CloudFront – Content Delivery Network (CDN)  
- IAM – Access control and security policies  
- AWS Management Console – Deployment and configuration  

---

Architecture Diagram  

User → CloudFront → S3 Bucket  

Explanation:  

1. User sends request to CloudFront distribution URL  
2. CloudFront checks nearest edge location  
3. If content is cached → served immediately  
4. If not cached → CloudFront fetches content from S3 bucket  
5. Content delivered to user securely via HTTPS  



Deployment Instructions  

Step 1: Create Static Website Files  

1. Create a folder named `Static-Website-Project`  
2. Create `index.html` and `style.css` files  
3. Add HTML and CSS content  

---

Step 2: Create S3 Bucket  
 

1. Login to AWS Console  
2. Navigate to S3  
3. Click Create Bucket  
4. Enter unique bucket name  
5. Disable “Block all public access”  
6. Create bucket  

---
Step 3: Enable Static Website Hosting  
 

1. Open bucket  
2. Go to Properties  
3. Enable Static Website Hosting  
4. Set index document as `index.html`  
5. Save changes  
 

---

Step 4: Upload Website Files  

1. Go to Objects tab  
2. Upload index.html  
3. Upload style.css  
 

---

Step 5: Configure Bucket Policy  

Add policy to allow public read access or configure Origin Access Control if using CloudFront private access.
 

---

Step 6: Create CloudFront Distribution  
 

1. Navigate to CloudFront  
2. Click Create Distribution  
3. Select S3 bucket as origin  
4. Enable “Allow private S3 access”  
5. Use recommended cache settings  
6. Set Default Root Object as `index.html`  
7. Create distribution  
8. Wait until status shows "Deployed"  
 

---

Step 7: Access Website  

Use CloudFront distribution domain name:

https:// d28icawggfnejh.cloudfront.net
 

Website should load successfully.

---

Test Cases  

| TC-01 | Access CloudFront URL | Website loads successfully 
 
| TC-02 | Access S3 direct URL | Either restricted or accessible based on configuration 
 
| TC-03 | Refresh website multiple times | Faster loading due to caching 

---

Screenshots / Demos  

Included screenshots of:  

1. S3 Bucket Creation  
2. Static Website Hosting Enabled  
3. Uploaded Files  
4. Bucket Policy  
5. CloudFront Distribution Created  
6. Distribution Status – Deployed  
7. Final Website Output  

---

Lessons Learned  

- Understanding difference between S3 website endpoint and REST endpoint  
- Importance of Default Root Object in CloudFront  
- How CDN improves website performance  
- How caching reduces latency and cost  
- Importance of secure access using Origin Access Control  

---

## 🔐 Security Best Practices Implemented  

- Used CloudFront Origin Access Control  
- Restricted direct S3 public access (if configured)  
- Enabled HTTPS redirection  
- Used recommended cache settings  

---

Conclusion  

This project successfully demonstrates how to deploy a secure, scalable, and globally distributed static website using Amazon S3 and CloudFront.  

The implementation improves performance, ensures security, and follows AWS best practices for production-ready static website hosting.

---

 
