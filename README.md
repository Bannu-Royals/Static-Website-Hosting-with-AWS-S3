# Static-Website-Hosting-with-AWS-S3

![WhatsApp Image 2024-07-15 at 11 06 55_27f8a392](https://github.com/user-attachments/assets/1f201356-827f-40ff-9edf-0626c3e28ad9)
## Project Documentation: Static Website Hosting with S3

#### Overview

This documentation provides a step-by-step guide to hosting a static website on Amazon S3. Hosting a static website on S3 is a cost-effective and scalable way to serve static content like HTML, CSS, and JavaScript files.

#### Prerequisites

- An AWS account.
- Basic knowledge of HTML, CSS, and JavaScript.
- AWS CLI (optional, for advanced configurations).

#### Step-by-Step Guide

### 1. Create an S3 Bucket

1. Log in to the AWS Management Console.
2. Navigate to the S3 service.
3. Click on "Create bucket".
4. Enter a unique bucket name (e.g., `my-static-website`).
5. Choose the AWS region where you want to create the bucket.
6. Leave the other settings as default and click "Create bucket".

[Amazon S3 Documentation: Creating a Bucket](https://docs.aws.amazon.com/AmazonS3/latest/userguide/creating-bucket.html)

### 2. Upload Your Website Files

1. Click on your newly created bucket.
2. Click on "Upload".
3. Add your website files (e.g., `index.html`, `styles.css`, etc.).
4. Click "Upload" to upload the files to your S3 bucket.

[Amazon S3 Documentation: Uploading Objects](https://docs.aws.amazon.com/AmazonS3/latest/userguide/upload-objects.html)

### 3. Configure the Bucket for Static Website Hosting

1. Click on the "Properties" tab of your bucket.
2. Scroll down to the "Static website hosting" section.
3. Click on "Edit" and then select "Enable".
4. Specify the index document (e.g., `index.html`).
5. Optionally, specify an error document (e.g., `error.html`).
6. Click "Save changes".

[Amazon S3 Documentation: Configuring a Bucket for Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)

### 4. Set Bucket Policy for Public Access

1. Click on the "Permissions" tab of your bucket.
2. Scroll down to the "Bucket policy" section and click "Edit".
3. Paste the following bucket policy to allow public read access:
    ```json
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "PublicReadGetObject",
                "Effect": "Allow",
                "Principal": "*",
                "Action": "s3:GetObject",
                "Resource": "arn:aws:s3:::my-static-website/*"
            }
        ]
    }
    ```
4. Replace `my-static-website` with the name of your bucket.
5. Click "Save changes".

[Amazon S3 Documentation: Bucket Policy Examples](https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html)

### 5. Access Your Static Website

1. Go back to the "Properties" tab of your bucket.
2. In the "Static website hosting" section, you will see the "Bucket website endpoint".
3. Open this URL in your web browser to see your static website live.

[Amazon S3 Documentation: Website Endpoints](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteEndpoints.html)

### Optional Enhancements

#### 1. Custom Domain with Route 53

1. Register a domain or use an existing one.
2. Configure Amazon Route 53 to route traffic to your S3 bucket.

[Amazon Route 53 Documentation: Getting Started](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html)

#### 2. HTTPS with Amazon CloudFront

1. Set up a CloudFront distribution to serve your static website over HTTPS.
2. Configure the CloudFront distribution to use your S3 bucket as the origin.
3. Associate an SSL/TLS certificate from AWS Certificate Manager (ACM) for HTTPS support.

[Amazon CloudFront Documentation: Getting Started with a Simple CloudFront Distribution](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/GettingStarted.SimpleDistribution.html)

### Example Files

**index.html:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Static Website</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Welcome to My Static Website</h1>
    <p>This is a simple static website hosted on Amazon S3.</p>
</body>
</html>
```

**styles.css:**
```css
body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin-top: 50px;
}
h1 {
    color: #333;
}
p {
    color: #666;
}
```

### Conclusion

By following this documentation, you have successfully hosted a static website on AWS S3. This setup is ideal for serving static content efficiently and can be enhanced with custom domains and HTTPS for added security and professionalism.

#### Related Links

- [Amazon S3 Overview](https://aws.amazon.com/s3/)
- [Amazon S3 Pricing](https://aws.amazon.com/s3/pricing/)
- [AWS Free Tier](https://aws.amazon.com/free/)
- [AWS Getting Started Resource Center](https://aws.amazon.com/getting-started/)
- [Amazon S3 FAQs](https://aws.amazon.com/s3/faqs/)

### Conclusion

By following this documentation, you have successfully hosted a static website on AWS S3. This setup is ideal for serving static content efficiently and can be enhanced with custom domains and HTTPS for added security and professionalism.
