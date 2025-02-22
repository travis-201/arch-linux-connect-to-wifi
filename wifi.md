# Connecting to Wi-Fi in the Arch Linux Installer

## Step 1: Check if Your Network Interface is Detected
Run the following command to list available network interfaces:
```bash
iwctl device list
```
Typically, a wireless interface will have a name like `wlan0` or `wlp2s0`.

## Step 2: Start the `iwctl` Utility
Launch `iwctl` (the interactive mode of iwd, Arch’s default wireless management tool):
```bash
iwctl
```

## Step 3: Scan for Available Networks
Inside `iwctl`, run:
```bash
station wlan0 scan
station wlan0 get-networks
```
Replace `wlan0` with your actual Wi-Fi interface name.

## Step 4: Connect to a Wi-Fi Network
To connect to a Wi-Fi network:
```bash
station wlan0 connect "Your_WiFi_Name"
```
- If your network has a password, you will be prompted to enter it.
- If the connection is successful, you should see a confirmation message.

## Step 5: Verify Connection
Exit `iwctl` by typing:
```bash
exit
```
Then, check if you have an IP address:
```bash
ip a
```
Check internet connectivity:
```bash
ping -c 3 google.com
```
If you receive responses, your internet connection is working!
