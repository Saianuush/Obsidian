# Raspberry Pi 4B + Ubuntu Server — Day 1 Setup

**Date:** 15 September 2026

## 🎯 Goal

Set up the Raspberry Pi 4B as a headless robotics/computing machine using Ubuntu Server, Ethernet, SSH, C++, and eventually ROS 2 and a Raspberry Pi Camera.

---

# 1. Hardware Setup

- Raspberry Pi 4 Model B — 8GB RAM
- microSD card
- USB-C power supply
- Ethernet cable
- Windows laptop/PC
- Desktop monitor
- USB keyboard
- Raspberry Pi Camera — future setup

### Initial Physical Setup

For the initial Ubuntu setup and troubleshooting, the Raspberry Pi was connected directly to:

- 🖥️ Desktop monitor
- ⌨️ USB keyboard
- 🌐 Ethernet cable
- 🔌 USB-C power supply
- 💾 microSD card

The monitor and keyboard were used to verify the Ubuntu boot process and log into the Raspberry Pi locally.

After SSH was successfully configured, the Raspberry Pi could be controlled remotely from the Windows computer.

---

# 2. Operating System

Installed:

```text
Ubuntu 26.04.1 LTS
GNU/Linux 7.0.0-1017-raspi
aarch64
```

The Pi is running the 64-bit ARM version of Ubuntu Server.

---

# 3. First Boot

### Steps

1. Flashed Ubuntu Server 26.04 LTS to the microSD card using Raspberry Pi Imager.
2. Inserted the microSD card into the Raspberry Pi.
3. Connected the Raspberry Pi to the desktop monitor.
4. Connected a USB keyboard.
5. Connected Ethernet.
6. Connected the USB-C power supply.
7. Raspberry Pi automatically booted.
8. Verified Ubuntu was booting successfully using the monitor.
9. Logged into Ubuntu locally using the keyboard.

### LED observations

- 🔴 Red LED → solid
- 🟢 Green ACT LED → faint periodic blinking

The green LED activity indicated SD-card activity.

---

# 4. Network Setup

The Raspberry Pi was connected to the router using Ethernet.

The Windows computer was connected to the same network through Wi-Fi.

Initial attempt:

```powershell
ssh Saianuush@ubuntu.local
```

This failed because Windows could not resolve:

```text
ubuntu.local
```

Used:

```powershell
arp -a
```

to inspect devices on the local network.

The Raspberry Pi was eventually identified with the IP:

```text
192.168.0.113
```

---

# 5. Testing SSH

Tested whether SSH was available:

```powershell
Test-NetConnection 192.168.0.113 -Port 22
```

Then connected using:

```powershell
ssh saianuush@192.168.0.113
```

Successfully received:

```text
Welcome to Ubuntu 26.04.1 LTS
```

and reached:

```text
saianuush@Saianuush:~$
```

### Result

SSH is working successfully.

The Raspberry Pi can now be controlled remotely from the Windows computer without requiring the monitor or keyboard.

---

# 6. Current Headless Setup

```text
Windows Computer
      │
      │ SSH
      ▼
Raspberry Pi 4B
      │
      ├── Ubuntu Server 26.04.1 LTS
      ├── C++
      ├── Python
      └── Future ROS 2
```

The monitor and keyboard were only needed for the initial physical setup and troubleshooting.

The intended setup is now:

```text
Windows Computer
      │
      │ SSH
      ▼
Raspberry Pi 4B
      │
      └── Ethernet → Router
```

---

# 7. Checking C++ Compiler

Ran:

```bash
g++ --version
```

Output:

```text
g++ (Ubuntu 15.2.0-16ubuntu1) 15.2.0
```

Therefore, the C++ compiler was available and working.

---

# 8. Creating a Workspace

Checked the home directory:

```bash
ls
```

Initially attempted:

```bash
cd temp
```

This returned:

```text
-bash: cd: temp: No such file or directory
```

Created the directory:

```bash
mkdir temp
```

Entered it:

```bash
cd temp
```

Checked the contents:

```bash
ls
```

---

# 9. C++ Hello World

Created the C++ source file:

```bash
nano hello.cpp
```

