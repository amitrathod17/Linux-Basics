# Problem

## Group Creation and User Assignment
The system admin team at xFusionCorp Industries has streamlined access management by implementing group-based access control. Here's what you need to do:

a. Create a group named nautilus_admin_users across all App servers within the Stratos Datacenter.

b. Add the user mohammed into the nautilus_admin_users group on all App servers. If the user doesn't exist, create it as well.

# Solution

        ssh user1@stapp01
        ssh user2@stapp02
        ssh user3@stapp03

        Check whether the user is already exits in the server
        
        id mohammed

        sudo groupadd nautilus_admin_users

        sudo useradd -g nautilus_admin_users mohammed

        check:
        cat /etc/group | grep nautilus_admin_users
        cat /etc/passwd | grep mohammed
