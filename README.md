
**Zoe's Collective Template**

This repository is a backup of my templates that I have created and used in my Zabbix environment. These are developed and tested running version 5.4.0alpha2. I primarily use this to monitor my plex instance and libraries that are run through VMWare ESXi. As such, this template can discover newly created virtual machines.

> Files in repository
> - zoe_zbx_template.yaml - This is the default language Zabbix imports and exports in.
> - zoe_zbx_template.json
> - zoe_zbx_template.xml

***Getting Started / How to Use***

 - Download the .yaml file.
 -  In your Zabbix frontend, on the left sidebar navigate to Configuration > Templates.
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
 - Once the import is complete, you will need to fill in the Macros. Navigate to Configuration > Templates then select the template we imported.
 - In here, there is a tab labeled "Macros". You will need to fill in the relative Macros then click 'Update'.

***Finding VMware UUID***
You will need to enable SSH access to your VMware ESXi host. 

 - In the vSphere Client or web client, right click on the host. Select Services > Enable Secure Shell.
 - If you do not have Putty on your machine, right click the host again. There will be an option "Get SSH for Chrome".
 - Once you have done this, SSH into your host and use the following command:
 - `esxcfg-info -u | awk '{print tolower($0)}'`
 - Copy the UUID and exit out of your host.
 - Redo the first step, this time choose disable secure shell.

***What is included in this template?***
*This list is not final and will continue to be added to.*
 - CPU Utilization (Percentage): Item and Triggers
 - CPU Usage (Hz, MHz, GHz): Item
 - ESXi Host memory Usage: Item
 - Filesystem Discovery (Percent and numeric): Items and Triggers.
 - Guest Memory Usage (Numeric): 
 - Memory Max Size (GB): Item
 - Power State: Items and Triggers
 - qBittorrent Version and qBittorrent API version check: Item and Triggers
 - qBittorrent Torrent List: Item - If the torrent queue is empty, there is a custom fail during preprocessing that will write the result as "Torrent queue empty".
 - qBittorrent Connection Status: Item & Trigger
 - qBittorrent Download Speed: Item
 - qBittorrent Amount Downloaded: Item
 - Power State: Items and Triggers
 - Uptime: Item
 - VMware Cluster Discovery
 - VMware Datastore Discovery
 - VMware Hypervisor Discovery - Will sort into host group "Hypervisors")
 - VMware Virtual Machine Discovery - Will sort into host group "Virtual Machines")
 - Windows Services Discovery - Custom overrides are pre-set to filter out annoying Windows background services (looking at you, BITS and OneSync.)