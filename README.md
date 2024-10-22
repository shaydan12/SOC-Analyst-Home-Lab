## Introduction

I followed through [MyDFIR's](https://www.youtube.com/channel/UCWoH3f-Yx6TxJfO2O_ezJUw) [30-Day SOC Analyst Challenge](https://youtube.com/playlist?list=PLG6KGSNK4PuBb0OjyDIdACZnb8AoNBeq6), a challenge which helps aspiring SOC analyst gain practical, hands on knowledge and  experience within 1 month.

&nbsp;

In this challenge, I set up a SOC environment  placing a Windows Server and a Linux Server up in the cloud with SSH and RDP enabled and open to the internet in order to investigate brute force activity.

&nbsp;

Having any machine with SSH or RDP open to the internet is a security risk, as it allows anyone which includes attackers to try and break in using methods such as brute force attacks.

&nbsp;

&nbsp;

&nbsp;

## Logical Diagram

![image](https://github.com/user-attachments/assets/39dbb3a2-ee6a-4a74-931f-310d29b5f95f)

I installed the Elastic Agents onto the Windows and Linux servers which I want to monitor. The agents are connected to a fleet which manages multiple agents within a centralized location, making configuration and policy creating easier.

![image](https://github.com/user-attachments/assets/aa9828db-1889-4f6c-8259-5a7baba45d49)

&nbsp;

&nbsp;

## Creating Alerts and Dashboards

&nbsp;

### **Creating Dashboards**

I created a table that shows what source ip and from what countries most of the brute force attacks are coming from, along with a table that shows information about successful SSH login attempts, (one from myself):

![image](https://github.com/user-attachments/assets/5bc8c65d-cfcc-4741-b75a-9a2e22260899)

&nbsp;

I did the same for RDP login attempts:

![image](https://github.com/user-attachments/assets/013bc01a-240b-4761-959e-d4d53b933dce)

&nbsp;

Visual map of failed SSH authentications:

![image](https://github.com/user-attachments/assets/e5be8e16-0e00-486e-9160-79119d181cd3)

Visual map of SSH successful authentications:

![image](https://github.com/user-attachments/assets/d1b645f5-8a97-4afd-bae9-d6f9eb427704)

Visual map of RDP successful authentications:

![image](https://github.com/user-attachments/assets/d85b22f1-79c0-40a8-9470-64a26447ff75)

Visual map of RDP failed authentications:

![image](https://github.com/user-attachments/assets/0a4535a1-a112-476c-b8a8-25b947095fdd)

### **Creating Alerts**

I created an alert that triggers whenever there is a large amount of authentication attempts via SSH in a short period of time. I quickly tested the rule by brute forcing the Linux server myself, and an alert was generated:  
![image](https://github.com/user-attachments/assets/598aca04-9895-44b8-9d3d-9c9cf27b5b5c)

![image](https://github.com/user-attachments/assets/fae1cc64-d15d-4f0a-b86b-def95d43b87a)

&nbsp;

## Investigating Brute Force Activity

![image](https://github.com/user-attachments/assets/a021fab4-3477-4d44-a878-592d2f739839)

## Using Elastic Defend EDR

## Mitigation and Security Best Practices


- Place internet facing ports behind a firewall or a VPN
- Choose a strong password
- Enable 2FA

&nbsp;

&nbsp;

&nbsp;
