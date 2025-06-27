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


# LAB 3
Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus App Server 3 at the /home/usersdata location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:


Locate all files (excluding directories) owned by user john within the /home/usersdata directory on App Server 3. Copy these files while preserving the directory structure to the /blog directory.

    cd /home/usersdata
    sudo find . -type f -user john -exec cp -p --parents {} /blog \;

# LAB 4
Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.
Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

vi /etc/ssh/sshd_config
PermitRootLogin no
sudo systemctl restart sshd
