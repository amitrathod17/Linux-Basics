# Problem

##  Custom Apache User Setup
Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.

Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

# Solution

        ssh user@stapp01
        ssh user@stapp02
        ssh user@stapp03

        # chatgpt solution

        To disable direct SSH login for the root user, follow these steps carefully. This is a common DevOps security practice to prevent unauthorized access to your system.

        🔐 Why Disable Root SSH Login?
        The root user has full control over the system.

        If someone brute-forces or guesses the root password, they gain total access.

        Disabling direct root login forces users to login as a normal user first, then use sudo.

        ✅ Step-by-Step: Disable SSH Login for Root
        🖥️ Step 1: Open the SSH configuration file
        bash
        Copy
        Edit
        sudo nano /etc/ssh/sshd_config
        🔍 Step 2: Find this line
        bash
        Copy
        Edit
        #PermitRootLogin yes
        🔁 Change it to:

        bash
        Copy
        Edit
        PermitRootLogin no
        💡 Note: If the line is commented (# at the start), remove the # to enable the setting.

---

## Step 4: Restart SSH service to apply changes

        sudo systemctl restart sshd

## Step 5: Test It
#### Try to SSH into the server as root from another terminal or system:

        ssh root@your-server-ip

You should get: 
        
        Permission denied

## Best Practice:

- Create a normal user (e.g., devopsuser)
- Add them to the sudo group:

        sudo useradd -m devopsuser
        sudo passwd devopsuser
        sudo usermod -aG sudo devopsuser

Now, login as devopsuser, then use:

        sudo <command>

---

### How to Know Who the Root User Is on a Linux Server
In Linux, the root user is always the user with user ID (UID) 0.
There is always only one root account, even if multiple users have sudo privileges.

### 1. Check who is currently logged in as root
        whoami
        
        If this returns root, then you are currently the root user.

### 2. List all users and identify root
You can check the /etc/passwd file:

        grep ':0:' /etc/passwd
        
        This will return something like:

        root:x:0:0:root:/root:/bin/bash

### Explanation:

- root is the username

- 0:0 means UID 0 and GID 0 (Group ID)

This confirms root is the superuser account

## 3. Check who has sudo privileges
If you're looking for users with admin-like privileges, check the sudo group:

        getent group sudo
or on some systems:

        getent group wheel
This lists users who can run commands as root using sudo.

## Summary
- Command	Purpose
- whoami	Check if you're currently root
- grep ':0:' /etc/passwd	Find the actual root user (UID 0)
- getent group sudo	See who can use sudo (not the same as being root)