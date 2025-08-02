Following from 45 mints

Here's a well-organized, formatted version of your notes, structured for easier reading and practice:

---

# 🐧 **Linux Fundamentals & Basic Commands Reference Guide**

---

## I. **Linux Overview**

* **Linux = Kernel**
* Websites to Explore:

  * [GNU](https://www.gnu.org/)
  * [Linux Distributions](https://linuxdistro.org/)
  * [Linux Kernel](https://kernel.org/)
  * [Apache](https://apache.org/)

### 🔹 Kernel Version Example:

* **Example:** `2.6.18`
* `uname -a` gives:

  * OS (Linux)
  * FQDN (Fully Qualified Domain Name)
  * Kernel Version → **2.6 = Major**, **.18 = Minor**
  * Anything after `.18` = Patch version
  * Compilation date and time

---

## II. **Linux Versions & Platform Support**

### 🔹 RHEL Versions:

| Version      | CPU Support     | Virtual Guests |
| ------------ | --------------- | -------------- |
| **Basic**    | 2 Physical CPUs | Up to 4        |
| **Advanced** | Unlimited CPUs  | Unlimited      |

> ⚠️ Limitations apply to native RHEL virtualization, **not** 3rd-party (e.g., VMWare)

### 🔹 Supported Platforms:

* Intel (32/64-bit)
* AMD (32/64-bit)
* IBM POWER, z-series, S/390

> 🧠 **Note:** Memory limitations depend on hardware.

### 🔹 Use Cases:

* **Minimal Server:** RHEL Basic
* **File & Print Server**
* **Web Server**
* **Infrastructure Server:** DHCP, DNS, Proxy
* **Application Server:** Apache Tomcat, JBOSS, Weblogic
* **Database Server:** MySQL, PostgreSQL, Oracle
* **Clustering**

---

## III. **Basic Linux Commands**

### 🔸 Terminal Info

* `tty` – Show current terminal
* `whoami` – Current logged-in user
* `pwd` – Show current working directory
* `cd` – Change directory

  * `cd` or `cd ~` – Home
  * `cd /` – Root
  * `cd ..` – One level up
  * `cd ../../` – Two levels up

### 🔸 Path & Variables

* `echo` – Print output

  * `echo $PATH` – Show system path
  * `echo $PWD` – Current dir
  * `echo $OLDPWD` – Previous dir
* `set` – Show/set shell variables

### 🔸 File & Directory Listing

* `ls` – List contents

  * `ls /` – Root directory
  * `ls -l` – Long format
  * `ls -ld /etc` – Directory properties
  * `ls -ltr` – Sort by time (old → new)
  * `ls -a` – Show hidden files
  * `ls ???` – Match 3-character names
  * `ls a*` – Starts with ‘a’
* `stat filename` – File attributes

---

## IV. **File Manipulation**

### 🔸 Reading/Writing Files

* `cat file` – Show file content

  * `cat file1 file2 > newfile` – Merge files
  * `>>` – Append to file
* `more` / `less` – Paginate output
* `head file` – Start lines
* `tail file` – End lines
* `wc -l file` – Line count

### 🔸 Create/Edit Files

* `touch file` – Create empty file
* `touch -t 200801091530 file` – Modify timestamp

### 🔸 File Management

* `mkdir dir` – Create directory

  * `mkdir -p a/b/c` – Nested
* `cp src dest` – Copy

  * `cp -v` – Verbose
* `mv old new` – Move/rename
* `rm file` – Remove file

  * `rm -rf dir/` – Recursive and force

---

## V. **Navigation & Shortcuts**

### 🔸 Navigation

* ↑ / ↓ – Browse command history
* Tab – Auto-complete command/file

### 🔸 Copy & Paste (GNOME Terminal)

* Copy: Left click drag / `Ctrl+C`
* Paste: Right click / `Ctrl+Shift+V`

---

## VI. **Advanced Features**

### 🔸 Redirection

* Input: `cat < file.txt`
* Output: `command > file.txt`
* Append: `command >> file.txt`

### 🔸 Pipes

* `|` – Pass output as input to next

  * `cat file | sort`
  * `cat file1 file2 | sort | grep pattern`

### 🔸 Command Chaining

* `command1 ; command2` – Run both, regardless of success
* `command1 && command2` – Run second if first succeeds
* `command1 || command2` – Run second if first fails

---

## VII. **User & Search Tools**

* `su` – Switch user (default to root)
* `find / -name filename` – Search files
* `file filename` – Check file type
* `alias` – View/create aliases

  * `alias copy='cp -v'`

---

## VIII. **Special Tools**

* `seq 1000 > file.txt` – Sequence numbers 1–1000
* `history` – Show command history

  * `!690` – Run 690th command
  * Stored in `~/.bash_history`

---

## 🧠 Tips

* Files starting with `.` (dot) are **hidden** (e.g., `.bashrc`)
* `~` = User's home directory

---
