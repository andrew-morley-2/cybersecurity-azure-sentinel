# About
In this project, I will set up Microsoft Sentinel (SIEM) and connect it to a live virtual machine acting as a honey pot. Then, we can observe live attacks (RDP Brute Force) from all around the world. A custom PowerShell script will be used to look up the attackers Geolocation information and plot it on the Azure Sentinel Map.

# Languages Used

- <b>PowerShell</b>

# Utilities Used

- <b>Azure Portal</b>
- <b>Geolocation API</b>

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

# Section Four: Geolocation API Setup

- <b>RDP to your honeypot VM. </b>

<img src="https://i.imgur.com/3awy2CD.jpg" alt="VM RDP">

- <b>Open Event Viewer on your VM and find a failed RDP attempt. </b>

<img src="https://i.imgur.com/XLuUFvl.jpg" alt="Event Viewer">

- <b>Create Geolocation API at ipgeolocation.io and add it to PowerShell script. The script will look up the attackers Geolocation information. Run the script. </b>

<img src="https://i.imgur.com/rQOczM6.png" alt="GeoLocation Script">

# Section Five: Custom Logs in Log Analytics Workspaces

- <b>Create a custom log for failed RDP attempts. </b>

<img src="https://i.imgur.com/HPqfIV2.jpg" alt="Create Custom Log">

- <b>Run query on custom log. Select extract fields to refine the raw data. </b>

<img src="https://i.imgur.com/hguNIjS.jpg" alt="Extract Fields">

- <b>Define custom fields one by one for the following: latitude, longitude, destinationhost, username, sourcehost, state, country, timestamp, and label. </b>

<img src="https://i.imgur.com/xWDDoZe.jpg" alt="Custom Fields">

# Section Six: Microsoft Sentinel Setup

- <b>Create new workbook in Microsoft Sentinel based on custom logs and custom fields. </b>

<img src="https://i.imgur.com/TppN6hu.jpg" alt="Create Workbook">

- <b>Add map to workbook based on custom fields. Let PowerShell script run for several hours as attackers around the world attempt to brute force an RDP connection to your VM. </b>

# Section Seven: Results

- <b>Open your workbook in Microsoft Sentinel after several hours have passed and view the map of all the failed RDP attempts based on Geolocation. </b>

<img src="https://i.imgur.com/zGl4vdF.jpg" alt="Geolocation Map">
