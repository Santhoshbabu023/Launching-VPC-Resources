# AWS VPC Project: Launching VPC Resources

## Introduction

This project demonstrates how to set up and manage Amazon VPC (Virtual Private Cloud) resources in AWS. By leveraging Amazon VPC, I created a secure, isolated network and launched both public and private EC2 instances while ensuring proper configuration and security.

## Project Overview

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) allows you to create a private network within AWS, offering control over IP ranges, subnets, and security settings. It’s essential for securely managing resources, controlling connectivity, and network isolation.

### How I Used Amazon VPC in This Project

In this project, I utilized Amazon VPC to create a secure, isolated network. The tasks involved:

- Setting up public and private subnets
- Configuring route tables for traffic flow
- Applying network ACLs to control access
- Ensuring secure and efficient communication between instances

### One Thing I Didn't Expect

One thing I didn’t expect was how crucial it is to plan subnet CIDR blocks carefully. Overlapping or misconfigured IP ranges can lead to connectivity issues later, requiring adjustments that can disrupt the network setup.

### Time Taken

This project took approximately **1 hour** to complete. I set up the VPC, created subnets, configured security groups, set up NAT gateways, and tested connectivity to ensure proper communication and security.

---

## Setting Up Direct VM Access

### Direct Access to a Virtual Machine (VM)

Directly accessing a virtual machine means connecting to the instance without intermediaries, using protocols like SSH or RDP. This allows you to interact with the EC2 instance's operating system and perform administrative tasks directly.

### SSH: A Key Method for Directly Accessing a VM

SSH traffic means data transferred over the Secure Shell protocol, which is used to securely access and manage remote systems. It encrypts communication to protect sensitive information, typically used for remote server management or file transfers.

### Setting Up Key Pairs for Direct Access

In AWS, key pairs consist of a **public key**, which is stored on EC2 instances, and a **private key**, which the user keeps. The private key is used to securely authenticate and establish SSH connections to EC2 instances.

### Private Key Format

A private key's file format defines how the key data is structured and stored. My private key's file format was **PEM**, which is a base64-encoded format with a "-----BEGIN PRIVATE KEY-----" header.

---

## Launching a Public Server

To launch a public EC2 instance, I updated the instance's networking settings by:

- Modifying security group rules to allow specific traffic (like SSH)
- Adjusting network interface settings
- Ensuring proper subnet and route table configurations for seamless connectivity

---

## Launching a Private Server

My private server has its own dedicated security group because it requires more restricted access for security purposes. This ensures only authorized internal resources can communicate with it, minimizing exposure to external threats.

### Private Server's Security Group Source

The source for my private server's security group is an internal IP range or security group ID, meaning only authorized internal resources can access it, reducing exposure and enhancing security.

---

## Speeding Up VPC Creation

I used an alternative way to set up an Amazon VPC using the **VPC Wizard** in the AWS Management Console. The wizard offers predefined configurations for subnets, route tables, and security settings, streamlining the setup process.

### VPC Resource Map

A VPC resource map is a visual representation of components in a VPC (subnets, route tables, security groups, etc.). It helps you understand their relationships, making management and troubleshooting easier.

---

## Key Insights from VPC Setup

- **CIDR Block Configuration**: My new VPC has a CIDR block of **10.0.0.0/16**, and it’s possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because they are in separate, isolated networks.
- **Public Subnets**: When determining the number of public subnets, I had two options: creating one subnet per Availability Zone or a single subnet. AWS recommends distributing resources across multiple zones for better availability and fault tolerance.
- **NAT Gateways**: The setup page offered to create **NAT Gateways**, which allow instances in private subnets to access the internet while blocking inbound traffic, ensuring isolated yet functional resources.

---

## Key Learning Outcomes

### What You've Learned:

- **💻 Launch a Public EC2 Instance**: You launched an EC2 instance in a public subnet, selected the appropriate AMI and instance type, and configured key pairs for secure access.
- **🤐 Launch a Private EC2 Instance**: You launched an EC2 instance in a private subnet, configured a dedicated security group, and used the same key pair for access.
- **⚡️ Speed Up VPC Creation**: You explored using the VPC wizard and leveraged the VPC resource map to visualize how components like subnets and route tables are connected.

---

## Conclusion

This project provided hands-on experience with AWS networking features like VPCs, subnets, security groups, and NAT gateways. By following this process, you can efficiently deploy secure, isolated resources in AWS and manage them through the VPC setup.
