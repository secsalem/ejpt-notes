

Here are the summarized steps from the document in bullet points:

**Step 1:** Check the contents of the student's directory: `ls -l`.

**Step 2:** Observe that the `welcome` binary has the setuid bit set (or on), which means it runs with root privileges. Check the file type: `file welcome`.

**Step 3:** Investigate the binary using the `strings` command: `strings welcome`.

**Step 4:** Observe the greetings strings in the output of the `strings` command. It's possible that the `welcome` binary is calling the `greetings` binary. Delete the `greetings` binary and copy `/bin/bash` to its location, renaming it as `greetings`.

**Step 5:** Run the `welcome` binary again. The student user will escalate to the root user, allowing you to retrieve the flag located in the `/root` directory.

Flag: `b92bcdc876d52108778e2d81f3b01494`

These steps outline how to exploit a setuid binary (`welcome`) to gain root privileges by replacing another binary (`greetings`) that is executed by the `welcome` program.