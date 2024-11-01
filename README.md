# Installing Kali Purple and Elastic SEIM

---
In this project, I will be installing Kali purple on a virtual machine which will serve as blue, Then will also have another Kali machine which will serve as the Red team and lastly a Windows machine that will serve as the victim. For the experiment, i will be using Virtual box as my hypervisor 

I will be conducting a series of attacks on the Windows machine using Kali for attacks the monitoring these attacks using Kali Purple where the Elastic SEIM will be installed.

First, i have to install Kali Purple i already downloaded the ISO from Kali website 


Kali purple machine will have 8GB of RAM, 4 CPU and 80GB ROM

<img width="1007" alt="Screenshot 2024-11-01 at 03 14 14" src="https://github.com/user-attachments/assets/5442e0d8-1143-49ad-8096-7d0408bd15b5">

<img width="900" alt="Screenshot 2024-11-01 at 03 31 52" src="https://github.com/user-attachments/assets/f5cbe6f4-8a7d-4b54-b8c5-48f4cba9c431">





## Project Overview
- **Objective**: This project demonstrates a controlled phishing simulation attack using GoPhish. It aims to educate users about phishing risks, help them recognize phishing emails, and analyze user responses.
- **Scope**: The simulation involves creating a phishing campaign with realistic email and landing page components, tracking user engagement metrics, and evaluating security awareness.
- **Tools**: GoPhish, virtual machines (isolated lab environment), email templates, and custom landing pages.

---

## Project Setup

### Environment
1. **Lab Environment**: Set up a secure, isolated lab environment to avoid accidental exposure.
   - **Install GoPhish**: Install GoPhish on a virtual machine.
   - **Network Configuration**: Configure network settings to allow controlled email delivery within the lab environment.

2. **Landing Page**: Create a realistic landing page in GoPhish that resembles a typical login page (e.g., corporate login, Microsoft 365) for the phishing simulation.

---
In this experiment i will be creating a phishing simulation using Gophisp
First i had to create VPC instance, I will be using Linode then i had to created an ubuntu 22.04 machine with 1GB RAM 1 CPU and 25GB ROM 
Then i SSH into the machine, Next i updated all the packages using "sudo apt-get update && apt-get upgrade -y "
Then i installed unzip "sudo apt-get install unzip"
Then i had to make a new directory name Gophish and used the wget command to download Gophish from their github repo.
Next i used the unzip tool to extract Gophisp
Then i modified the config.json file and edited the listen_url to "0.0.0.0"
Next i used "chmod +x gophisp" to make the gophish and executable 
Then i started Gophisp using "sudo ./gophish" command
After starting the service i was able to access the gophisp page on "https://0.0.0.0:3333"
Next i created a new user group
Then i create added the email template
Next i added the landing page
Lastly i added the sending profile

Then i created and launched a new campaign 



## Phishing Campaign Design

### Email Template
- **Subject Line**: Create a compelling subject line (e.g., "Urgent: Action Required for Account Security").
- **Body Content**: Use company branding and language to enhance realism.
- **Call to Action**: Include a call-to-action button or link (e.g., "Click here to verify your account").

### Landing Page Customization
- Design the landing page to mimic an authentic login page, while optionally including disclaimers to inform users that this is part of a security exercise.

---

## Campaign Execution and Metrics

1. **Target Group**: Define a test group (or use lab test accounts) to receive the simulated phishing emails.
2. **Campaign Configuration**: Use GoPhish's campaign features to manage email sends, links, and data tracking.
3. **Metrics Tracking**:
   - Number of **emails opened**
   - Number of **links clicked**
   - **Landing page interactions**
   - **Credentials entered** (if using a login page simulation)

---

## Post-Attack Analysis and Reporting

1. **Data Analysis**: Review GoPhish results to understand:
   - User engagement with the phishing email.
   - Click-through rate.
   - The number of users who attempted to log in.

2. **Report Findings**: Summarize outcomes, highlighting areas for improvement in security awareness training.

3. **Recommendations**:
   - Provide anti-phishing best practices and awareness training based on results.
   - Outline potential policy improvements to reduce phishing risks.

---

## Legal and Ethical Considerations

- **Disclaimer**: Phishing simulations should be conducted in controlled environments only, with participant consent if done outside the lab.
- **User Privacy**: Protect user data by anonymizing results or using simulated accounts.

---

## Project Deliverables

- **Code Repository**: Include configuration scripts, GoPhish settings, and any code used in campaign setup.
- **Documentation**: Provide a README detailing each step, from installation to analysis.
- **Analysis Report**: Offer a sample report or template for documenting findings from a phishing simulation campaign.

---

This project demonstrates technical skills and a cybersecurity mindset with respect to user education and ethical considerations.
