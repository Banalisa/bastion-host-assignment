Bastion Host Project – Instasafe Technologies Assignment

→ Objective

The goal of this project is to set up a Bastion Host in a cloud environment to securely access a private server.

A bastion host acts as a secure gateway between external users and a private network, reducing the attack surface by ensuring that only the bastion host is publicly accessible.

→ Cloud Environment Setup

1. Infrastructure
Cloud Provider : AWS (t3.micro instances, Ubuntu 22.04 LTS)
Servers Created.
Bastion Host → Publicly accessible with a public IP.
Private Server → Accessible only from the Bastion Host’s private IP (no public IP).
2. Security Groups
Bastion Host : Port 22(SSH) → Allowed only from my local IP.
Private Server : Port 22(SSH) → Allowed only from Bastion Host’s private IP.
3. SSH Configuration in MobaXterm
Instead of using /.ssh/config, MobaXterm allows configuration via the GUI.
-> Connect to Bastion Host
-> Open MobaXterm → Session → SSH
-> Enter:
Remote host : 35.172.223.225 Username: ubuntu
-> In the Advanced SSH settings tab: - Check Use private key and browse to
“/Desktop/bastionKey.pem”.
-> Save session as Bastion Host.
-> Connect to Private Server via Bastion 
-> Open MobaXterm → Session → SSH.
-> Enter: Remote host : 10.0.2.55
-> Username: ubuntu
-> Go to Network settings → SSH gateway (jump host) :
 Check Connect through SSH gateway Enter 35.172.223.225 as the gateway
 host. Specify ubuntu and the bastion private key file.
-> In the main session window, added the Private Server’s private key under Use
private key. Save session as Private Server. Now you can double-click Private
Server in MobaXterm, and it will automatically jump through the Bastion Host.


