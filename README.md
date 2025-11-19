Static Website Hosting Using AWS S3 (React App Deployment)

This project demonstrates how to deploy a React.js static website using Amazon S3. S3 provides a simple, scalable, and cost-effective way to host static websites such as SPAs (Single Page Applications) created with React.

🚀 Project Overview

This project includes:

A frontend web application built using React.js

Deployment of the React build folder to an S3 bucket

Configuration of Static Website Hosting on S3

Public access setup using bucket policies

React SPA routing support by setting index.html as error page

🏗️ Architecture
React App → npm run build → Build Folder → S3 Bucket → Public Website URL

✔️ Features

Host React website on S3

Fully serverless and scalable

Very low cost

SPA-friendly setup (React Router supported)

Easy deployment steps

📦 Tech Stack

Frontend: React.js

Cloud: AWS

Service Used: Amazon S3

🛠️ How to Deploy React App on S3
1️⃣ Build the React App

Run the command:

npm run build


This generates a build folder with production-optimized static files.

2️⃣ Upload Build Files to S3

Inside the bucket:

Click Upload

Upload all files inside the build/ folder

Do NOT upload the entire project.

3️⃣ Enable Static Website Hosting

Go to:

S3 > Your Bucket > Properties > Static Website Hosting

Enable it and set:

Index document: index.html

Error document: index.html (important for React Router)

4️⃣ Make Your Bucket Public

Go to:

Permissions > Bucket Policy

Add this policy (replace your-bucket-name):

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

5️⃣ Access Your Website

In the Static Website Hosting section, you will get a URL like:

http://your-bucket-name.s3-website-region.amazonaws.com


Open it — your React website is now live!


🎯 Conclusion

This project shows a complete end-to-end process for deploying a React application using AWS S3. It’s a simple, secure, and cost-efficient way to host static websites without managing any servers.
