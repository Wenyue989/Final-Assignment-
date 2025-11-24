# Standard Operating Procedure (SOP)
### How to Connect to a Secured Wi-Fi Network Using Manual Configuration (Windows 11)

---

**Version:** `1.0`    
**Group Members:** _Name1, Name2, Name3,Name4_  
**Date:** `YYYY-MM-DD`

---

##  Approval Table

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Group Member | Contributor | — | — |
| Group Member | Contributor | — | — |
| Group Member | Contributor | — | — |
| Group Member | Contributor | — | — |

---

##  Revision History

| Version | Date | Changes | Author |
|--------|------|---------|--------|
| 1.0 | YYYY-MM-DD | Initial Release | Your Name |

---

##  Purpose

This document provides a standardized process for manually connecting a Windows 10/11 device to a secured Wi-Fi network.  
Manual configuration is used when the network is hidden, uses enhanced security, or automatic connection fails.

---

##  Scope

This procedure applies to:

- Students, staff or support personnel
- Windows 11 laptops/desktops
- Networks requiring WPA3/WPA2 authentication or manual configuration

---

##  Objectives

After completing this SOP, the user will be able to:

- Add a Wi-Fi profile manually
- Configure WPA3/WPA2 security
- Enter authentication details
- Verify successful connection

---

##  Definitions

| Term | Meaning |
|------|--------|
| **SSID** | Wireless network name |
| **WPA2/WPA3** | Wi-Fi security encryption standards |
| **PSK** | Pre-Shared Key (Wi-Fi password) |
| **DHCP** | Automatic IP assignment |
| **Static IP** | Manual IP configuration |

---

##  Accountability Matrix

| Role | Responsibility |
|------|--------------|
| End User | Provide correct Wi-Fi credentials |
| IT Technician | Perform configuration |
| Network Administrator | Approve secure Wi-Fi settings |

---

##  Required Information

| Setting | Example |
|---------|---------|
| SSID | `Group-Project-WiFi` |
| Security Type | WPA3-Personal → fallback WPA2 |
| Password | `ProjectSecure2025!` |
| Optional: IP Settings | Provided by admin |

---

##  Procedure

### **Step 1 — Open Wi-Fi Settings**

1. Click **Start**
2. Go to **Settings → Network & Internet → Wi-Fi**

 Screenshot placeholder:  
`![Wi-Fi Settings](images/step1.png)`

---

### **Step 2 — Add a Network**

1. Select **Manage known networks**
2. Click **Add network**

 `![Add Network](images/step2.png)`

---

### **Step 3 — Enter Network Information**

- SSID: `Group-Project-WiFi`
- Security Type: `WPA3-Personal`  
  _(if unsupported → select `WPA2-Personal`)_

 `![Security Type](images/step3.png)`

---

### **Step 4 — Enter Password**

- Enter: `ProjectSecure2025!`
- Check:  `Connect automatically`
- Click: **Save**

 `![Password Screen](images/step4.png)`

---

### **Step 5 — (Optional) Static IP Settings**

If required:

| Field | Value |
|-------|-------|
| IP Address | `192.168.1.120` |
| Mask | `255.255.255.0` |
| Gateway | `192.168.1.1` |
| DNS | `8.8.8.8` |

 `![Static IP](images/step5.png)`

---

###  Step 6 — Connect & Confirm Status

- Click Wi-Fi icon
- Select `Group-Project-WiFi`
- Should display: **Connected, secured**

 `![Connected](images/connected.png)`

---

##  Verification

Run the following command:

```sh
ping google.com

>Expected result:

```sh
Reply from ...
0% packet loss

##  Troubleshooting Guide

If the connection fails or does not work as expected, check the following common issues:

| Symptom | Possible Cause | Solution |
|---------|---------------|----------|
|  Cannot connect to the Wi-Fi network | Password incorrect | Re-enter the Wi-Fi password and ensure case sensitivity |
|  Wi-Fi network not visible | SSID misspelled or network is hidden | Verify spelling or confirm access with network administrator |
|  Connected but no Internet | DNS or IP configuration incorrect | Enable DHCP or manually configure DNS (e.g., `8.8.8.8`) |
|  WPA3 option unavailable | Device or adapter does not support WPA3 | Switch to WPA2-Personal |
|  Connection takes too long | Weak signal or interference | Move closer to the router or remove obstacles |
|  Keeps disconnecting | Poor signal or system roaming settings | Disable roaming sensitivity or test closer to the access point |

flowchart TD
A[Start] --> B[Open Wi-Fi Settings]
B --> C[Add New Network]
C --> D{Security Type Available?}
D -->|WPA3| E[Select WPA3-Personal]
D -->|No WPA3| F[Select WPA2-Personal]
E --> G[Enter Password & Save]
F --> G[Enter Password & Save]
G --> H{DHCP?}
H -->|Yes| I[Connect]
H -->|No| J[Enter Static IP]
J --> I[Connect]
I --> K[Ping Test]
K -->|Success| L[Done]
K -->|Fail| M[Troubleshoot]

flowchart TD
    A[Start] --> B[Collect Wi-Fi Information<br/>(SSID, Security, Password)]
    B --> C[Open Wi-Fi Settings<br/>(Settings → Network & Internet → Wi-Fi)]
    C --> D[Click 'Manage known networks'<br/>then 'Add network']
    D --> E{Is WPA3-Personal Available?}
    E -->|Yes| F[Select WPA3-Personal]
    E -->|No| G[Select WPA2-Personal]
    F --> H[Enter SSID: Group-Project-WiFi<br/>Enter Password: *********]
    G --> H[Enter SSID: Group-Project-WiFi<br/>Enter Password: *********]
    H --> I[Check 'Connect automatically'<br/>Click Save]
    I --> J{Use DHCP?}
    J -->|Yes| K[Connect to Wi-Fi Network]
    J -->|No| L[Enter Static IP,<br/>Subnet, Gateway, DNS]
    L --> K[Connect to Wi-Fi Network]
    K --> M[Open Command Prompt<br/>Run: ping google.com]
    M --> N{Ping Successful?}
    N -->|Yes| O[Done<br/>(Connected & Verified)]
    N -->|No| P[Troubleshoot<br/>(Password / DNS / Signal / WPA3 support)]
