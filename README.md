# AWS EC2 + NGINX Domain Deployment

## Objective 
Buy a domain, deploy NGINX on an EC2 instance, and make the page load over your own domain. Here are the steps I took. 

## 1. Buy a Domain
- Bought jaydenm.org through cloudflare.
<img width="563" height="123" alt="Screenshot 2026-02-07 at 17 10 51" src="https://github.com/user-attachments/assets/3e83f586-4457-48b1-80d2-ee0cb21ad0f5" />

## 2. Launch an EC2 Instance
- Used Amazon Linux as the distro.
- Created a new key pair to SSH.
<img width="1621" height="584" alt="Screenshot 2026-02-07 at 17 39 28" src="https://github.com/user-attachments/assets/88e242ec-3b4d-4f46-9c8a-e560966813f1" />

## 3. Configure DNS
- Created a record in Cloudflare
- Pointed it to the IPv4 address
<img width="1329" height="318" alt="Screenshot 2026-02-08 at 16 19 47" src="https://github.com/user-attachments/assets/31bcaec4-444a-4a15-a36f-e0b3e7f0bf31" />

## 4. Testing
- 
