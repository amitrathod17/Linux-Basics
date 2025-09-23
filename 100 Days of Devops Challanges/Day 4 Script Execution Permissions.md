# Problem

## Day 4: Script Execution Permissions

In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 1 within the Stratos Datacenter.


Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 1. Additionally, ensure that all users have the capability to execute it.

# Solution

To grant **execute permission** for **all users**, you should use:

```bash
chmod +x /tmp/xfusioncorp.sh
```

Or more explicitly for **all users (owner, group, others)**:

```bash
chmod a+x /tmp/xfusioncorp.sh
```

---

### 🔍 Final Check:

You can confirm the permissions with:

```bash
ls -l /tmp/xfusioncorp.sh
```

Expected output should show something like:

```
-rwx--x--x 1 root root 40 Aug  7 07:05 /tmp/xfusioncorp.sh
```

or

```
-rwxr-xr-x 1 root root 40 Aug  7 07:05 /tmp/xfusioncorp.sh
```

---
