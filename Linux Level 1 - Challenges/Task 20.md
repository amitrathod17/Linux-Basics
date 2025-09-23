# Problem

##  Install SELinux packages

Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. To initiate testing, the following requirements have been established for App server 2 in the Stratos Datacenter:


Install the required SELinux packages.

Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.

No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.

Disregard the current status of SELinux via the command line; the final status after the reboot should be disabled.

# Solution

First know what distro you using to find the packages

        cat /etc/os-release/

        AME="CentOS Stream"
        VERSION="9"
        ID="centos"
        ID_LIKE="rhel fedora"
        VERSION_ID="9"
        PLATFORM_ID="platform:el9"
        PRETTY_NAME="CentOS Stream 9"
        ANSI_COLOR="0;31"
        LOGO="fedora-logo-icon"
        CPE_NAME="cpe:/o:centos:centos:9"
        HOME_URL="https://centos.org/"
        BUG_REPORT_URL="https://issues.redhat.com/"
        REDHAT_SUPPORT_PRODUCT="Red Hat Enterprise Linux 9"
        REDHAT_SUPPORT_PRODUCT_VERSION="CentOS Stream"


        sudo yum install selinux*

Check the status of SElinux

        sudo sestatus
<b>Output</b>    SELinux status:                 disabled

Now
    cat /etc/selinux/config

There are 3 options avialble check the appropriate and edit
By using vi editor diable the enforcing property.

    sudo vi /etc/selinux/config

Verfity agian

    cat /etc/selinux/config


     This journey helped me build a strong foundation in Linux – from essential commands and file systems to permissions and process management.

    Next step: diving deeper into system administration and DevOps tools!