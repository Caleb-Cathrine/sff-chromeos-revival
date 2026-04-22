# HP SFF Revitalization: ChromeOS Flex Deployment

A technical guide on repurposing legacy Small Form Factor (SFF) hardware into a modern, high-speed workstation for Web Development and Data Analysis.

## 💻 Hardware Profile
* **Model:** HP Compaq Elite SFF
* **CPU:** Intel Core 2 Duo
* **RAM:** 8GB DDR3
* **Storage:** 500GB HDD

## 🛠️ The Build Process

### 1. Advanced Media Creation
Standard automated tools often encounter 404 errors or network timeouts. To ensure a stable installation, I used a manual flashing method:
* **Image:** Downloaded the official ChromeOS Flex `.bin` recovery image.
* **Flashing:** Utilized **Rufus** to write the image to a 16GB USB drive. 
* **Partitioning:** Selected the MBR partition scheme to ensure compatibility with the HP legacy BIOS.

### 2. BIOS & Boot Configuration
* Accessed the Startup Menu using `Esc` and navigated to Boot Device Options (`F9`).
* Configured the system to boot from the USB Hard Drive.
* Verified hardware compatibility (Keyboard, Mouse, and Monitor) in the "Try it First" live environment.

### 3. Network Workaround (The Android Handshake)
**The Challenge:** The machine lacked internal Wi-Fi, and the legacy TRENDnet dongle was not natively supported by the kernel during setup.
**The Solution:** I utilized **Android USB Tethering**. By connecting a smartphone via USB and sharing the mobile data connection, I successfully bypassed the network requirement to complete the Google Account synchronization and OS installation.

### 4. Final OS Installation
* Performed a clean, destructive installation to the internal 500GB HDD.
* Configured the "Owner" profile with a secure Device PIN.
* Enabled **Guest Mode** to allow for shared family browsing and printing without compromising the main developer environment.

## 📸 Gallery
*(Upload your photos to a folder named 'screenshots' in this repo to display them here)*

| Setup Phase | Final Result |
| :--- | :--- |
| ![Account Setup](screenshots/setup_screen.jpg) | ![Desktop View](screenshots/final_desktop.jpg) |

## 🚀 Post-Install Optimization
* **Linux Development Environment:** Enabled to support VS Code and Python.
* **Performance:** Boot times reduced from 2+ minutes (Windows) to ~15 seconds.
* **Security:** Sandboxed architecture with automatic background updates.
