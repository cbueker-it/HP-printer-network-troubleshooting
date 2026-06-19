**HP Printer Network Troubleshooting**

I documented the troubleshooting process that I used to reconnect an HP LaserJet M29w printer after moving residences with my wife. This project demonstrates printer network troubleshooting, wireless reconfiguration, device validation, and packet capture analysis using `tshark`.

Lab Objectives
- Restore printer connectivity to a wireless network
- Verify printer network configuration
- Confirm printer visibility on the local network
- Access and review the printer web interface
- Use a packet capture analysis tool to test and validate network communication
- Document the troubleshooting process and resolution

Environment
- Ubuntu Linux Desktop
- HP LaserJet M29w
- Spectrum Router
- Google Chrome
- `tshark`

Problem

After moving to a new residence, the printer was no longer connected to the wireless network. As a result, printing services and access to the printer's management interface were unavailable.

Troubleshooting Process

Printer Network Validation

I accessed the printer's embedded web interface and reviewed the network summary page to verify that the device successfully obtained network settings through DHCP.

This confirmed that the printer was connected to the wireless network and had received valid network configuration information.

Image: Printer Network Summary

<img src="images/printer-network-summary-redacted.png" alt="Printer Network Summary" width="700"/>

Printer Web Interface Verification

I opened the printer's web management interface to check its operational status and confirm it could be managed across the network.

This provided confirmation that network communication between the workstation and printer was functioning correctly.

Image: Printer Web Interface

<img src="images/printer-web-interface.png" alt="Printer Web Interface" width="700"/>

Router Device Verification

I reviewed the Spectrum router management portal and confirmed that the printer appeared as an active connected device.

This verified that the printer was successfully joined to the wireless network and visible to other devices on the local network.

Image: Router Device Detection

<img src="images/router-device-detection-redacted.png" alt="Router Device Detection" width="700"/>

Packet Capture Analysis with 'tshark'

I used 'tshark' to capture network traffic between my Ubuntu driver and the printer.

The packet capture confirmed:
- TCP three-way handshake activity
- HTTP GET requests from the workstation
- HTTP 200 OK responses from the printer
- Successful communication between both devices

This provided packet-level validation that network connectivity and printer services were functioning correctly.

Image: TShark Validation

<img src="images/tshark validation bash output.png" alt="TShark Validation" width="700"/>

Skills Practiced
- Network Troubleshooting
- Wireless Device Configuration
- DHCP Validation
- Embedded Web Interface Administration
- TCP/IP Fundamentals
- Packet Capture Analysis
- 'tshark'
- HTTP Communication Analysis
- Technical Documentation

Key Networking Concepts Observed

TCP Three-Way Handshake

The packet capture showed the standard TCP connection process:

SYN
SYN-ACK
ACK

This sequence established a reliable connection between the workstation and printer before data transfer occurred.

HTTP Communication

The capture also showed HTTP GET requests and HTTP 200 OK responses.

This confirmed that the workstation successfully requested information from the printer web interface and that the printer returned the requested content.

DHCP Network Assignment

The printer received its network configuration automatically through DHCP, allowing it to join the network without manual IP configuration.

Lessons Learned
- Network configuration reports provide valuable troubleshooting information.
- Embedded web interfaces can quickly validate printer status and connectivity.
- Router management portals help verify device presence on a network.
- Packet captures provide evidence of successful communication at the protocol level.
- 'tshark' is an effective command-line tool for network troubleshooting and analysis.

Summary

This project demonstrates practical printer troubleshooting and network validation in a home lab environment. It shows how wireless configuration, device management, router verification, and packet capture analysis can be combined to diagnose and validate network-connected devices.

[`Back to GitHub Profile`](https://www.github.com/cbueker-it)
