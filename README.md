# Traffic-Analysis
Using Wireshark to capture login credentials and passwords on a website.

![image](https://github.com/user-attachments/assets/d4aecc66-4b47-4cd2-a847-625deb6bf08f)
# Wireshark Network Analysis Guide

Wireshark is a popular open-source network protocol analyzer that allows users to capture and examine data traveling across a network in real-time. This guide explores the process of capturing login credentials over insecure protocols using Wireshark. **This repository is intended for educational and ethical use only.**


## Introduction
Wireshark can display details of various network protocols, helping users analyze, troubleshoot, and understand network traffic. This repository includes a step-by-step guide on capturing network traffic using Wireshark, with a focus on observing login data through HTTP protocol traffic.

### Key Features:
- Capture data packets on a network
- Inspect network communication between devices
- Analyze insecure protocols for potential security issues
- Practical filtering techniques for data analysis

## Disclaimer
**Unauthorized interception of sensitive data, including login credentials, is illegal. This guide is for educational purposes only and should only be used on networks where you have explicit permission to monitor traffic.**

## Installation
Wireshark is available for:
- Windows
- macOS
- Linux (often pre-installed)

Visit the official [Wireshark Download Page](https://www.wireshark.org/download.html) to install the latest version for your operating system.

## Step-by-Step Guide
Follow these steps to capture network traffic and filter login data over insecure protocols using Wireshark.

### Step 1: Launch Wireshark
- Open Wireshark on your preferred OS and click the red **Start** button to initiate capturing.

### Step 2: Generate Network Traffic
- Using a browser, attempt to log in to an insecure site, I am using a vulnerable site for practical experience/labs valled `http://zero.webappsecurity.com`.
![Screenshot 2024-11-01 000252](https://github.com/user-attachments/assets/642c8f95-470c-4670-94ac-3210068e1532)
![Screenshot 2024-11-01 000412](https://github.com/user-attachments/assets/8ad566d3-c419-465f-8b56-fee1c89d52e4)
![Screenshot 2024-11-01 000839](https://github.com/user-attachments/assets/1d5ff201-4a84-43d3-8e1e-5dd2b905b8fa)
![Screenshot 2024-11-01 000901](https://github.com/user-attachments/assets/38a266d6-741d-4872-921f-0cc8331b5bcb)


### Step 3: View Captured Data
- Return to Wireshark to observe the captured network traffic.
  ![image](https://github.com/user-attachments/assets/72478025-a0b3-4c1e-9920-70b7c720af3d)


### Step 4: Apply a Filter
- Enter a filter for `http` in the search bar to narrow down results.
  ![Screenshot 2024-11-01 001017](https://github.com/user-attachments/assets/de1901e1-0091-4375-a012-d18796617092)


### Step 5: Filter HTTP Methods
- Try filtering for login data by using `GET` and `POST` methods:
  - **GET Method**: `http.request.method == "GET"`
    ![Screenshot 2024-11-01 001128](https://github.com/user-attachments/assets/67c64d78-ce7b-4971-9b91-b315d04e3a98)

  - **POST Method**: `http.request.method == "POST"`
    
![Screenshot 2024-11-01 001305](https://github.com/user-attachments/assets/f49f0eb0-51e9-45e8-87b7-fd5433ea3da7)

### Step 6: Inspect the Form Data
- Locate packets with login information. The username and password may appear in fields like:
  - `user_login`
  - `user_password`
  - You will find the login credentials in the highlighted portions
    
    ![Screenshot 2024-11-01 001813](https://github.com/user-attachments/assets/dc009415-add0-464a-a30f-52399ddae981)


## Filtering Techniques
Use additional Wireshark filtering techniques to enhance your network analysis:
- `http.request` - Shows all HTTP requests
- `http.response` - Shows all HTTP responses
- **Follow TCP Stream** - Right-click on a packet to view a reconstructed stream of data (useful for reading plain text data in sessions).

## Ethical and Legal Considerations
This project demonstrates how easily unencrypted network data can be intercepted. This information is provided to raise awareness of potential security weaknesses, such as unencrypted HTTP protocols, and to underscore the importance of using secure, encrypted protocols (e.g., HTTPS, SSH).

**Never use this tool for unauthorized data interception.** Ethical use of Wireshark includes:
- Testing on networks where you have permission
- Using it to diagnose and troubleshoot network issues
- Educating others on secure network practices

For safe, ethical testing environments, consider using virtual labs, such as:
- [Hack The Box](https://www.hackthebox.eu)
- [TryHackMe](https://tryhackme.com)

## Contributing
Contributions to this guide are welcome. Please submit a pull request or open an issue for discussion.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
