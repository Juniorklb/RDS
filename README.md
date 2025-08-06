
# 🖥️ Remote Desktop Services (RDS) – Windows Server 2022 Project

This project demonstrates how to deploy **Remote Desktop Services (RDS)** using **Windows Server 2022** in a virtual lab environment. It allows multiple users to connect remotely to a centralized server using Remote Desktop Protocol (RDP), simulating enterprise-level access and control.

---

## 📌 Project Overview

| Key Info             | Details                        |
|----------------------|--------------------------------|
| **Project Name**     | Remote Desktop Services (RDS) Setup |
| **Server OS**        | Windows Server 2022             |
| **Virtualization**   | VMware Workstation              |
| **Domain**           | kalomba.local                   |
| **Tools**            | Server Manager, AD DS, RDP      |
| **Goal**             | Centralized remote desktop access for domain users |

---


---

## ⚙️ Prerequisites

- ✅ VMware Workstation or VMware Player installed
- ✅ Windows Server 2022 ISO
- ✅ Domain Controller already configured (`kalomba.local`)
- ✅ Admin privileges on both servers
- ✅ At least two VMs:
  - **DC-01**: Domain Controller
  - **RDS-01**: Remote Desktop Services host

---

## 🧱 Step-by-Step Instructions

### 🧾 Phase 1 – Create and Configure the RDS Virtual Machine

1. **In VMware:**
   - Create a new VM named `RDS-01`
   - Install Windows Server 2022
   - Assign at least 4GB RAM
   - Set static IP (e.g., `192.168.1.20`)
   - Configure DNS to point to your DC-VM IP

2. **Rename the computer:**
   - Open `System Properties` → Change name to `RDS-01`

3. **Join the Domain:**
   - Join to `kalomba.local` and reboot

---

### 🧾 Phase 2 – Install Remote Desktop Services Roles

1. Open **Server Manager** on `RDS-01`

2. Click `Manage` → `Add Roles and Features`

3. Select:
   - Role-based or feature-based installation

4. Select the current server: `RDS-01.kalomba.local`

5. Check:
   - `Remote Desktop Services`

6. Under **Role Services**, check:
   - `Remote Desktop Session Host`
   - `Remote Desktop Licensing`

7. Click **Next** and install  
8. Restart the server when prompted

📸 *Take screenshot of roles being installed and confirmation screen*

---

### 🧾 Phase 3 – Configure Licensing

1. Open **RD Licensing Manager**

2. Right-click the server → `Activate Server`

3. Choose “Automatic connection” and complete the wizard  
   *(You can simulate trial/demo activation if needed)*

4. Open **RD Licensing Diagnoser**
   - Verify that the licensing server is recognized

📸 *Screenshot of RD Licensing Diagnoser window*

---

### 🧾 Phase 4 – Enable Remote Desktop Access

1. Go to `System` → `Remote settings`

2. Enable:  
   - `Allow remote connections to this computer`

3. Add specific users:
   - Click `Select Users`
   - Add domain users or security groups (e.g., `RemoteUsers`)

📸 *Screenshot of RDP access settings and selected users*

---

### 🧾 Phase 5 – Test RDP Connection from Client PC

1. Use another VM (client) or host machine  
2. Open **Remote Desktop Connection** (`mstsc.exe`)

3. Enter:

4. Log in using a domain user (e.g., `user1@kalomba.local`)
   
6. Repeat test with multiple domain users to simulate multiple sessions

📸 *Screenshot of successful remote desktop session*

---

### 🧾 Optional Phase 6 – Publish RemoteApps or Configure RD Web Access

1. Add **RD Connection Broker** and **RD Web Access** roles

2. Use **Server Manager** → Remote Desktop Services → Collections

3. Publish common apps like:
- Notepad
- Calculator
- Paint

4. Access them via:



📸 *Screenshot of RDWeb login page or published apps*

---

## 📸 Screenshots to Include

- ✅ Role Installation Wizard
- ✅ Server Reboot Screen
- ✅ RD Licensing Manager
- ✅ RDP Permissions Settings
- ✅ Successful RDP Session
- ✅ Optional: RD Web Login or RemoteApp Published

---

## 🎯 Project Outcome

> Successfully deployed and tested **Remote Desktop Services** in a lab environment. This includes:
- Remote multi-user access
- Licensing simulation
- Centralized desktop experience for users
- Role-based access control

---

## 📁 Files & Demo

| File / Resource | Description |
|-----------------|-------------|
| `RDS_Project_Windows_Server_2022.pdf` | Final documented report with screenshots |
| `screenshots/` | Folder of step-by-step images |
| `video/` (optional) | Live demo of RDP session |
| `README.md` | This file |

---

## 🔗 Live Demo (Optional)

🎥 Watch the demo: [Link to YouTube or Drive](#)

---

## 👨‍💻 Author

**Junior Kalomba**  
🌐 Portfolio: [https://juniorkalomba.netlify.app](https://juniorkalomba.netlify.app)  
📁 GitHub: [github.com/yourusername](https://github.com/Juniorklb)

---

## 🧠 Skills Demonstrated

- Windows Server 2022 Administration  
- Role and Feature Management  
- RDS Licensing Setup  
- Remote Desktop Access Configuration  
- Basic User Access Testing  
- VMware Lab Environment

---

## 📚 Related Labs

- ✅ [Active Directory + GPO Lab](#)
- ✅ [File Server with Permissions Project](#)
- ✅ [DHCP & DNS Configuration Lab](#)

---

> 🧾 *This lab project strengthens my experience as a system administrator in delivering remote access solutions using Windows Server 2022.*


