# :smiley: OverTheWire-Bandit-Writeup
Write-up for OverTheWire: Bandit CTF challenges.

## :open_book: Introduction

OverTheWire is a community that can help you to learn and practice security concepts in the form of fun-filled games. They offer lots of wargames to practice your skills.This writeup is userfull beginner friendly.
Here is the [link](https://overthewire.org/wargames/bandit/) . 

![image](https://user-images.githubusercontent.com/79222856/162040555-e16fb865-83b0-4f96-8e89-ca0431497191.png)

The first set of challenges is named "Bandit," and it's more of a tutorial to the Linux CLI, with each level's goal being to discover the password to move to the next.

![image](https://user-images.githubusercontent.com/79222856/162041580-9b993e51-06dd-4c42-bfe6-2adbf7ea0f45.png)

You will encounter many situations in which you have no idea what you are supposed to do. Don’t panic! Don’t give up! The purpose of this game is for you to learn the basics. Part of learning the basics, is reading a lot of new information.Before looking at the answers, I recommend doing it yourself because you won't learn anything unless you try. My primary idea is to demonstrate you how I handled it and to compare your solutions to mine.

## :clipboard: Table of Contents

- [:triangular_flag_on_post: Bandit Level 00](#triangular_flag_on_post-bandit-level-0)
- [:triangular_flag_on_post: Bandit Level 00 - 01](#triangular_flag_on_post-bandit-level-00---01)
- [:triangular_flag_on_post: Bandit Level 01 - 02](#triangular_flag_on_post-bandit-level-01---02)
- [:triangular_flag_on_post: Bandit Level 02 - 03](#triangular_flag_on_post-bandit-level-02---03)
- [:triangular_flag_on_post: Bandit Level 03 - 04](#triangular_flag_on_post-bandit-level-03---04)
- [:triangular_flag_on_post: Bandit Level 04 - 05](#triangular_flag_on_post-bandit-level-04---05)
- [:triangular_flag_on_post: Bandit Level 05 - 06](#triangular_flag_on_post-bandit-level-05---06)
- [:triangular_flag_on_post: Bandit Level 06 - 07](#triangular_flag_on_post-bandit-level-06---07)
- [:triangular_flag_on_post: Bandit Level 07 - 08](#triangular_flag_on_post-bandit-level-07---08)
- [:triangular_flag_on_post: Bandit Level 08 - 09](#triangular_flag_on_post-bandit-level-08---09)
- [:triangular_flag_on_post: Bandit Level 09 - 10](#triangular_flag_on_post-bandit-level-09---10)
- [:triangular_flag_on_post: Bandit Level 10 - 11](#triangular_flag_on_post-bandit-level-10---11)
- [:triangular_flag_on_post: Bandit Level 11 - 12](#triangular_flag_on_post-bandit-level-11---12)
- [:triangular_flag_on_post: Bandit Level 12 - 13](#triangular_flag_on_post-bandit-level-12---13)
- [:triangular_flag_on_post: Bandit Level 13 - 14](#triangular_flag_on_post-bandit-level-13---14)
- [:triangular_flag_on_post: Bandit Level 14 - 15](#triangular_flag_on_post-bandit-level-14---15)
- [:triangular_flag_on_post: Bandit Level 15 - 16](#triangular_flag_on_post-bandit-level-15---16)
- [:triangular_flag_on_post: Bandit Level 16 - 17](#triangular_flag_on_post-bandit-level-16---17)
- [:triangular_flag_on_post: Bandit Level 17 - 18](#triangular_flag_on_post-bandit-level-17---18)
- [:triangular_flag_on_post: Bandit Level 18 - 19](#triangular_flag_on_post-bandit-level-18---19)
- [:triangular_flag_on_post: Bandit Level 19 - 20](#triangular_flag_on_post-bandit-level-19---20)
- [:triangular_flag_on_post: Bandit Level 20 - 21](#triangular_flag_on_post-bandit-level-20---21)
- [:triangular_flag_on_post: Bandit Level 21 - 22](#triangular_flag_on_post-bandit-level-21---22)
- [:triangular_flag_on_post: Bandit Level 22 - 23](#triangular_flag_on_post-bandit-level-22---23)
- [:triangular_flag_on_post: Bandit Level 23 - 24](#triangular_flag_on_post-bandit-level-23---24)
- [:triangular_flag_on_post: Bandit Level 24 - 25](#triangular_flag_on_post-bandit-level-24---25)
- [:triangular_flag_on_post: Bandit Level 25 - 26](#triangular_flag_on_post-bandit-level-25---26)
- [:triangular_flag_on_post: Bandit Level 26 - 27](#triangular_flag_on_post-bandit-level-26---27)
- [:triangular_flag_on_post: Bandit Level 27 - 28](#triangular_flag_on_post-bandit-level-27---28)
- [:triangular_flag_on_post: Bandit Level 28 - 29](#triangular_flag_on_post-bandit-level-28---29)
- [:triangular_flag_on_post: Bandit Level 29 - 30](#triangular_flag_on_post-bandit-level-29---30)
- [:triangular_flag_on_post: Bandit Level 30 - 31](#triangular_flag_on_post-bandit-level-30---31)
- [:triangular_flag_on_post: Bandit Level 31 - 32](#triangular_flag_on_post-bandit-level-31---32)
- [:triangular_flag_on_post: Bandit Level 32 - 33](#triangular_flag_on_post-bandit-level-32---33)
- [:triangular_flag_on_post: Bandit Level 33 - 34](#triangular_flag_on_post-bandit-level-33---34)
- [:bulb: Acknowledgement](#bulb-acknowledgement)



## :triangular_flag_on_post: Bandit Level 00

### Problem Description:
let's go :grinning: !!! Logging into the game using SSH.
![image](https://user-images.githubusercontent.com/79222856/162045944-4e5b543f-06e3-41c0-916b-5c6a17ac04ee.png)

### Solution & Explanation:
To begin, you must understand how to use the secure shell (SSH) protocol to connect to the bandit.labs.overthewire.org server. If you're using Linux, you may access the server by running the following command:


```
0xRh1d0Y@kali:~$ ssh bandit.labs.overthewire.org -l bandit0 -p 2220
```
If you're using Windows, though, you won't find an SSH client by default. While there are several great SSH clients available for use in Windows environments like PuTTY !  But , here i am using Termius it is straightforward and easy.

![image](https://user-images.githubusercontent.com/79222856/162047741-296f239a-c90a-4b5f-b65e-22f273fb629e.png)

When you're finished entering the address ,port number,username and password then hit "hosts," and you'll be able to access the bandit0 shell.

![image](https://user-images.githubusercontent.com/79222856/162048999-5f862d21-ee3f-439f-a0ff-48a18b1a3f27.png)

## :triangular_flag_on_post: Bandit Level 00 - 01

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162050490-5988f2c8-6934-4754-890c-883a8d5418bb.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162051066-f74ff496-7092-43b8-919b-5cfc19c7dbcb.png)


### Explanation:

This level is also a straightforward giveaway. As suggested by the level's hint, run **ls** to examine the current directory, then **cat** the **readme** file to view its information. 

If you don't understand the meaning behind any of these commands. Well, try to read the manual pages! **man** is the name of the command that pulls up manpages. So you use **man** by doing this:

```
$ man [name of program you are interested in]
```
Here is the manpages of **ls** and **cat**:
![image](https://user-images.githubusercontent.com/79222856/162051742-303b54d2-76ee-4372-b03d-d58f94008993.png)

![image](https://user-images.githubusercontent.com/79222856/162051913-24f49238-670e-4eb6-88c8-5eb82c0bc0c7.png)

### Summary:
```
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme 
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
 ```
The password to the level 01's box is **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**


## :triangular_flag_on_post: Bandit Level 01 - 02

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162151146-748f84ef-9b59-407c-8267-85eb1ace4d77.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162151326-8b3a6462-658a-474f-a0c0-ff0b8a67ad72.png)

### Explanation:
To acquire the password for stage 2, we have to print the content of the file called **–** (the dash symbol), as recommended by the hint.

If you just use the **cat** command to read and print the contents of the file called **–**, unfortunately, your terminal will become stuck. 
![image](https://user-images.githubusercontent.com/79222856/162151886-49824c11-8c76-43d3-ae28-19f195543935.png)

As we can see, `cat` command doesn't work with a dashed filename
Instead, so as to hide the special character from `cat`, we direct the `cat` command to the file location.You must supply the full path of the file.

### Summary:
```
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
The password to gain access to the level 02's box is **CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9**



## :triangular_flag_on_post: Bandit Level 02 - 03

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162153896-a5e80005-0ad9-4736-a5b8-5faea4d23fbf.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162154105-cf0f07e2-d675-4ec4-b556-53332d406708.png)

### Explanation:
Accessing a file with spaces in its name:
To read a file name with spaces, use quotes (' ')
Either use a backslash before each space or write the full file name as a string. As an example: 
1. Adding backslash before each space:    
```
bandit2@bandit:~$ cat spaces\ in\ this\ filename
```
2. Adding double quote:
```
bandit2@bandit:~$ cat "spaces in this filename"
```
Another command that is really useful for this round is **tab completion**, which is triggered by pressing **tab**. This would make the program automatically fills in partially typed commands. 

### Summary:
```
bandit2@bandit:~$ ls 
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
The password to gain access to the level 03's box is **UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK**

## :triangular_flag_on_post: Bandit Level 03 - 04

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162156316-bf878fdb-7ac1-48cb-9a63-a77de687fe91.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162156510-606eb55b-cffa-49e3-b75f-c1ceca768028.png)

### Explanation:
Here ls  shows no output Because, the file is hidden, just use **ls -a** to find it. To learn about how flags such as **-a** or **-l** work, you can use **man ls**.

![image](https://user-images.githubusercontent.com/79222856/162157817-b56b91ca-881b-4462-899a-5f6d831919a1.png)

### Summary:
```
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls 
bandit3@bandit:~/inhere$ ls -al
total 12
drwxr-xr-x 2 root    root    4096 May  7  2020 .
drwxr-xr-x 3 root    root    4096 May  7  2020 ..
-rw-r----- 1 bandit4 bandit3   33 May  7  2020 .hidden
bandit3@bandit:~/inhere$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
The password to gain access to the box in level 04 is **pIwrPrtPN36QITSp3EQaw936yaFoFgAB**

## :triangular_flag_on_post: Bandit Level 04 - 05

### Problem Description:
![image](https://user-images.githubusercontent.com/79222856/162160247-dc877a44-7ad2-46fa-9bc1-fd3cbef6adfc.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162160951-b0e911ce-977d-43cb-b9a2-72041cb36027.png)

### Explanation:
Because just one file is human-readable and contains the password for the following round, rather than accessing each file one by one and reading its content, we may print all of each text and spot the password using:

```
Checking for human readable file:
	
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
    
Checking File details:

-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09
bandit4@bandit:~/inhere$ ls -l
total 40
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file00
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file01
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file02
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file03
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file04
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file05
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file06
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file07
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file08
-rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file09
bandit4@bandit:~/inhere$ file ./*   //checking file types
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text    
./-file08: data
./-file09: data
As can be  see, `-file07` is human readable.then we're going to be able to **cat** the password directly from it.

bandit4@bandit:~/inhere$ cat ./-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```
So,the only human-readable string is **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**. 

### Summary:

![image](https://user-images.githubusercontent.com/79222856/162163359-22ff0ce9-26bd-4a38-b2c8-1ffe0c4eb7c0.png)

The password to gain access to the level 05's box is **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**