Program:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello World" << std::endl;
    return 0;
}
```

Compiled:

```bash
g++ hello.cpp -o hello
```

Executed:

```bash
./hello
```

Output:

```text
Hello World
```

### Result

Successfully compiled and executed a C++ program directly on the Raspberry Pi.

---

# 10. Shutting Down the Raspberry Pi

Learned that the Raspberry Pi should not normally be powered off by simply unplugging the USB-C power supply while Ubuntu is running.

Proper shutdown:

```bash
sudo shutdown now
```

Alternative:

```bash
sudo poweroff
```

After the Pi has completely shut down, the USB-C power supply can be disconnected.

---

# 11. Turning the Raspberry Pi Back On

The Raspberry Pi 4B does not require a traditional power button.

To turn it on:

1. Connect the USB-C power supply.
2. The Pi automatically starts booting.
3. Wait for Ubuntu to start.
4. Connect through SSH from the Windows computer.

Example:

```powershell
ssh saianuush@192.168.0.113
```

The IP address may change depending on the router's DHCP assignment.

---

# 12. Important Commands Learned

## Linux Navigation

List files:

```bash
ls
```

Enter a directory:

```bash
cd <directory>
```

Create a directory:

```bash
mkdir <directory>
```

---

## C++

Check compiler:

```bash
g++ --version
```

Compile:

```bash
g++ hello.cpp -o hello
```

Run executable:

```bash
./hello
```

---

## Networking

Check network interfaces/IP addresses:

```bash
ip addr
```

From Windows, view local network devices:

```powershell
arp -a
```

Test SSH port:

```powershell
Test-NetConnection 192.168.0.113 -Port 22
```

Connect to Raspberry Pi:

```powershell
ssh saianuush@192.168.0.113
```

---

## Shutdown

```bash
sudo shutdown now
```

or:

```bash
sudo poweroff
```

---

# 13. Current Status

| Component | Status |
|---|---|
| Raspberry Pi 4B 8GB | ✅ Working |
| Ubuntu Server 26.04.1 LTS | ✅ Installed |
| 64-bit ARM | ✅ Working |
| Ethernet | ✅ Working |
| SSH | ✅ Working |
| Windows → Pi remote terminal | ✅ Working |
| Desktop monitor → Pi | ✅ Tested |
| Keyboard → Pi | ✅ Tested |
| g++ | ✅ Installed |
| C++ compilation | ✅ Working |
| C++ execution | ✅ Working |
| Hello World | ✅ Completed |
| Headless operation | ✅ Ready |

---

# 14. Future Work 🚀

## Phase 1 — Raspberry Pi Camera

### Goal

Connect the Raspberry Pi Camera directly to the Raspberry Pi and make it work under Ubuntu Server.

Planned workflow:

```text
Raspberry Pi Camera
        ↓
Raspberry Pi 4B
        ↓
Ubuntu Server
        ↓
Camera Detection
        ↓
Capture Image
        ↓
Save Image
        ↓
Live Camera Stream
```

### Tasks

- [ ] Connect Raspberry Pi Camera to the CSI camera connector
- [ ] Check whether Ubuntu detects the camera
- [ ] Install/configure required camera software
- [ ] Test camera detection
- [ ] Capture a still image
- [ ] Save an image to the Raspberry Pi
- [ ] Capture continuous frames
- [ ] Test camera FPS
- [ ] Access the camera remotely from the Windows computer

---

# 15. Phase 2 — C++ + Camera

After getting the camera working:

```text
Camera
   ↓
Image Capture
   ↓
C++
   ↓
OpenCV
   ↓
Image Processing
```

### Planned experiments

- [ ] Capture camera frames using C++
- [ ] Read image dimensions
- [ ] Resize images
- [ ] Convert color spaces
- [ ] Edge detection
- [ ] Image saving
- [ ] Basic image processing
- [ ] Measure FPS

---

# 16. Phase 3 — ROS 2

After the camera is working:

```text
Raspberry Pi 4B
       │
       ├── Ubuntu Server 26.04
       ├── ROS 2
       ├── C++
       ├── Python
       └── Raspberry Pi Camera
```

### ROS 2 learning plan

- [ ] Install ROS 2
- [ ] Create a ROS 2 workspace
- [ ] Learn ROS 2 nodes
- [ ] Learn topics
- [ ] Learn publishers
- [ ] Learn subscribers
- [ ] Create a basic C++ ROS 2 node
- [ ] Create a basic Python ROS 2 node
- [ ] Publish camera images
- [ ] Subscribe to camera images
- [ ] Learn `rqt`
- [ ] Learn RViz2
- [ ] Eventually visualize data from the Pi on the main computer

---

# 17. Long-Term Robotics Pipeline

The eventual goal is to build a robotics computing pipeline:

```text
                Raspberry Pi 4B
             ┌───────────────────┐
             │   Ubuntu Server   │
             │                   │
Camera ─────►│      ROS 2        │
             │        ↓          │
             │ Image Processing  │
             │        ↓          │
             │ Computer Vision   │
             │        ↓          │
             │       SLAM        │
             │        ↓          │
             │ Navigation        │
             │        ↓          │
             │ Robot Control     │
             └─────────┬─────────┘
                       │
                       ▼
                 Robot Hardware
```

Long-term pipeline:

**Camera → Computer Vision → ROS 2 → SLAM → Navigation → Robot**

---

# 🎯 Day 1 Achievement

> Successfully set up Raspberry Pi 4B 8GB with Ubuntu Server 26.04.1 LTS, connected the Pi to a desktop monitor and keyboard for initial setup, established Ethernet networking and SSH access from Windows, verified the C++ compiler, and successfully compiled and executed a C++ Hello World program.

## Next Milestone

**Raspberry Pi Camera → detect camera → capture first image 📷🤖**