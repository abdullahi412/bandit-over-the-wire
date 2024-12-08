# Bandit OverTheWire Game: Levels 0-8

This README documents my journey through the Bandit game levels 0 to 8 on OverTheWire. It includes the steps and commands I used to solve each level, providing a clear guide for anyone following along.

---

## Level 0
- **Objective:** Find the password for the next level in a file named `readme`.
- **Steps:**
  1. Used `ls` to list the files, which showed `readme`.
  2. Used `cat readme` to display the contents of the file.
- **Answer:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

---

## Level 1
- **Objective:** Access a file named `-` to find the password.
- **Steps:**
  1. Used `ls`, which displayed a file named `-`.
  2. Learned that `cat -` doesn’t work because `-` is interpreted as an option.
  3. Used `cat ./-` to explicitly reference the file.
- **Answer:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

---

## Level 2
- **Objective:** Access a file with spaces in its name.
- **Steps:**
  1. Used `ls`, which displayed a file named `spaces in this filename`.
  2. Realized that spaces in filenames require quoting or escaping.
  3. Used `cat "spaces in this filename"` to view the file contents.
- **Answer:** `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

---

## Level 3
- **Objective:** Find a hidden file inside a directory.
- **Steps:**
  1. Used `ls`, which showed a directory named `inhere`.
  2. Navigated into the directory using `cd inhere/`.
  3. Used `ls -a` to reveal hidden files, finding `...Hiding-From-You`.
  4. Used `cat ...Hiding-From-You` to display the contents.
- **Answer:** `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`

---

## Level 4
- **Objective:** Find the file containing ASCII text among several numbered files.
- **Steps:**
  1. Used `ls -al` to list all files, including hidden ones, in long format.
  2. Used `file ,/-fileXX` on each file to determine its type.
  3. Found `,/-file07` contained ASCII text.
  4. Used `cat ,/-file07` to view the file.
- **Answer:** `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

---

## Level 5
- **Objective:** Locate a non-executable file that is exactly 1033 bytes in size.
- **Steps:**
  1. Used `find` with the following criteria:
     - `-type f`: Look for regular files.
     - `-size 1033c`: Files that are exactly 1033 bytes.
     - `! -executable`: Files that are not executable.
  2. Command: `find . -type f -size 1033c ! -executable`
  3. Found the file and used `cat maybehere07/.file2` to retrieve the password.
- **Answer:** `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

---

## Level 6
- **Objective:** Locate a file with specific ownership and size properties.
- **Steps:**
  1. Used `find` with the following criteria:
     - `/`: Search from the root directory.
     - `-size 33c`: File size is 33 bytes.
     - `-user bandit7`: Owned by user `bandit7`.
     - `-group bandit6`: Owned by group `bandit6`.
     - `2>/dev/null`: Suppress permission errors.
  2. Command: `find / -size 33c -user bandit7 -group bandit6 2>/dev/null`
  3. Located the file and used `cat` to retrieve the password.
- **Answer:** `morbNTDkSW6jI1Uc0ym0dMaLnO1FVAaj`

---

## Level 7
- **Objective:** Find the line of text that occurs only once in the file `data.txt`.
- **Steps:**
  1. Used `ls`, which displayed the `data.txt` file.
  2. The hint specified that the password is the **only unique line** in the file.
  3. Used the command: `cat data.txt | grep "millionth"`
- **Answer:** `dfwvzFQi4mU0wfNbOe9RoWskMLg7eEc`

---

## Level 8
- **Objective:** Find the unique line of text in `data.txt`.
- **Steps:**
  1. Used `ls`, which displayed the `data.txt` file.
  2. Since the file contained random lines, used `sort` and `uniq` to filter the unique line.
  3. Command: `sort data.txt | uniq -u`
- **Answer:** `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

