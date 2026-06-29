<img width="827" height="22" alt="image" src="https://github.com/user-attachments/assets/83033951-7b57-4100-9aa4-ada214927d32" /># over-the-wire-bandit
In this section , I will be covering OTW bandit game levels 1 -20. I will document my journey including what have I learnt , challenges I have expeirnced .

# Level 0 - 1

Goal : To find the password for the next level which is stored in a file called readme located in the home directory. 

## Solution :

<img width="696" height="506" alt="image" src="https://github.com/user-attachments/assets/24ba61a4-0127-45e9-9886-c4d092ee21b2" />

## To find the password : 

<img width="490" height="22" alt="image" src="https://github.com/user-attachments/assets/99d904ad-9c7d-42d4-90f4-7ce9755f9802" />




 ## Explanation 
 You use the ssh command which stands for (Secure Shell) to connect to  bandit.labs.overthewire.org remotely over a secure network.  The cat command is used to display the contents inside a file

## password is :  `6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR`




 # Level 1 -2 

## Goal :  To open a file called - in the home directory to get the level for the next level


## Solution : 

<img width="288" height="24" alt="image" src="https://github.com/user-attachments/assets/1e05fa01-94a1-479b-b9a2-35dd5a4a83f5" />



## Explanation : 

the "-" symbol is used by the cat command for stdin (Standard Input) therefore its an option. To avoid you need to write out the full file path by ./[file name]

Password : `PK8fYLZg2hnHSz83plBL1iEPKdD3QToB`





 # Level 2 - 3

## Goal :  To open a file called --spaces in this filename-- in the home directory to get the level for the next level


## Solution 

<img width="576" height="23" alt="image" src="https://github.com/user-attachments/assets/bd4501b2-f853-4769-8028-9f28e8efb651" />




## Explanation

the "-" symbol is used by the cat command for stdin (Standard Input) therefore its an option. To avoid you need to write out the full file path by ./[file name] 

Password : 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME


# Level 3 -4

## Goal : To find the password in n a hidden file in the inhere directory.

### Solution:


<img width="451" height="115" alt="image" src="https://github.com/user-attachments/assets/600fe182-954a-4dbd-94a2-fd32776d9558" />#



<img width="558" height="181" alt="image" src="https://github.com/user-attachments/assets/67b1527b-749b-430a-b4e2-a8094e7f62d5" />


Explanation : use the 'cd' to get the inhere directory then use cat along with ./ to get the file path rather . option

Password : xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq


# Level 4 - 5

Goal : To find The password for the next level is stored in the only human-readable file in the inhere directory.

## Solution :

<img width="556" height="24" alt="image" src="https://github.com/user-attachments/assets/09bbc352-9cc1-4d06-a2e9-d895b14d0750" />


## Explanation : 
The <code><b>find</b></code> command is used to filter out any files by using the option <code><b>type -f</b></code>, then we use the piping symbol <code><b>|</b></code> to redirect its output to the <code><b>xargs</b></code> command which is used to convert stdin (standard input) into an argument which is applied to the second command . The file command , this used to find the file type, in this case we are looking for a human readable file , which is ASCII text. Once we do , use the cat command and <code><b>./</b></code> to get the full file path as it contains <code><b>-</b></code>

## Password : `6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG`


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


## Password : `pXa26xhMWaC2SvDotA4r9EgZkulOeSBW`






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


  ## Password : `Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3`




 # Level 7 - 8

  ## Goal : The password for the next level is stored in the file data.txt next to the word <code<b>millionth</b></code


  ## Solution :

  <img width="510" height="26" alt="image" src="https://github.com/user-attachments/assets/157aac11-4a64-47d3-8c0a-00238cf727c0" />



  ## Explanation :  To find the password we use 2 commands , <code><b>grep</b></code> and <code><b>cat</b></code> . 


  -  <code><b>grep</b></code> = This command is used to search for matching patterns in a file . We use to find the pattern <code><b>millionth</b></code>
  -  <code><b>cat</b></code> = This command is used to display contents of a file or it can be used
    to concatenate files together. For this context , we are using to display contents the file  <code><b>data.txt</b></code>
  -  <code><b> | </b></code> to redirect the output of the first command into the second command.
 


 ## Password : `VR1ljMayciFxbnUokuQmJFw6QC9VKtub`


 # Level 8 - 9

 ## Goal : The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
  

 ## Solution : 
 
 <img width="456" height="19" alt="image" src="https://github.com/user-attachments/assets/402ea4fa-8f39-42bc-80c5-ff48f5554d33" />


## Explanation

In this level, we use the commands `sort` and `uniq`.

