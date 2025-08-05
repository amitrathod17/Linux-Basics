# Problem

## Linux User Setup with Non-Interactive Shell
To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:

### Create a user named yousuf with a non-interactive shell on App Server 3.

# Solution

        ssh user3@stapp03
        
        useradd --help

        sudo useradd -s /sbin/nologin yousuf

        Check:
        cat /etc/passwd | grep yousuf

        yousuf:x:1002:1002::/home/yousuf:/sbin/nologin

        other users output sample

---


        banner:x:1001:1001::/home/banner:/bin/bas
