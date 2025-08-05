# Problem

##  Custom Apache User Setup
In response to heightened security concerns, the xFusionCorp Industries security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:


a. Create a user named javed on App server 3 within the Stratos Datacenter.

b. Assign a unique UID 1307 and designate the home directory as /var/www/javed.

# Solution

        ssh user@stapp03

        sudo useradd -u 1307 -d /var/www/javed javed

        check:
        cat /etc/passwd | grep javed
