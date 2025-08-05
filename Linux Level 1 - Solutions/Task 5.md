# Problem

## Temporary User Setup with Expiry
To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:

### Create a user named yousuf with a non-interactive shell on App Server 3.

# Solution
    
    ssh user1@stapp01

    check whether user exits or not

    useradd --help

    sudo useradd -e 2024-01-28 john

    ## To verify

    sudo chage --help

    sudo chage -l john
 ---
    Last password change                                    : Aug 05, 2025
    Password expires                                        : never
    Password inactive                                       : never
    Account expires                                         : Jan 28, 2024
    Minimum number of days between password change          : 0
    Maximum number of days between password change          : 99999
    Number of days of warning before password expires       : 7