# Kali Linux Lab Environment Setup

## Hardware
- MacBook with Apple Silicon (M1)

## Virtualization
- UTM
- Kali Linux ARM64

## Operating System
- Kali Linux
- XFCE Desktop Environment

## Network
- UTM Shared Network
- Internet connectivity verified through both terminal and browser

---

# Kali Linux Setup

## 1. Install Kali Linux

I am using an Apple Silicon Mac, therefore I used the **ARM64 version of Kali Linux** rather than the x86 version.

I initialy attempted to use VirtualBox, but ran into compatibility and graphical environment issues because the VirtualBox setup was designed around an x86 Kali VM. I decided to switch to UTM, which provides a better fit for running an ARM64 Linux VM on Apple Silicon.

### Installation Process
1. Installed UTM
2. Created a new virtual machine
3. Selected **Virtualize**
4. Selected **Linux**
5. Selected the Kali Linux ARM64 ISO
6. Allocated virtual storage and memory
7. Installed Kali Linux
8. Created a Kali user account
9. Configured the virtual disk
10. Completed the Kali installation
11. Booted into the Kali XFCE desktop

---

# Network Configuration

## UTM Network

For networking, I initially looked at the lab instructions, which were written for VirtualBox and required a separate NAT Network.
UTM does not use the same VirtualBox NAT Network configuration.

Instead, I used:
> **Network → Shared**

This seems to provides NAT-style Internet access for the Kali VM.

---

## 🔎 Setup Verification & Testing

### 1. Check network interfaces

```bash
ip addr
```

### 2. Check routing information

```bash
ip route
```

### 3. Test Internet connectivity using an IP address

```bash
ping -c 4 8.8.8.8
```

### 4. Test Internet connectivity and DNS resolution

```bash
ping -c 4 google.com
```

### 5. Test Internet access through Firefox

Open Firefox and type:

```text
https://www.google.com
```
To confirm that Google loads and that I can perform a search

### 6. Test GitHub access through Firefox

Then search for github through the google page opened:
```text
https://github.com
```
To confirm that GitHub loads and that a search can be performed


## ✅ Final Network Verification

| Test | Result |
|---|---|
| Network interface detected | ✅ |
| IP address assigned | ✅ |
| Routing configured | ✅ |
| Internet connectivity | ✅ |
| DNS resolution | ✅ |
| Google accessible | ✅ |
| GitHub accessible | ✅ |
| Firefox Internet access | ✅ |
