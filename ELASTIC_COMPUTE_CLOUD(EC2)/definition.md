# Definition
- EC2 is one of the most popular AWS service
- EC2 = Elastic Computed Cloud = Imfrastructure as a service
- It mainly consists in the capabilities of: 
  - Renting virtual machine (EC2)
  - Storing data on Virtual drives (EBS)
  - Distributing load accross machine (ELB)
  - Scaling the services using auto scaling group(ASG)
  - Knowing EC2 is fundamental of knowing how cloud works

# Sizing and config options 
- Operating system(OS): Linux, Window, MacOS
- How much computed power and cores (CPU)
- How much random-access memory(RAM)
- How much storage space: 
  - Network attached (EBS & EFS)
  - Hardware (EC2 instance store)
- Network card: speed of the card, public ip address
- Firewall rule: security group
- Bootstrap script(config at the first lauch): EC2 user data

# EC2 instance types
* Refer: [aws.amazon.com/ec2/instance-types](https://aws.amazon.com/ec2/instance-types/)
- Instance type has following namming convention, for ex m5.2xlarge:
  - m: instance class
  - 5: generation (AWS improves them over time)
  - 2xlarge: size within instance class
- Using instance type balance between: 
  - Compute
  - Memory
  - Networking (bandwidth...)
- Computed optimize
- Memory optimize

# Security groups
- Security groups are the fundamental of network security in AWS
- They control how traffic is allowed into or out of EC2 instance
- Security groups only contain rules
- Security groups rules can reference by IP or by security group
- Common port 
  - 22 SSH - secure shell - login to linux instance
  - 21 FTP (File Transfer Protocol) upload files in to a file share
  - 22 SFTP ( Secure File Transfer Protocol) upload file using SSH
  - 80 HTTP - access unsecure website
  - 443 HTTPS access secure website
  - 3389 RDP (Remote desktop protocol) - login to a window instance
# EC2 Purchasing option
Ref: [EC2 Pricing](https://aws.amazon.com/ec2/pricing/)
- EC2 On Demand
  - Pay for what you use
  - Linux/Window - Billing persecon at the 1st minutes
  - All others operating system - billing per hour
  - No longterm commitment, recommend for shortterm or application you don't know how application will behave
- EC2 - Reservation Instance
  - Reservation Priod 1 year ( + discount) 3 year (+++ discount)
  - Payment option - No upfront (+), partial upfront (++), all upfront (+++)
  - Reserve Instance scope (reserve capacity in an AZ)
  - Convertible Reserved Instance
    - Can change instance type, family, OS, scope and tenacy
    - Up to 66% discount

