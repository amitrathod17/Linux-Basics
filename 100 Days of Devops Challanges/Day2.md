# Problem

## Day 2: Temporary User Setup with Expiry

As part of the temporary assignment to the Nautilus project, a developer named john requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:

Create a user named john on App Server 1 in Stratos Datacenter. Set the expiry date to 2024-01-28, ensuring the user is created in lowercase as per standard protocol.

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