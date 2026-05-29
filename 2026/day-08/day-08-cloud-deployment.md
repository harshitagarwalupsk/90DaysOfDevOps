<img width="418" height="188" alt="image" src="https://github.com/user-attachments/assets/c8a5dc75-b9f6-4bc0-995b-d10c8688cbeb" />
## Commands Used
apt install nginx

systemctl status nginx

## Challenges Faced
Facing challange in creating securrity group and using the public or private IP of my machine and http or https during the setup.

## What I Learned
Difference between Public and Private IP, http and https and how the inbound rules are created under the security group.

#### Internet Accessibility: 
The Public IP is a globally routable address that allows devices outside of the AWS network (like your personal laptop) to reach the instance over the internet.

#### External Routing: 
Private IPs are isolated and only function within the Amazon Virtual Private Cloud (VPC) for internal communication between your own AWS resources.How to F

#### Use HTTP when:
Testing initial setups: Use HTTP right after installing Nginx to verify the web server works.No SSL certificate exists: Use HTTP if you have not created or bought an SSL/TLS certificate yet.Local development: Use HTTP when running internal tests where data security is not a risk.

#### Use HTTPS when:
Live production sites: Use HTTPS for any website accessible to the public.Handling sensitive data: Use HTTPS whenever users type passwords, credit cards, or personal info.Improving SEO ranking: Google ranks HTTPS websites higher than unsecured HTTP sites.Avoiding browser warnings: Modern browsers display a scary "Not Secure" warning on HTTP sites.
