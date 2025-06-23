# LAB 1

The system admin team at xFusionCorp Industries has streamlined access management by implementing group-based access control. Here's what you need to do:
a. Create a group named nautilus_developers across all App servers within the Stratos Datacenter.
b. Add the user kano into the nautilus_developers group on all App servers. If the user doesn't exist, create it as well.

groupadd nautilus_developers
sudo useradd -G nautilus_developers  kano

# LAB 2

To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. 
Here's your task:
Create a user named john with a non-interactive shell on App Server 1.
[tony@stapp01 ~]$ sudo useradd -s /sbin/nologin john
