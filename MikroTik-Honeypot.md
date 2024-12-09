
# MikroTik RouterOS Honeypot with Telegram Bot Notifications

## **Objective**
The goal of this project is to design a honeypot mimicking a MikroTik RouterOS interface that:
1. Detects and logs:
   - Website visits to the fake router interface.
   - Login attempts and password entries.
   - Port scanning activities.
2. Sends real-time notifications to a Telegram bot with relevant details for each event.
---

## **Implementation**

### **1. Honeypot Interface Design**
- Developed a **web-based replica of the MikroTik RouterOS interface** using HTML, CSS, and JavaScript.
 - Original UI
![Screenshot 2024-12-09 090214](https://github.com/user-attachments/assets/ebacb2f5-4b43-4ae6-99b3-4d8bca9bd8c9)
 - Honeypot UI
![Screenshot 2024-12-09 090200](https://github.com/user-attachments/assets/65271d03-106b-4e04-94d8-786f21c2d919)
---

## **Details of Implementation**
- To implement a MikroTik RouterOS honeypot, created a replica of the MikroTik web interface using web development tools and deployed it locally. Set up scripts to log website visits (recording IP, timestamp, and User-Agent), login attempts (capturing entered credentials), and port scanning activities (using MikroTik firewall rules). 

- Integrated a Telegram bot for real-time notifications that include details like IP address, timestamp, and event type. Used a Python script with the Telegram API to send messages triggered by these events. Tested the honeypot by simulating visits, login attempts, and port scans with tools like nmap in a controlled environment.

## **Example Notifications**

### **1. Website Visit Detected:**
![Screenshot 2024-12-09 092909](https://github.com/user-attachments/assets/2d18a74e-cacc-4e82-898f-3c3f1a3c90bc)
### **2. Login Attempt Detected:**
![Screenshot 2024-12-09 092921](https://github.com/user-attachments/assets/fd64b245-7b46-4102-86fb-0114b13a3c82)
### **3. Port Scanning Detected:**
![Screenshot 2024-12-09 092928](https://github.com/user-attachments/assets/af6f8bb1-1caf-4143-8c21-f79d5c5cad4f)
---
