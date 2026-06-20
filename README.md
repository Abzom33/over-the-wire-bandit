<img width="827" height="22" alt="image" src="https://github.com/user-attachments/assets/83033951-7b57-4100-9aa4-ada214927d32" /># over-the-wire-bandit
In this section , I will be covering OTW bandit game levels 1 -20. I will document my journeyincluding what have I learnt , challenges I have expeirnced .

# Level 0 - 1

Goal : To find the password for the next level which is stored in a file called readme located in the home directory. 

## Solution :
<img width="696" height="506" alt="image" src="https://github.com/user-attachments/assets/24ba61a4-0127-45e9-9886-c4d092ee21b2" />

## To find the password

<img width="490" height="22" alt="image" src="https://github.com/user-attachments/assets/99d904ad-9c7d-42d4-90f4-7ce9755f9802" />




 ## Explanation 
 You use the ssh command which stands for (Secure Shell) to connect to  bandit.labs.overthewire.org remotely over a secure network.  The cat command is used to display the contents inside a file

 The password is :  ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If4




 # Level 1 -2 

## Goal :  To open a file called - in the home directory to get the level for the next level


## Solution 

<img width="288" height="24" alt="image" src="https://github.com/user-attachments/assets/1e05fa01-94a1-479b-b9a2-35dd5a4a83f5" />



## Explanation

the "-" symbol is used by the cat command for stdin (Standard Input) therefore its an option. To avoid you need to write out the full file path by ./[file name]

Password : 263JGJPfgU6LtdEvgfWU1XP5yac29mFx





 # Level 2 - 3

## Goal :  To open a file called --spaces in this filename-- in the home directory to get the level for the next level


## Solution 

<img width="576" height="23" alt="image" src="https://github.com/user-attachments/assets/bd4501b2-f853-4769-8028-9f28e8efb651" />




## Explanation

the "-" symbol is used by the cat command for stdin (Standard Input) therefore its an option. To avoid you need to write out the full file path by ./[file name] 

Password : MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx


# Level 3 -4

## Goal : To find the password in n a hidden file in the inhere directory.

Solution:
<img width="451" height="115" alt="image" src="https://github.com/user-attachments/assets/600fe182-954a-4dbd-94a2-fd32776d9558" />#



<img width="558" height="181" alt="image" src="https://github.com/user-attachments/assets/67b1527b-749b-430a-b4e2-a8094e7f62d5" />


Explanation : use the 'cd' to get the inhere directory then use cat along with ./ to get the file path rather . option

Password : 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ


# Level 4 - 5

Goal : To find The password for the next level is stored in the only human-readable file in the inhere directory.

Solution :

<img width="750" height="238" alt="image" src="https://github.com/user-attachments/assets/89de3178-3b3e-4bbd-ae93-d1a8a41c9f88" />


## Explanation : 
The <code><b>find</b></code> command is used to filter out any files by using the option <code><b>type -f</b></code>, then we use the piping symbol <code><b>|</b></code> to redirect its output to the <code><b>xargs</b></code> command which is used to convert stdin (standard input) into an argument which is applied to the second command . The file command , this used to find the file type, in this case we are looking for a human readable file , which is ASCII text. Once we do , use the cat command and <code><b>./</b></code> to get the full file path as it contains <code><b>-</b></code>

## Password : 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw


# Level 5 - 6

## Goal : Find the password for the next level in a file inside <code><b>inhere</b></code> which has the following properties :

- human-readable
- 1033 bytes in size
- not executable


## Solution :

<img width="651" height="26" alt="image" src="https://github.com/user-attachments/assets/dd213b87-0d39-44ae-814a-4b4862d65229" />


## Explanation :

In this level , we are looking for a file with the follwing properties , human-readable , 1033 bytes in size , not executable . We can use the <code><b>find</b></code> command to search for files in a directory. We can use the options :

- <code><b>.</b></code> =  to look in this current directory
- <code><b>- type f</b></code>  filter out files
-  <code><b>- size </b></code>  ( c = Bytes , k = kilobytes , M = Megabits , G = Gigabytes ) - 1033c is 1033 bytes
-  <code><b>- ! executable </b></code>  = not executable


## Password : HWasnPhtq9AVKe0dmk45nxy20cvUa6EG






# Level 6 - 7

## Goal : We are looking for a password for the next level which is stored somewhere on the server which has the following properties :

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size


## Solution :

<img width="827" height="22" alt="image" src="https://github.com/user-attachments/assets/5385de5e-2578-4710-95fd-ff4996b412a8" />


## Explanation : In this level the password is stored <code><b>somewhere on the server</b></code> , which means that it could be anywhere.

- Therfore , we need to search the whole file system . We use the <code><b>find</b></code> command and use these options  :
  - <code><b>/</b></code>  = This stands for root , which represents the whole Linux File System.
  - <code><b>user</b></code> = This finds files that belong to the user.
  - <code><b>group</b></code> = This finds files that belong to the group.
  -  We use <code><b>user</b></code> to find files belong to user bandit7
  -  <code><b>group</b></code> to find files belong to the group bandit6
  -  <code><b>grep</b></code> = used to find the word password in the Linux File Sytem
  -  <code><b> | </b></code> to redirect the output of the first command into the second command.


  ## Password : morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj




 # Level 7 - 8

  ## Goal : The password for the next level is stored in the file data.txt next to the word <code<b>millionth</b></code


  ## Solution :

  <img width="510" height="26" alt="image" src="https://github.com/user-attachments/assets/157aac11-4a64-47d3-8c0a-00238cf727c0" />



  ## Explanation :  To find the password we use 2 commands , <code><b>grep</b></code> and <code><b>cat</b></code> . 


  -  <code><b>grep</b></code> = This command is used to search for matching patterns in a file . We use to find the pattern <code><b>millionth</b></code>
  -  <code><b>cat</b></code> = This command is used to display contents of a file or it can be used
    to concatenate files together. For this context , we are using to display contents the file  <code><b>data.txt</b></code>
  -  <code><b> | </b></code> to redirect the output of the first command into the second command.
 


 ## Password : dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

  




