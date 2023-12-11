---
title: "Hosting a static website on Amazon S3"
datePublished: Mon Dec 11 2023 10:44:53 GMT+0000 (Coordinated Universal Time)
cuid: clq0seihb000n08ky5n9921ga
slug: hosting-a-static-website-on-amazon-s3
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702291378308/32dc88f0-ea14-4099-b22f-455c8f673cfc.jpeg
tags: aws, web-development, learning-journey, s3-bucket

---

  
Hosting a static website on Amazon S3 is a straightforward process. Here's a step-by-step guide:

### **1\. Create an S3 Bucket:**

* Log in to your AWS Management Console.
    
* Navigate to the Amazon S3 service.
    
* Click on "Create bucket."
    
* Choose a globally unique bucket name and select the region.
    
* Keep the default settings for the rest of the options, and click "Create bucket."
    

### **2\. Configure the S3 Bucket for Static Website Hosting:**

* Select your newly created bucket.
    
* Click on the "Properties" tab.
    
* Click on "Static website hosting."
    
* Choose the option to enable static website hosting.
    
* Specify the index document (e.g., `index.html`) and the error document if you have one.
    
* Save the changes.
    

### **3\. Upload Your Website Content:**

* Go back to the main dashboard of your bucket.
    
* Click on the "Upload" button.
    
* Add your HTML, CSS, JavaScript files, and any other assets that make up your website.
    
* Make sure to set the permissions for these files to be publicly readable. You can do this by selecting the file and choosing "Make public" or configuring the bucket policies accordingly.
    

### **4\. Set Bucket Permissions:**

* Navigate to the "Permissions" tab of your bucket.
    
* Ensure that the bucket policy allows public read access. You can use a policy like the following (modify it based on your bucket name and requirements):
    

```plaintext
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

### **5\. Access Your Website:**

* Once your files are uploaded and the bucket is configured, you can access your website using the provided endpoint. The endpoint will be in the format: [`http://your-bucket-name.s3-website-your-region.amazonaws.com`](http://your-bucket-name.s3-website-your-region.amazonaws.com).
    

### **6\. Configure Custom Domain (Optional):**

* If you have a custom domain, you can configure it to point to your S3 website. This involves setting up a DNS record and updating your bucket settings to recognize the custom domain.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702291195763/4dfae946-0088-4188-8882-b648fd995bce.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702291202290/95230a9a-0140-45f8-bf1f-61b6c0a29619.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702291205955/ef35160f-672e-46cc-863e-6604778c37e3.png align="center")