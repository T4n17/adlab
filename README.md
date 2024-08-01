## Active Directory LAB

A small private network running an Active Directory, which includes a domain controller (running Windows Server 2022 Standard Evaluation with Desktop), a normal user (running Windows 10 Pro without a product key (unactivated)), and an operator (a minimal Kali installation).

# Topology

![alt text](https://github.com/T4n17/adlab/blob/main/NetworkTopology.png)

Each machine has two adapters: one is a NAT adapter used by Vagrant, and the other is an internal network adapter that simulates a private network.


# Prerequisites

You should have VirtualBox and Vagrant installed.
It is recommended to have at least 30 GB of free space and 16 GB of RAM to set up the environment.

# Installing

- Clone the repository: `git clone https://github.com/t4n17/adlab`
- Navigate to the directory and run: vagrant up (This step might take a while, especially for the user01 machine)

# Usage

After setup, you can modify any aspect of the machines to simulate various scenarios. The operator machine can be accessed with: `vagrant ssh bt01`, and the other machines can be accessed with `vagrant rdp dc01` or `vagrant rdp user01`. You can also access the machines directly from VirtualBox.
