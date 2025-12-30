# Kali-VM-Configuration-Performance-Optimization-
Eliminate UI lag and mouse stutter


Windows Host Config
Power Plan: Set to "Best Performance" while plugged in.

Core Isolation: Start > Search "Core Isolation" > Turn Memory Integrity OFF. (Reboot required).

Windows Features: Uncheck the following in "Turn Windows features on or off":

Hyper-V

Virtual Machine Platform

Windows Hypervisor Platform

VM Settings
Processors: 1 Processor, 4 Cores.

Memory: 4GB - 8GB.

Display:

Accelerate 3D Graphics: Checked

Graphics Memory: 1 GB (Do not use "Recommended" 8GB)

Monitors: Use host setting for monitors

Compatibility: Manage > Change Hardware Compatibility > Workstation 17.x.

Advanced: Options > Advanced > Uncheck "Enable side channel mitigations for Hyper-V enabled hosts".

Virtualization: Hardware > Processors > Check "Virtualize Intel VT-x/EPT".

Post-Install (Inside Kali)
Run the following to install proper drivers and resizing tools:

Bash

sudo apt update
sudo apt install -y open-vm-tools-desktop
reboot
Runtime Priority Adjustment
If lag persists, force Windows to prioritize the VM over background tasks:

Open Task Manager (Ctrl+Shift+Esc).

Go to Details.

Right-click vmware-vmx.exe (highest RAM usage).

Set Priority -> High.
