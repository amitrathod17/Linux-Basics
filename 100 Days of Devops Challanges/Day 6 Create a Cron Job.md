# Problem

## Day 6: Create a Cron Job

The Nautilus system admins team has prepared scripts to automate several day-to-day tasks. They want them to be deployed on all app servers in Stratos DC on a set schedule. Before that they need to test similar functionality with a sample cron job. Therefore, perform the steps below:

a. Install cronie package on all Nautilus app servers and start crond service.

b. Add a cron */5 * * * * echo hello > /tmp/cron_text for root user.

---


From what you’ve shown, part **(a)** and part **(b)** both look correct — you did install `cronie`, started `crond` (systemd auto-enabled it during install), and added the cron job for the root user.

---

### ✅ Let’s check each requirement:

**a. Install cronie package on all Nautilus app servers and start crond service**

* `yum install -y cronie` → ✅ done.
* Install log shows:

  ```
  Created symlink /etc/systemd/system/multi-user.target.wants/crond.service → /usr/lib/systemd/system/crond.service.
  ```

  That means the service was enabled & started automatically → ✅ done.

---

\**b. Add a cron */5 \* \* \* \* echo hello > /tmp/cron\_text for root user**

* You switched to `root` via `sudo -i` → ✅ correct user.
* You ran `crontab -e` and added:

  ```
  */5 * * * * echo hello > /tmp/cron_text
  ```

  Then `crontab -l` confirms it’s installed for root → ✅ correct.

---

### 🔍 Things to verify to be 100% sure:

1. **Service running check**:

   ```bash
   systemctl status crond
   ```

   Should show `active (running)`.

2. **File update check**:
   Wait at least 5 minutes, then:

   ```bash
   cat /tmp/cron_text
   ```

   You should see:

   ```
   hello
   ```

   If the cron is working, the timestamp of the file will update every 5 minutes.

---

If you’re doing this for **all Nautilus app servers**, you’ll need to:

* SSH into each (`stapp01`, `stapp02`, `stapp03`).
* Repeat the install + cron setup.

---

If you’d like, I can give you a **one-liner** to push the cron job and install `cronie` on all three app servers in one go from the jump host. That will save you time and avoid missing a server.

# Steps I have used by own

- ssh to the user
- locate which distro is running on the user by cat / etc/os-release
- install the package cronie by sudo yum install -y cronie
- check the status by systemctl status crond
- Move to root account by sud0 -i
- user crontab -e to excute the command
- run the command cat /tmp/cron_text to check the output.
- exit

Made the same changes on the rest of the application users.

