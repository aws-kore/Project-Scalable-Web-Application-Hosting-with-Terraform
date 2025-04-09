                 +--------------------+    
                 |   AWS Cloud        |                                    Project Overview:
                                                 This Terraform project sets up an AWS infrastructure that includes a Virtual Private Cloud (VPC), public and private subnets, EC2 instances for web and database services, an Internet Gateway, a NAT Gateway, an S3 bucket, and the necessary networking components. The project is designed to create a secure, scalable environment where an EC2 instance (web server) can communicate with an EC2 instance running MariaDB (database server) in a private subnet. Additionally, public-facing services are hosted on the web server while database services are isolated within a private subnet.
                 +--------------------+    
                          |  
              +-------------------------+
              |         VPC (10.0.0.0/16)|
              +-------------------------+
               /                         \
              /                           \
    +----------------+            +----------------+
    | Public Subnet  |            | Private Subnet |
    | (10.0.0.0/24)  |            | (10.0.1.0/24)  |
    +----------------+            +----------------+
              |                           |
  +---------------------+        +----------------------+
  |  Web Server (EC2)   |        |   MariaDB (EC2)      |
  |  (Public Subnet)    |        |   (Private Subnet)   |
  +---------------------+        +----------------------+
           |                              |
           |                              |
           +----> Internet Gateway <------+
           |
           +----------------------------+
           |        NAT Gateway         |
           +----------------------------+
           |
  +-----------------------+
  |     S3 Bucket         |
  |  (Storage/Backups)    |
  +-----------------------+
