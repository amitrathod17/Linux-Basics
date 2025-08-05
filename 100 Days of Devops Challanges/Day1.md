# Problem

## Day 1: Temporary User Setup with Expiry

To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:

Create a user named anita with a non-interactive shell on App Server 2.

# Solution

        ssh user@stapp02

        useradd -help

        sudo useradd -s /sbin/nologin anita

### To verify

    getent passwd anita

    anita:x:1002:1002::/home/anita:/sbin/nologin
