# Problem

## Day 3: Temporary User Setup with Expiry

Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.


Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

# Solution

        ssh tony@stapp01

        sudo -i

        vi /etc/ssh/sshd_config

        systemctl restart sshd

        grep PermitRootLogin /etc/ssh/sshd_config

### To verify

    PermitRootLogin no
    the setting of "PermitRootLogin without-password"