- `sort` — sorts a file, arranging its contents in a particular order.
- `uniq` — filters out repeated lines in a file.

We use the following option for the `uniq` command:

- `-u` — returns only the lines that are unique (appeared exactly once).

- For `uniq` to work correctly, you must run `sort` first.  
- `uniq` can only detect duplicates that are **adjacent** to each other.  
-  So `sort` arranges the lines alphabetically, then `uniq -u` removes duplicates and returns each unique line once.



## Password : `EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl`




# Level 9 - 10 : The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.


## Solution : 

<img width="462" height="22" alt="image" src="https://github.com/user-attachments/assets/f7e9532c-f14a-4848-bebb-9fae95505b8b" />



## Explanation :  
In this level, we use the commands `strings` and `grep`.

- `strings` —  It extracts human-readable strings from files such as binary files.
- `grep` — Seaches for matching patterns in a file.

 - We use the `|` piping symbol to redirect the output of the command `strings` into the `grep`
  command.


## Password :  B0s2khmbT9u0geKuOoVGW3JZKhndE3BG


# Level 10 -11

## Goal : The password for the next level is stored in the file data.txt, which contains base64 encoded data


## Solution : 

 <img width="460" height="23" alt="image" src="https://github.com/user-attachments/assets/36e8347c-aa37-4356-936d-ff8ce7f7979e" />


 ## Explanation : 
 
 For this level , the textfile <code><b>data.txt</b></code> contains base64 encoded data. To get    the password for this level you need it to decode it by using this option:

 - <code><b>base64 -d</b></code> = this is used to decode the base64 encoded data.


## Password : ` pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro`


# Level 11 - 12

## Goal : The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions


## Solution : 

<img width="674" height="41" alt="image" src="https://github.com/user-attachments/assets/a7b2ef7d-dc37-443c-982d-0df1ddcb94c6" />


## Explanation :

For this level , all the letters have shifted by 13 positions. So the letter `A` --> `N`, 
`Z` --> `M` . Therfore we need shift each letter by 13 positions to get the password.  We can use `tr` command , which is used for translating characters.

- First for we need get all letters A-Z upper and lowercase
-  For the second set , we use all the letters that have been rotated 13 positions , so it can be mapped to the first set , which includes A-Z .  `N-Z` `A-M`

- Result :  <code><b> cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m</b></code>


## Password :

- The password is  `GROozWPO8QyN0mGrjUkID0WCYkZiQxrN`



# Level 12 - 13

## Goal : The password for the next level is stored in the file `data.txt`, which is a `hexdump` of a file that has been repeatedly compressed.

## Solution :

<img width="700" height="659" alt="image" src="https://github.com/user-attachments/assets/de500a98-f2b7-4f7d-8494-0d14d0aeb3d6" />



Explanation :
Since `data.txt` is a hexdump , you have to reverse by using the command `xxd -r `to reverse the hexdump , since it is not pernament you have to redirect by using the `>` symbol to redirect into a new file called hexdump.

- First we need to identify what type of file we are dealing with, we can use the `file` command to check the file type
- Use `mv` to rename the file with the correct suffix so the decompression tool recognises it. For example if file tells you it's a `gzip` compressed file, rename it to `.gz`
- Then use the correct tool to decompress it. `gzip`, `bzip2`, `tar` etc. each handle different formats
- Keep repeating this check with file, rename with mv, decompress , until file tells you it's `ASCII` text
- Once it's `ASCII` text, use `cat` to read the password


  ## Password :

`qQYQiHOBPR8zR61qxYqX45quvihF2uzk`



# Level 13 - 14

## Goal : The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by user `bandit14.` For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. 


## Solution :


   <img width="789" height="42" alt="image" src="https://github.com/user-attachments/assets/09dc0877-c57e-4f0b-b8e2-0b6b91e59bb1" />
   
   

<img width="796" height="218" alt="image" src="https://github.com/user-attachments/assets/f8cb93a0-77e0-4e72-abc5-3b7d7467210f" />



<img width="559" height="29" alt="image" src="https://github.com/user-attachments/assets/05edd3c2-a73d-47a1-823a-e9210ffc1f4c" />



## Explanation : 

- First we use the `scp` command to copy the `ssh private key` from bandit remote server to my local machine.
- Once the the `ssh private key` is in  our local machine , we `ssh` and use the `-i` option to specify the private key which we copied using the `scp` command .
- Once logged in to `bandit14` , use the `cat` command to open the file  /etc/bandit_pass/bandit14 .



  ## Password :

  - `aaWecNkG4FhxJQxz07uiwzVP6bJiYS65`


   


   




  
 

 


  




