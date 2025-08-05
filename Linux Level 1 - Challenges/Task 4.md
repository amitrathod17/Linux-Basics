# Problem

## Service User Creation without Home Directory

In response to the latest tool implementation at xFusionCorp Industries, the system admins require the creation of a service user account. Here are the specifics:


### Create a user named anita in App Server 3 without a home directory.

In response to the latest tool implementation at xFusionCorp Industries, the system admins require the creation of a service user account. Here are the specifics:

Create a user named anita in App Server 3 without a home directory.

# Solution
        ssh user@stapp03
        check whether the user exits using id command

        useradd -- help

        useradd -M anita

# To verify

    cat /etc/passwd | grep anita
    This command will show you the /bin/bash

    So, use
    ls -ld /home/anita (list directories)
    Return: values should be not cannot access `/home/anita`: No such file or directories 

    Input other user id to see the output.

    