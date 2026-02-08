# AWS EC2 + NGINX Domain Deployment

## Objective 
Buy a domain, deploy NGINX on an EC2 instance, and make the page load over your own domain. Here are the steps I took. 

## 1. Buy a Domain
- Bought jaydenm.org through cloudflare.
<img width="563" height="123" alt="Screenshot 2026-02-07 at 17 10 51" src="https://github.com/user-attachments/assets/3e83f586-4457-48b1-80d2-ee0cb21ad0f5" />

## 2. Launch an EC2 Instance
- Used Amazon Linux as the distro.
- Created SSH key pair for secure remote access
<img width="1621" height="584" alt="Screenshot 2026-02-07 at 17 39 28" src="https://github.com/user-attachments/assets/88e242ec-3b4d-4f46-9c8a-e560966813f1" />

## 3. Configure DNS
- Created a record in Cloudflare
- Pointed it to the IPv4 address
<img width="1329" height="318" alt="Screenshot 2026-02-08 at 16 19 47" src="https://github.com/user-attachments/assets/31bcaec4-444a-4a15-a36f-e0b3e7f0bf31" />

## 4. Testing
- Domain access: http://nginx.jaydenm.org - NGINX welcome page loads
<img width="1680" height="1050" alt="Screenshot 2026-02-08 at 16 16 37" src="https://github.com/user-attachments/assets/46e21ca1-7225-4a17-8267-72e796a8cf09" />

## Challenges Encountered

**Challenge 1: NGINX page not loading**
- Problem: When accessing the domain, browser showed "This site can't be reached"
- Cause: Browser was auto-redirecting to HTTPS instead of HTTP
- Solution: Explicitly used `http://` in the URL since SSL/TLS wasn't configured yet

**Challenge 2: "Web server is down" message**
- Problem: Cloudflare showing error even though EC2 was running
- Cause: Cloudflare proxy (orange cloud) was enabled, expecting HTTPS
- Solution: Changed DNS to "DNS only" mode (gray cloud) for HTTP compatibility
