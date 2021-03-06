**Zoe's Collective Template**

This repository is a backup of my templates that I have created and used in my Zabbix environment. These are developed and testing running version 5.4.0alpha2. I primarily use this to monitor my plex instance and libraries that are run through VMWare ESXi. As such, this template can discover newly created virtual machines.

> Files in repository
>  - zoe_zbx_template.yaml - This is the default language Zabbix will import and export in.
> - zoe_zbx_template.json
> - zoe_zbx_template.xml

***Getting Started / How to Use***

 - Download the .yaml file.
 - In your Zabbix frontend, on the left sidebar navigate to Configuration > Templates.
 - On this page, in the top right corner, select 'Import'.
 - Choose the file by clicking "Choose File".
 - You will need to check the following rules:
	 - Groups: Create New
	 - Templates: Update Existing, Create New
	 - Value Mappings: Update Existing, Create New
	 - Template Downloads: Update Existing, Create New
	 - Template Linkage: Create New
	 - Applications: Create New
	 - Items: Update Existing, Create New
	 - Triggers: Update Existing, Create New
	 - Graphs: Update Existing, Create New
	 - Web Scenarios: Update Existing, Create New
 - Click import.

***What is included in this template?***
*This list is not final and will continue to be added to.*
 - CPU Utilization (Percentage): Item and Triggers
 - CPU Usage (read in Hz): Item
 - qBittorrent Version and qBittorrent API version check: Item and Triggers
 - qBittorrent Torrent List: Item
 - qBittorrent Connection Status: Item
 - qBittorrent Download Speed: Item
 - qBittorrent Amount Downloaded: Item
 - VMware Host memory usage: Item
 - VMware Memory Size: Item
 - VMware Power State: Items and Triggers
 - VMware Uptime: Item