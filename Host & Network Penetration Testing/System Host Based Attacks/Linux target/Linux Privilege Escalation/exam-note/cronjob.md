

Here are the summarized steps from the document in bullet points:

**Step 1:** There's a "message" file in the student user's home directory, but only the root user has permissions to access it. Check the permissions: `ls -l`.

**Step 2:** Search for a file with the same name ("message") on the system: `find / -name message`.

**Step 3:** Discover that a file with the same name is present in the /tmp directory, and it's overwritten every minute: `ls -l /tmp/`.

**Step 4:** Identify a script or binary that's copying the file from the student's home directory to /tmp. Use the `grep` command to locate it by searching for the destination path in potential directories. Find a match in the /usr directory: `grep -nri "/tmp/message" /usr`.

**Step 5:** Check the permissions on this script file and its contents: `ls -l /usr/local/share/copy.sh` and `cat /usr/local/share/copy.sh`.

**Step 6:** Realize that the script file is writable by the current "student" user and can be modified to execute privileged operations as it's executed by a root cron job.

**Step 7:** Use `printf` to replace the original code with lines that add an entry to the sudoers file, allowing the student user to use `sudo` without a password prompt: `printf '#! /bin/bash\necho "student ALL=NOPASSWD:ALL" >> /etc/sudoers' > /usr/local/share/copy.sh`.

**Step 8:** Check the current sudoers list: `sudo -l`.

**Step 9:** There are no new entries, so wait for one minute (the cron job runs every minute) and check the sudoers list again.

**Step 10:** After waiting for a minute, the new entry should be present. Switch to the root user using `sudo`: `sudo su`.

**Step 11:** Collect the flag from the root directory: `cd /root`, `ls -l`, and `cat flag`. The flag is revealed: 697914df7a07bb9b718c8ed258150164.

These steps outline the process of exploiting a cron job to gain privileged access and retrieve the flag from the root directory.