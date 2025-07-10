# 🌐 Day 4 – Assigning Elastic IP to EC2 Instance

**Date:** 9 July 2025  
**Goal:** Assign a static (Elastic) IP address to my EC2 instance to keep the public IP fixed — even after reboot.

---

## ✅ What I Did

1. Navigated to EC2 Dashboard → **Network & Security → Elastic IPs**
2. Clicked **“Allocate Elastic IP address”**
   - Chose default Amazon IPv4 pool
   - Selected `us-east-1` as region
3. Clicked **Allocate** and successfully received a new Elastic IP (e.g., `52.0.24.104`)

4. Associated the Elastic IP with my running EC2:
   - Selected the IP
   - Actions → **Associate Elastic IP**
   - Linked it to my EC2 instance

5. Verified:
   - Public IPv4 updated on EC2
   - Website accessible via new IP → `http://52.0.24.104`

---

## ⚠️ Important Notes

- Elastic IP is **free only while attached** to a running EC2
- Charges apply if left unassociated
- HTTPS (`https://`) won't work on raw IPs unless SSL is manually configured (we used only `http://`)

---

## 📘 Learnings

- Elastic IP keeps server accessible on same IP after reboot
- Crucial for production/public websites
- Always release unused Elastic IPs to avoid charges

---

screenshots
'/c/Users/HP/OneDrive/Pictures/Screenshots/Screenshot (241).png' '/c/Users/HP/OneDrive/Pictures/Screenshots/Screenshot (239).png' '/c/Users/HP/OneDrive/Pictures/Screenshots/Screenshot (240).png'

