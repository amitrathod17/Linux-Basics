# Problem

## Linux User Data Transfer
Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus App Server 3 at the /home/usersdata location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:


Locate all files (excluding directories) owned by user anita within the <b>/home/usersdata</b> directory on App Server 3. Copy these files while preserving the directory structure to the <b>/beta</b> directory.<b></b>


# Solution
    
    ssh user1@stapp01

    Step 1: Locate all files owned by anita
    
    find /home/usersdata -type f -user anita

## Explanation

   - find: the command to search for <b>files or directories.</b>

   - /home/usersdata: the directory to search inside.

   - -type f: look only for files (ignore directories).

   -  -user anita: only show files owned by user anita.

Step 2: Copy those files to /beta while preserving the directory structure

We'll combine find with cp --parents.

Here’s the full command:

      find /home/usersdata -type f -user anita -exec cp --parents {} /beta \;

## Explanation

- -exec ... \;: runs a command (cp) on each file found.

- cp --parents {}: copies each file and its folder path (structure) from /home/usersdata.

- /beta: this is the target folder where the files will be copied.

So, if a file is:

      /home/usersdata/project1/file1.txt

It will be copied to:
      
      /beta/home/usersdata/project1/file1.txt

## Permissions Note:
Make sure:

- You are running the command as a user with enough permission to read from /home/usersdata and write to /beta.

- If not, prefix the commands with sudo, like this:

      sudo find /home/usersdata -type f -user anita -exec cp --parents {} /beta \;

# Dry Run

Great question! As a beginner, it's smart to ask this.

---

### 🔍 **What is a “dry run”?**

A **dry run** means:

> "Simulate the action **without actually doing it**."

In your case, it means:

* You **preview** which files will be copied
* But you **don’t copy anything yet**

This helps avoid mistakes like:

* Copying the wrong files
* Overwriting data
* Wasting time/resources

---

### ✅ **Why is a dry run helpful here?**

You're about to:

* Copy many files
* Preserve folder structure
* Use a powerful command (`find` + `cp --parents`)

Mistakes can be:

* Hard to undo
* Messy to clean up

So, a dry run:

* Gives you confidence that the command works
* Shows what files match your search
* Lets you fix problems before copying

---

### 🧪 **How to do a dry run**

Run just the `find` command first. This doesn’t copy anything — it only **shows** what will be copied:

```bash
find /home/usersdata -type f -user anita
```

If the output looks like the correct files, then proceed to use the `cp` command.

---

### ✅ BONUS TIP – Test with `echo` instead of `cp`

To simulate the full command **without copying**, you can do:

```bash
find /home/usersdata -type f -user anita -exec echo cp --parents {} /beta \;
```

What it does:

* Instead of actually copying, it prints what **would be** copied.

Example output:

```
cp --parents /home/usersdata/project1/file1.txt /beta
cp --parents /home/usersdata/project2/file2.txt /beta
```

✅ Now you’re 100% sure what will happen — safely.

---

### 🚀 Once it looks right, run the real command:

```bash
sudo find /home/usersdata -type f -user anita -exec cp --parents {} /beta \;
```

Let me know if you'd like help making this into a script or understanding each part better!

