# About
In this project, I will set up Microsoft Sentinel (SIEM) and connect it to a live virtual machine acting as a honey pot. Then, we can observe live attacks (RDP Brute Force) from all around the world. A custom PowerShell script will be used to look up the attackers Geolocation information and plot it on the Azure Sentinel Map.

# Languages Used

- <b>PowerShell</b>

# Utilities Used

- <b>Azure Portal</b>
- <b>GeoLocation API</b>

# Services Used

- <b>Microsoft Sentinel (SIEM)</b>
- <b>Virtual Machines</b>
- <b>Log Analytics Workspaces</b>
- <b>Microsoft Defender for Cloud</b>


# Project Diagram

<img src="https://i.imgur.com/GyduMAk.png" alt="Project Diagram">

# Section One: Virtual Machine Setup

- <b>Create the virtual machine in Azure </b>

<img src="https://i.imgur.com/iRJHrc9.jpg" alt="Create VM">

- <b>Create a new network security group (NSG) with a custom inbound rule that allows all ports. </b>

<img src="https://i.imgur.com/nWnWzke.jpg" alt="Create NSG">

# Section Two: Microsoft Defender for Cloud

- <b>Enable Microsoft Defender for Cloud and apply it to the newly created resource(s). </b>

<img src="https://i.imgur.com/rusf0Vn.jpg" alt="Apply Defender">

- <b>Enable data collection for all events. </b>

<img src="https://i.imgur.com/IcfPz07.jpg" alt="Enable Data Collection">

# Section Three: Log Analytics Workspaces and Microsoft Defender for Cloud

- <b>Create a new workspace and connect your VM. </b>

<img src="https://i.imgur.com/K0McGzV.jpg" alt="Log Analytics Workspaces">

- <b>Add Microsoft Sentinel to your workspace. </b>

<img src="https://i.imgur.com/h0XZdI8.jpg" alt="Add Microsoft Sentinel">
