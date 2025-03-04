# Change-NIC-IP-address
Change NIC IP Address on Windows 10.

![image](https://github.com/user-attachments/assets/cd406bae-7ca5-4954-8c26-7b7e1a5ebedf)

# What is a NIC?
A Network Interface Card (NIC) is a critical hardware component that enables a device to connect to a network and exchange data. NICs can either be integrated into the motherboard or installed as separate expansion cards, offering connectivity through wired or wireless means.

# Why Should You Change the NIC IP Address in Windows 10?
Modifying the IP address assigned to your NIC can be necessary in several situations, such as:

## Assigning a Static IP Address
Devices like printers, servers, or gaming consoles often require a fixed IP address for reliable communication.

## Resolving Network Problems
Changing the IP address can help fix issues like IP conflicts where two devices share the same IP.

## Connecting to Specific Networks
Certain networks may require devices to use an IP address within a specific range to gain access.

## Enhancing Privacy and Security
Altering your IP address can reduce the chance of being tracked or monitored online.

## Testing Network Configurations
IT professionals and developers often need to change IP addresses for troubleshooting or testing purposes.

# How to Check Your Current NIC IP Address?
Before making changes to your NIC’s IP address, it’s helpful to know the current configuration. Follow these steps:

## Open Command Prompt
Press Win + R, type cmd, and hit Enter.

## Run the IP Configuration Command
Enter the following command and press Enter:

```
ipconfig
```

## Locate the IP Address
Look under the section for Ethernet adapter or Wi-Fi adapter. The value next to IPv4 Address is your current IP address.

# How to Change the NIC IP Address on Windows 10
There are multiple ways to modify your NIC IP address, including using Settings, the Control Panel, Command Prompt, or PowerShell.

## Method 1: Through the Settings App
The Settings app is the most user-friendly method for changing the IP address.

### Access Network Settings
Press Win + I to open Windows Settings.
Go to Network & Internet > Status.
Click Change adapter options under the Advanced network settings section.

### Open NIC Properties
Right-click your active network adapter (Ethernet or Wi-Fi) and select Properties.

### Edit IPv4 Settings
Highlight Internet Protocol Version 4 (TCP/IPv4) and click Properties.

### Set a Static IP Address
Select Use the following IP address and input:
- IP Address: Enter your desired IP (e.g., 192.168.1.100).
- Subnet Mask: Typically 255.255.255.0 for home networks.
- Default Gateway: Enter your router’s IP (e.g., 192.168.1.1).

### Configure DNS Servers (Optional)
- Preferred DNS: Use your router’s IP (e.g., 192.168.1.1) or a public DNS like Google’s (8.8.8.8).
- Alternate DNS: Add a secondary DNS (e.g., 8.8.4.4).

### Save Changes
- Click OK and close all windows.
- Restart the network adapter if necessary.

## Method 2: Using the Control Panel
Another way to change your NIC IP address is through the Control Panel.

### Open Network and Sharing Center
Press Win + R, type control, and hit Enter.
Navigate to Network and Sharing Center and click Change adapter settings.

### Access Adapter Properties
Right-click your active network adapter and choose Properties.

### Modify IPv4 Settings
- Highlight Internet Protocol Version 4 (TCP/IPv4) and click Properties.
- Follow the same steps as in Method 1 to set a static or dynamic IP.

## Method 3: Via Command Prompt
For advanced users, the Command Prompt offers a quick way to reconfigure the NIC IP address.

### Open Command Prompt with Admin Privileges
Press Win + S, type cmd, right-click Command Prompt, and select Run as administrator.

### Identify Your Network Interface
Run this command to see all the network interfaces:

```
netsh interface ipv4 show config
```

Note the name of the interface you want to modify (e.g., Ethernet or Wi-Fi).

### Set a Static IP Address
Use the following command to assign a new IP:

```
netsh interface ipv4 set address name="Ethernet" static 192.168.1.100 255.255.255.0 192.168.1.1
```

- Replace 192.168.1.100 with your desired IP.
- Replace 255.255.255.0 with your subnet mask.
- Replace 192.168.1.1 with your default gateway.

### Configure DNS Settings (Optional)
- Use this command to set DNS servers:

```
netsh interface ipv4 set dns name="Ethernet" static 8.8.8.8
```

## Method 4: Using PowerShell
PowerShell is a modern alternative to the Command Prompt for managing network interfaces.

### Launch PowerShell as Admin
Press Win + X and select Windows PowerShell (Admin).
### Find Your NIC Name
Run this command to see all network interfaces:

```
Get-NetIPAddress
```

### Assign a New IP Address
Use this command to set a static IP:

```
New-NetIPAddress -InterfaceAlias "Ethernet" -IPAddress 192.168.1.100 -PrefixLength 24 -DefaultGateway 192.168.1.1
```

- Replace "Ethernet" with your NIC name.
- Replace 192.168.1.100 with your desired IP.
- Use 24 as the prefix length for a subnet mask of 255.255.255.0.

### Set DNS Servers
Configure DNS servers with this command:

```
Set-DnsClientServerAddress -InterfaceAlias "Ethernet" -ServerAddresses 8.8.8.8,8.8.4.4
```

# Need Reliable Proxy IPs?
If you’re looking to manage IPs with ease or access a wide range of addresses, consider using MacroProxy:

- Large IP Pool: Gain access to IPs from diverse locations worldwide.
- Fast and Reliable: Our servers ensure seamless and stable connections.
- 24/7 Support: Get expert assistance whenever you need it.

With these methods, you can easily modify your NIC IP address in Windows 10 to meet your specific networking needs.
