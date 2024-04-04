# UbuntuServer

Welcome to the Linux server project! In this assignment, we will be setting up a Linux infrastructure consisting of a server and a workstation to demonstrate the functionality of various network services. This project is part of a consolidation challenge and must be completed within a duration of 3 days, with a deadline of 04/04/2024.

This project aims to showcase the capabilities of Linux in a local library scenario where Windows licenses are not available. We will be using virtual machines and an internal virtual network to simulate the setup, ensuring that our DHCP does not interfere with the LAN.

You will find detailed instructions and documentation for setting up the Linux infrastructure below. Additionally, a summary of the project requirements and evaluation criteria is provided.

For the complete assignment document, please refer to [Assignment](/Assignment.md)

Let's dive into the setup process and demonstrate the power of Linux network services!

----
# Installation Guide

## 1. Installing Ubuntu Server
- Install Ubuntu Server.
- Set up the root password.
- Configure a user.

<details>
  <summary>See step by step</summary>

  <img src="/assets/i1.png" alt="Image 1">
  <img src="/assets/i2.png" alt="Image 2">
  <img src="/assets/i3.png" alt="Image 3">
  <img src="/assets/i4.png" alt="Image 4">
  <img src="/assets/i5.png" alt="Image 5">
  <img src="/assets/i6.png" alt="Image 6">
  <img src="/assets/i7.png" alt="Image 7">
  <img src="/assets/i8.png" alt="Image 8">
  <img src="/assets/i9.png" alt="Image 9">


</details>

## 2. Configuring ISC DHCP Server
- Install `isc-dhcp-server`.
- Configure `/etc/dhcp/dhcpd.conf`.
  ![Image 1](assets/1.png)

## 3. Installing net-tools and Firewall Configuration
- Install `net-tools` to use `netstat`.
- Allow necessary ports in the firewall.
  ![Image 2](assets/2.png)
  ![Image 3](assets/3.png)
  ![Image 4](assets/4.png)

## 4. Assigning a Static IP Address
- Use Netplan to configure a static IP.
- Modify `/etc/netplan/config.yaml`.
  ![Image 5](assets/5.png)
  ![Image 6](assets/6.png)
- Apply the configuration with `sudo netplan apply`.

## 5. Installing and Configuring BIND9 (DNS)
- Install `bind9`, `bind9utils`, and `bind9-doc`.


<details>
  <summary> Configure zone files and configuration files.</summary>
  

  - `named.conf.options`
    <img src="assets/named.conf.options.txt" alt="named.conf.options">

  - `db.example.com`
    <img src="assets/db.example.com.txt" alt="db.example.com">

  - `db.192`
    <img src="assets/db.192.txt" alt="db.192">

  - `named.conf.local`
    <img src="assets/named.conf.local.txt" alt="named.conf.local">


</details>


- Restart BIND9 with `sudo systemctl restart bind9`.
- Enable the firewall and allow BIND9.
  ![Image 7](assets/7.png)

## 6. Installing Apache HTTP Server
- Update the system.
- Install Apache2.
- Check the IP address in the browser.
- Modify the content of `/var/www/html/` to display your website.

## 7. Installing MariaDB and GLPI
- Download GLPI from GitHub.
- Extract the files into `/var/www/html/`.
- Change the permissions of the GLPI directory.
- Install MariaDB.
- Create a database for GLPI.
- Create a MySQL user for GLPI.
- Restart Apache.
- Access `localhost/glpi` in a browser and follow the instructions.
  ![Image 8](assets/8.png)

  # Conclusion

  In this guide, we've successfully set up a Linux server environment to demonstrate essential network services like DHCP, DNS, and HTTP. Through careful configuration and troubleshooting, we've ensured that each component functions smoothly, laying the groundwork for a reliable infrastructure. With our documentation and live demo, we're ready to showcase our Linux server solution to the local library and address any questions or concerns they may have. This marks the completion of our project, showcasing the power and flexibility of Linux in meeting the library's needs.