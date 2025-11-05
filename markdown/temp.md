##  Potential Cost Breakdown

| Category               | Option(s)              | Estimated Monthly Cost (USD) | Notes |
|------------------------|------------------------|------------------------------|-------|
| **Server & Hosting**   | **DigitalOcean**       | **$12**                      | Basic Droplet: 1 vCPU, 2 GB RAM, 50 GB SSD<br>→ Dock>
|                        | **Hetzner**            | **$4**                       | CX11 VPS: 1 vCPU, 2 GB RAM, 20 GB SSD<br>Cheapest Do>
| **Database**           | **MongoDB Atlas**      | **$0** (M0 free)<br>**$9+** (M2/M5) | M0: 512 MB shared<br>M2 ($9/mo): 2 GB<br>M5 (>
|                        | **Supabase**           | **$0** (free)<br>**$25+** (Pro) | Free: 500 MB DB<br>Pro ($25/mo): 8 GB |
| **Forum**              | **Discourse**          | **$0** (self-hosted)<br>**$100** (hosted) | Official Docker image → `docker pull di>
| **Email Verification** | **Gmail SMTP**         | **$0**                       | ~500 emails/day limit<br>Works perfectly in Docker w>
|                        | **SendPulse**          | **$0**                       | 12,000 emails/month free |
| **Domain Name**        | **Namecheap**          | **$1–$2**                    | `.com` ≈ $10–15/year (first year often $1) |
|                        | **Cloudflare Registrar**| **$1–$2**                   | `.com` ≈ $10/year + free DNS/security |
| **Backup & Storage**   | **AWS S3**             | **$0.25** (10 GB)            | $0.023/GB/month |
|                        | **Backblaze B2**       | **$0.05** (10 GB)            | $0.005/GB/month – **cheapest option** |
