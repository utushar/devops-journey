# 🌐 Static Website Deployment on EC2 using NGINX

**Date:** 8 July 2025  
**Instance Type:** t2.micro (Free Tier)  
**OS:** Ubuntu 22.04  
**Web Server:** NGINX

## ✅ Steps Followed:

1. **Created Website Files Locally**
   - Built a simple `index.html` and optional `style.css` inside `my-website` folder on local machine.

2. **Connected to EC2 using SSH**
   - Used `.pem` private key to securely connect to the EC2 instance:
     ```bash
     ssh -i ~/Downloads/tushar_key.pem ubuntu@18.205.240.243
     ```

3. **Transferred Website Files using SCP**
   ```bash
   scp -i ~/Downloads/tushar_key.pem ~/Documents/my-website/index.html ubuntu@18.205.240.243:/tmp
   scp -i ~/Downloads/tushar_key.pem ~/Documents/my-website/style.css ubuntu@18.205.240.243:/tmp

