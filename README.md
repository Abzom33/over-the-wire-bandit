# OverTheWire — Bandit Writeups

A collection of solutions and explanations for the [OverTheWire Bandit](https://overthewire.org/wargames/bandit/) wargame challenges.

---

## Table of Contents

- [Level 0 → 1](#level-0--1)
- [Level 1 → 2](#level-1--2)
- [Level 2 → 3](#level-2--3)
- [Level 3 → 4](#level-3--4)
- [Level 4 → 5](#level-4--5)
- [Level 5 → 6](#level-5--6)
- [Level 6 → 7](#level-6--7)
- [Level 7 → 8](#level-7--8)
- [Level 8 → 9](#level-8--9)
- [Level 9 → 10](#level-9--10)
- [Level 10 → 11](#level-10--11)
- [Level 11 → 12](#level-11--12)
- [Level 12 → 13](#level-12--13)
- [Level 13 → 14](#level-13--14)
- [Level 14 → 15](#level-14--15)

---

## Level 0 → 1

**Goal:** Find the password stored in a file called `readme` in the home directory.

### Solution

<img width="696" height="506" alt="image" src="https://github.com/user-attachments/assets/24ba61a4-0127-45e9-9886-c4d092ee21b2" />

<img width="490" height="22" alt="image" src="https://github.com/user-attachments/assets/99d904ad-9c7d-42d4-90f4-7ce9755f9802" />

### Explanation

You use the `ssh` command which stands for (Secure Shell) to connect to `bandit.labs.overthewire.org` remotely over a secure network. The `cat` command is used to display the contents inside a file.

**Password:** `6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR`

---

## Level 1 → 2

**Goal:** Open a file called `-` in the home directory to get the password for the next level.

### Solution

<img width="288" height="24" alt="image" src="https://github.com/user-attachments/assets/1e05fa01-94a1-479b-b9a2-35dd5a4a83f5" />

### Explanation

The `-` symbol is used by the `cat` command for stdin (Standard Input), therefore it's treated as an option. To avoid this, write out the full file path using `./[file name]`.

**Password:** `PK8fYLZg2hnHSz83plBL1iEPKdD3QToB`

---

## Level 2 → 3

**Goal:** Open a file called `--spaces in this filename--` in the home directory to get the password for the next level.

### Solution

<img width="576" height="23" alt="image" src="https://github.com/user-attachments/assets/bd4501b2-f853-4769-8028-9f28e8efb651" />

### Explanation

The `-` symbol is used by the `cat` command for stdin (Standard Input), therefore it's treated as an option. To avoid this, write out the full file path using `./[file name]`.

**Password:** `7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME`

---

## Level 3 → 4

**Goal:** Find the password in a hidden file in the `inhere` directory.

### Solution

<img width="451" height="115" alt="image" src="https://github.com/user-attachments/assets/600fe182-954a-4dbd-94a2-fd32776d9558" />

<img width="558" height="181" alt="image" src="https://github.com/user-attachments/assets/67b1527b-749b-430a-b4e2-a8094e7f62d5" />

### Explanation

Use `cd` to navigate into the `inhere` directory, then use `cat` along with `./` to get the full file path rather than triggering the `-` option.

**Password:** `xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq`

---

## Level 4 → 5

**Goal:** Find the password stored in the only human-readable file in the `inhere` directory.

### Solution

<img width="556" height="24" alt="image" src="https://github.com/user-attachments/assets/09bbc352-9cc1-4d06-a2e9-d895b14d0750" />

### Explanation

The `find` command is used to filter out files using the `-type f` option, then we use the piping symbol `|` to redirect its output to `xargs`, which converts stdin into an argument applied to the next command. The `file` command identifies the file type — we are looking for a human-readable file, which is **ASCII text**. Once found, use `cat` with `./` to get the full file path since the filename contains `-`.

**Password:** `6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG`

---

## Level 5 → 6

**Goal:** Find the password inside `inhere` in a file with these properties:

- Human-readable
- 1033 bytes in size
- Not executable

### Solution

<img width="651" height="26" alt="image" src="https://github.com/user-attachments/assets/dd213b87-0d39-44ae-814a-4b4862d65229" />

### Explanation

We use the `find` command to search for a file matching all three properties, using these options:

- `.` — search in the current directory
- `-type f` — filter for files only
- `-size 1033c` — match files of exactly 1033 bytes (`c` = bytes, `k` = kilobytes, `M` = megabytes, `G` = gigabytes)
- `! -executable` — exclude executable files

**Password:** `pXa26xhMWaC2SvDotA4r9EgZkulOeSBW`

---

## Level 6 → 7

**Goal:** Find the password stored somewhere on the server with these properties:

- Owned by user `bandit7`
- Owned by group `bandit6`
- 33 bytes in size

### Solution

<img width="827" height="22" alt="image" src="https://github.com/user-attachments/assets/5385de5e-2578-4710-95fd-ff4996b412a8" />

### Explanation

The password is stored **somewhere on the server**, meaning it could be anywhere on the filesystem. We use the `find` command with these options:

- `/` — search from root, representing the whole Linux file system
- `-user bandit7` — find files belonging to user `bandit7`
- `-group bandit6` — find files belonging to group `bandit6`
- `-size 33c` — match files of 33 bytes
- `grep` — used to filter results
- `|` — redirects the output of the first command into the second

**Password:** `Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3`

---

## Level 7 → 8

**Goal:** The password is stored in `data.txt` next to the word `millionth`.

### Solution

<img width="510" height="26" alt="image" src="https://github.com/user-attachments/assets/157aac11-4a64-47d3-8c0a-00238cf727c0" />

### Explanation

We use two commands: `cat` and `grep`.

- `cat` — displays the contents of `data.txt`
- `grep` — searches for the matching pattern `millionth`
- `|` — redirects the output of `cat` into `grep`

**Password:** `VR1ljMayciFxbnUokuQmJFw6QC9VKtub`

---

## Level 8 → 9

**Goal:** The password is stored in `data.txt` and is the only line of text that occurs exactly once.

### Solution

<img width="456" height="19" alt="image" src="https://github.com/user-attachments/assets/402ea4fa-8f39-42bc-80c5-ff48f5554d33" />

### Explanation

We use two commands: `sort` and `uniq`.

- `sort` — sorts the file, arranging its contents in order
- `uniq` — filters out repeated lines
- `-u` — returns only lines that are unique (appeared exactly once)

> `uniq` can only detect duplicates that are **adjacent** to each other, so `sort` must be run first to group identical lines together. Then `uniq -u` removes duplicates and returns each unique line once.

**Password:** `EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl`

---

## Level 9 → 10

**Goal:** The password is stored in `data.txt` in one of the few human-readable strings, preceded by several `=` characters.

### Solution

<img width="462" height="22" alt="image" src="https://github.com/user-attachments/assets/f7e9532c-f14a-4848-bebb-9fae95505b8b" />

### Explanation

We use two commands: `strings` and `grep`.

- `strings` — extracts human-readable strings from files, including binary files
- `grep` — searches for matching patterns; here we search for `=`
- `|` — redirects the output of `strings` into `grep`

**Password:** `B0s2khmbT9u0geKuOoVGW3JZKhndE3BG`

---

## Level 10 → 11

**Goal:** The password is stored in `data.txt`, which contains base64 encoded data.

### Solution

<img width="460" height="23" alt="image" src="https://github.com/user-attachments/assets/36e8347c-aa37-4356-936d-ff8ce7f7979e" />

### Explanation

The file `data.txt` contains base64 encoded data. To retrieve the password, decode it using:

- `base64 -d` — decodes base64 encoded data

**Password:** `pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro`

---

## Level 11 → 12

**Goal:** The password is stored in `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

### Solution

<img width="674" height="41" alt="image" src="https://github.com/user-attachments/assets/a7b2ef7d-dc37-443c-982d-0df1ddcb94c6" />

### Explanation

All letters have been shifted by 13 positions (ROT13), so `A` → `N`, `Z` → `M`, etc. We use the `tr` command to translate characters back.

- First set: all letters `A-Z` and `a-z`
- Second set: the letters rotated 13 positions — `N-ZA-M` and `n-za-m` — mapped back to the first set

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

**Password:** `GROozWPO8QyN0mGrjUkID0WCYkZiQxrN`

---

## Level 12 → 13

**Goal:** The password is stored in `data.txt`, which is a hexdump of a file that has been repeatedly compressed.

### Solution

<img width="700" height="659" alt="image" src="https://github.com/user-attachments/assets/de500a98-f2b7-4f7d-8494-0d14d0aeb3d6" />

### Explanation

Since `data.txt` is a hexdump, you first need to reverse it using `xxd -r`, then redirect the output into a new file using `>`.

Steps to follow:

1. Use `xxd -r` to reverse the hexdump into a binary file
2. Use the `file` command to identify the file type
3. Use `mv` to rename the file with the correct suffix so the decompression tool recognises it (e.g. rename to `.gz` for gzip)
4. Use the correct tool to decompress — `gzip`, `bzip2`, `tar`, etc.
5. Repeat steps 2–4 until `file` reports **ASCII text**
6. Use `cat` to read the password

**Password:** `qQYQiHOBPR8zR61qxYqX45quvihF2uzk`

---

## Level 13 → 14

**Goal:** The password is stored in `/etc/bandit_pass/bandit14` and can only be read by user `bandit14`. Instead of a password, you are given a private SSH key to log into the next level.

### Solution

<img width="789" height="42" alt="image" src="https://github.com/user-attachments/assets/09dc0877-c57e-4f0b-b8e2-0b6b91e59bb1" />

<img width="796" height="218" alt="image" src="https://github.com/user-attachments/assets/f8cb93a0-77e0-4e72-abc5-3b7d7467210f" />

<img width="559" height="29" alt="image" src="https://github.com/user-attachments/assets/05edd3c2-a73d-47a1-823a-e9210ffc1f4c" />

### Explanation

- Use `scp` to copy the SSH private key from the bandit remote server to your local machine
- Once the key is local, use `ssh` with the `-i` option to specify the private key file
- Once logged in as `bandit14`, use `cat` to read `/etc/bandit_pass/bandit14`

**Password:** `aaWecNkG4FhxJQxz07uiwzVP6bJiYS65`

---

## Level 14 → 15

**Goal:** The password for the next level can be retrieved by submitting the current level's password to `port 30000` on `localhost`.

### Solution

<img width="694" height="48" alt="image" src="https://github.com/user-attachments/assets/45363e85-5640-4165-8282-c2725a374a0c" />

### Explanation

- Use the `nc` command to connect to `port 30000` on `localhost`
- Use the piping symbol `|` to redirect the password as input to the `nc` command

**Password:** `pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7`

---
