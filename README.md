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

## :triangular_flag_on_post: Bandit Level 05 - 06
### Problem Description:
![image](https://user-images.githubusercontent.com/79222856/162202494-a66940ef-0393-460d-94d7-dbe9a00194ef.png)
### Solution:
![image](https://user-images.githubusercontent.com/79222856/162204698-e87383d5-19ac-49c8-8af2-cf89c83b89fe.png)


### Explanation:

The first thing we do when we start a new level is to run the **ls** command to see what files we have access to.There so many file !  imagine running cat on each and every one of them And wow, we're looking at 80 files in this instance.


We must use the suggestions provided to limit down the scope, for example, a file that is human-readable and 1033 bytes in size. In this case, the **find** command makes life a lot easier; read the manpage and look for an appropriate flag that will help you search for files that match your criteria. We may utilize the **type** and **size** parameters in this case .Try to read man **find** page to more understanding about find command : 
![image](https://user-images.githubusercontent.com/79222856/162207223-f076357a-388d-4e2c-9889-6e5d61a58c3c.png)
![image](https://user-images.githubusercontent.com/79222856/162207808-f94865e9-cac5-4410-83ef-2b8708815765.png)

```
Checking file details:

bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls    
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
bandit5@bandit:~/inhere$ file ./*
./maybehere00: directory
./maybehere01: directory
./maybehere02: directory
./maybehere03: directory
./maybehere04: directory
./maybehere05: directory
./maybehere06: directory
./maybehere07: directory
./maybehere08: directory
./maybehere09: directory
./maybehere10: directory
./maybehere11: directory
./maybehere12: directory
./maybehere13: directory
./maybehere14: directory
./maybehere15: directory
./maybehere16: directory
./maybehere17: directory
./maybehere18: directory
./maybehere19: directory
	
Using find command, applying required filters:

bandit5@bandit:~/inhere$ find . -type f ! -executable -size 1033c 
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7

```
### Summary:

```
bandit5@bandit:~/inhere$ find . -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
The password to gain access to the level 06's box is **DXjZPULLxYr17uwoI01bNLQbtFemEgo7**


## :triangular_flag_on_post: Bandit Level 06 - 07

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162209152-62d5805c-71dc-4b47-93c9-0d035bd8b7db.png)

### Solution:
![image](https://user-images.githubusercontent.com/79222856/162210647-89f803c8-d5aa-44e9-a320-bbc2dbe255b5.png)

### Explanation:
```
Similar to previous level, direct application of find command:

bandit6@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  .profile
bandit6@bandit:~$ find /  -user bandit7 -group bandit6 -size 33c 2>/dev/null   
	
This gives the path of the concerned file:

/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

```
The above command searches from the **root** directory (the first or top-most directory in the Linux Filesystem Hierarchy Standard), as shown by **the slash (/)** sign right after the **find** command. Other parameters include: 

1. **user**, which defines the file owner, bandit7.

![image](https://user-images.githubusercontent.com/79222856/162212769-c5acf78c-d128-4ba9-961f-7d25009d3607.png)

2. **group**, which defines the file group, bandit6 in this case.

![image](https://user-images.githubusercontent.com/79222856/162212363-7f5a5389-f176-4a2d-9da2-9cc66a7c6ab1.png)

3. **size**, which defines the size of the file. 33c means 33 bytes of characters.

![image](https://user-images.githubusercontent.com/79222856/162212611-776b5df7-5071-4742-87e6-16d555f11bc4.png)


### Summary:
```
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
The password to gain access to the level 07's box is **HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs**

## :triangular_flag_on_post: Bandit Level 07 - 08

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162259003-1fe81f28-2d52-4e2c-b12c-e7ab21f1ed24.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162259406-3a9b2230-78ba-4017-8987-c503b116f77a.png)


### Explanation:

**cat**-ing the file without doing anything else, you'll quickly regret it since the file includes an endless number of unique strings, making your terminal scroll forever.So here we can use **grep**:

```
Checking the files present:

bandit7@bandit:~$ ls
data.txt
	
Printing the lines in the file which has "millionth" in it:
	
bandit7@bandit:~$ grep -h "millionth" data.txt
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
	
OR
	
bandit7@bandit:~$ cat data.txt | grep millionth
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV

```
### Summary:

![image](https://user-images.githubusercontent.com/79222856/162261911-9872f6d0-f10c-4151-b8cd-37379e269981.png)

The password to gain access to the level 08's box is **cvX2JJa4CFALtqS87jk27qwqGhBM9plV**


## :triangular_flag_on_post: Bandit Level 08 - 09

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162264550-00c98c6b-3dd5-4a45-9c22-547c4532585b.png)

### Solution:
![image](https://user-images.githubusercontent.com/79222856/162265305-61da053b-f736-4aba-8c22-e0c1f3a95dd3.png)


### Explanation:
If you don't understand how commands like **sort** and **uniq** operate, this level may be extremely difficult.
	
Using `sort`, and `uniq` to print the uniq text in the file. `-u` flag used so as to print **only** the unique text:
Let's have a look at how the **uniq -u** command works first:


![image](https://user-images.githubusercontent.com/79222856/162267643-07ed5b25-8958-4af1-8a3a-8951fbee4f7e.png)

As you can see from the example above, the **uniq -u** command eliminates all instances of consecutively duplicated lines, leaving just the lines that have never been duplicated. What about non-consecutively repeated lines? How may they be arranged adjacent to one other? Well, **sort** will assist you in completing the task:

![image](https://user-images.githubusercontent.com/79222856/162267963-3a48abff-b555-475f-bce9-940a11cbb171.png)


In short, we can simply retrieve the unique password line by using the piping technique **|** to combine **sort** and **uniq -u**. 

### Summary:
```
bandit8@bandit:~$ cat data.txt |sort | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
The password to gain access to the level 09's box is **UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR**


## :triangular_flag_on_post: Bandit Level 09 - 10

### Problem Description:
![image](https://user-images.githubusercontent.com/79222856/162504634-55d4a8af-1b86-485a-9060-71b3d439f831.png)

### Solution:
![image](https://user-images.githubusercontent.com/79222856/162506994-fa089c6b-9c84-4c9c-92c2-ea31739fd4c7.png)

### Explanation:
`data.txt` is a binary file, grep doesn't work directly, so I use `strings`, piping it out to `grep`.Try the **strings** command at this point. If you want to know more about what **strings** command does, read its manpage:
![image](https://user-images.githubusercontent.com/79222856/162508510-eb79b6ec-cc13-48bc-9cd0-79f3bd8ce595.png)

In other words, it searches the whole file for any string values it can examine and displays them in the output.
Now let us run a strings command on the **data.txt** file and **grep** only records containing the “=” characters, as per the hint given to us to pass this level. 

### Summary:
```
bandit9@bandit:~$ cat data.txt | strings | grep "="
========== the*2i"4
=:G e
========== password
<I=zsGi
Z)========== is
A=|t&E
Zdb=
c^ LAh=3G
*SF=s
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
S=A.H&^
bandit9@bandit:~$ 
```
The password to gain access to the level 10's box is **truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk**

## :triangular_flag_on_post: Bandit Level 10 - 11

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162509796-710ed14f-ac8e-4e75-8806-875b8e511852.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162510630-0971efdb-e6ab-46fc-8828-6cc34da705f2.png)


### Explanation:

`Base64` Encoded text is present in `data.txt`, This level primarily introduces us to **base64** encoding, which is one of the most widely used methods for encoding data in the worldworld. However, owing to the abundance of tools accessible online, it is simple to detect and decode.  which is decoded as follows:

![image](https://user-images.githubusercontent.com/79222856/162511619-220e98e1-2f45-4798-8c19-a0c0582b7119.png)

However, we can easily do a **base64** decode because the server is running on a Linux distribution and all Unix operating systems have built-in support for the **base64** command. 

### Summary:

![image](https://user-images.githubusercontent.com/79222856/162513426-032125ea-5dc7-4ed0-a104-7d8a658560d2.png)

The password to the level 11's box is **IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR**

## :triangular_flag_on_post: Bandit Level 11 - 12

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162515792-bffb1b74-79fb-46c7-aba5-c6c9ab749a3c.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162516128-87038a89-4526-4ebb-b972-d6e883f7299b.png)

Now, we can decode this using any decoding tool that you like.I myself use [CyberChef](https://gchq.github.io/CyberChef/) as the main tool for CTFs.

![image](https://user-images.githubusercontent.com/79222856/162516369-2f5f679f-b9fa-4cec-adcb-88227e9cefd9.png)

### Explanation:

As provided in the hint, we are required to perform a ROT13 “decode” on the file given. First, let’s look at the clue.
```
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh
```
Now, we can decode this using any decoding tool that you like. I myself use [CyberChef](https://gchq.github.io/CyberChef/) as the main tool for CTFs.

However, if you believe solving this problem using a built-in Linux command is sexier, there is a method to imitate the **ROT13** decoding process with the **tr** command: 
![image](https://user-images.githubusercontent.com/79222856/162518079-fd180097-6b2a-4359-bdec-c4dc3efbe78c.png)

For this problem, **tr** command is used to translate the first set of characters ‘A-Za-z’ to ‘N-ZA-Mn-za-m’ which is a rotation of 13 positions of the first set.Like below!
```
bandit11@bandit:~$ cat data.txt | tr "A-Za-z" "N-ZA-Mn-za-m"
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```
### Summary:

![image](https://user-images.githubusercontent.com/79222856/162518556-9346180f-588f-4896-8aa5-0c19ff1eb9a8.png)

The password to the level 12's box is **5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu**

## :triangular_flag_on_post: Bandit Level 12 - 13

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162583122-e55741ad-a421-444e-ad41-025b4e3438ad.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162583933-a4933073-bd77-4903-9ede-bb61d7ce7a5c.png)

![image](https://user-images.githubusercontent.com/79222856/162585034-3ff26805-ab69-42b7-9497-a0e1fb4f6c3b.png)

![image](https://user-images.githubusercontent.com/79222856/162584078-a7007721-31db-4fc1-8766-e4fba27b9638.png)

### Explanation:
This is one of the most difficult levels in the CTF challenge. Let's start by moving the file to a new directory under your name in the **/tmp** folder (make one with the **mkdir** command!).

```
bandit12@bandit:~$ mkdir /tmp/0xRh1d0Y
```
Copy the data.txt file from **~** to **/tmp/yourusername/**:
```
bandit12@bandit:~$ cp data.txt /tmp/0xRh1d0Y
```
Change the working directory to **/tmp/yourusername** using cd:
```
bandit12@bandit:~$ cd /tmp/0xRh1d0Y/
```
Let's see what's in the file using **cat**:

![image](https://user-images.githubusercontent.com/79222856/162584316-87fb45f5-cb56-42ea-a9ee-7eb9fe31ade5.png)

As you can see, this is a hexdump, which was converted by the **xxd** command.

![image](https://user-images.githubusercontent.com/79222856/162584457-454a49c7-7bd8-499a-999e-814d4409358e.png)

**xxd** is not really a hex-editor, it just displays hex. However, we can use it to convert files into hex, make edits to them with our favorite text editors, then convert the files back into the correct formats.

Anyway, now we have to perform a reverse hashdump using **xxd** command:

```
bandit12@bandit:/tmp/0xRh1d0Y$ xxd -r data.txt > secretpass.txt

```
After running the reverse hexdump command and saving the result to a file (I named mine "secretpass.txt"), use the **file** command to see what type of file it is.
```
bandit12@bandit:/tmp/0xRh1d0Y$ file secretpass.txt 
secretpass.txt: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
```
From here on onwards, the flow is as follows:

1. Using the file command, determine what format of file this is.
2. Using the mv command to alter the file type by renaming it to that specific file format extension.
3. Using the appropriate tool to decompress/unzip the files (in this case, **gzip** or **gunzip**, **bzip2** and **tar** play a significant role).
4. Repeat steps 1-3 until you get the file.

The list of commands I have is as below; it will be pretty long. It does, however, follow the process that I outlined before. To make things simpler to understand, I've included a "line break" after each change in file type. I hope it proves useful! 

### Summary:

```
bandit12@bandit:/tmp/0xRh1d0Y$ xxd -r data.txt > secretpass.txt
bandit12@bandit:/tmp/0xRh1d0Y$ ls
data.txt  secretpass.txt
bandit12@bandit:/tmp/0xRh1d0Y$ rm -rf data.txt
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass.txt
bandit12@bandit:/tmp/0xRh1d0Y$ file secretpass.txt 
secretpass.txt: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/0xRh1d0Y$ mv secretpass.txt secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ gunzip -d secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass
bandit12@bandit:/tmp/0xRh1d0Y$ file secretpass
secretpass: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/0xRh1d0Y$ mv secretpass secretpass.bz2
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass.bz2
bandit12@bandit:/tmp/0xRh1d0Y$ bzip2 -d secretpass.bz2
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass
bandit12@bandit:/tmp/0xRh1d0Y$ file secretpass
secretpass: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/0xRh1d0Y$ mv secretpass secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ gunzip -d secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass
bandit12@bandit:/tmp/0xRh1d0Y$ file secretpass
secretpass: POSIX tar archive (GNU)
bandit12@bandit:/tmp/0xRh1d0Y$ mv secretpass secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ tar xvf secretpass.tar
data5.bin
bandit12@bandit:/tmp/0xRh1d0Y$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/0xRh1d0Y$ mv data5.bin secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ tar xvf secretpass.tar
data6.bin
bandit12@bandit:/tmp/0xRh1d0Y$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/0xRh1d0Y$ mv data6.bin secretpass.bz
bandit12@bandit:/tmp/0xRh1d0Y$ bzip2 -d secretpass.bz
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass  secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ file secretpass
secretpass: POSIX tar archive (GNU)
bandit12@bandit:/tmp/0xRh1d0Y$ mv secretpass secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ tar xvf secretpass.tar
data8.bin
bandit12@bandit:/tmp/0xRh1d0Y$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/0xRh1d0Y$ mv data8.bin secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass.gz  secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ gunzip -d secretpass.gz
bandit12@bandit:/tmp/0xRh1d0Y$ ls
secretpass  secretpass.tar
bandit12@bandit:/tmp/0xRh1d0Y$ file secretpass
secretpass: ASCII text
bandit12@bandit:/tmp/0xRh1d0Y$ cat secretpass
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

```
The password to the level 13's box is **8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL**

## :triangular_flag_on_post: Bandit Level 13 - 14

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162629214-01b07caa-49b6-4999-bac0-7b6cd819a4ee.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162629570-c4fdb194-e500-4984-a27a-973884d49fe5.png)

![image](https://user-images.githubusercontent.com/79222856/162629611-c47bece0-b7a2-45d9-973e-ec2882ee779d.png)


### Explanation:

SSH protocol - including logging in without a password. Let's have a look at what's in the **sshkey.private** file that you were given in the **~** directory: 
```
bandit13@bandit:~$ cat sshkey.private 
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
ZufGtZEwWbFWw/vVLNwOXBe4UWStGRWzgPpEeSv5Tb1VjLZIBdGphTIK22Amz6Zb
ThMsiMnyJafEwJ/T8PQO3myS91vUHEuoOMAzoUID4kN0MEZ3+XahyK0HJVq68KsV
ObefXG1vvA3GAJ29kxJaqvRfgYnqZryWN7w3CHjNU4c/2Jkp+n8L0SnxaNA+WYA7
jiPyTF0is8uzMlYQ4l1Lzh/8/MpvhCQF8r22dwIDAQABAoIBAQC6dWBjhyEOzjeA
J3j/RWmap9M5zfJ/wb2bfidNpwbB8rsJ4sZIDZQ7XuIh4LfygoAQSS+bBw3RXvzE
pvJt3SmU8hIDuLsCjL1VnBY5pY7Bju8g8aR/3FyjyNAqx/TLfzlLYfOu7i9Jet67
xAh0tONG/u8FB5I3LAI2Vp6OviwvdWeC4nOxCthldpuPKNLA8rmMMVRTKQ+7T2VS
nXmwYckKUcUgzoVSpiNZaS0zUDypdpy2+tRH3MQa5kqN1YKjvF8RC47woOYCktsD
o3FFpGNFec9Taa3Msy+DfQQhHKZFKIL3bJDONtmrVvtYK40/yeU4aZ/HA2DQzwhe
ol1AfiEhAoGBAOnVjosBkm7sblK+n4IEwPxs8sOmhPnTDUy5WGrpSCrXOmsVIBUf
laL3ZGLx3xCIwtCnEucB9DvN2HZkupc/h6hTKUYLqXuyLD8njTrbRhLgbC9QrKrS
M1F2fSTxVqPtZDlDMwjNR04xHA/fKh8bXXyTMqOHNJTHHNhbh3McdURjAoGBANkU
1hqfnw7+aXncJ9bjysr1ZWbqOE5Nd8AFgfwaKuGTTVX2NsUQnCMWdOp+wFak40JH
PKWkJNdBG+ex0H9JNQsTK3X5PBMAS8AfX0GrKeuwKWA6erytVTqjOfLYcdp5+z9s
8DtVCxDuVsM+i4X8UqIGOlvGbtKEVokHPFXP1q/dAoGAcHg5YX7WEehCgCYTzpO+
xysX8ScM2qS6xuZ3MqUWAxUWkh7NGZvhe0sGy9iOdANzwKw7mUUFViaCMR/t54W1
GC83sOs3D7n5Mj8x3NdO8xFit7dT9a245TvaoYQ7KgmqpSg/ScKCw4c3eiLava+J
3btnJeSIU+8ZXq9XjPRpKwUCgYA7z6LiOQKxNeXH3qHXcnHok855maUj5fJNpPbY
iDkyZ8ySF8GlcFsky8Yw6fWCqfG3zDrohJ5l9JmEsBh7SadkwsZhvecQcS9t4vby
9/8X4jS0P8ibfcKS4nBP+dT81kkkg5Z5MohXBORA7VWx+ACohcDEkprsQ+w32xeD
qT1EvQKBgQDKm8ws2ByvSUVs9GjTilCajFqLJ0eVYzRPaY6f++Gv/UVfAPV4c+S0
kAWpXbv5tbkkzbS0eaLPTKgLzavXtQoTtKwrjpolHKIHUz6Wu+n4abfAIRFubOdN
/+aLoRQ0yBDRbdXMsZN/jvY44eM+xRLdRVyMmdPtP8belRi2E2aEzA==
-----END RSA PRIVATE KEY-----
```
How can we make use of it? Let's check out the manpage of **ssh**:

![image](https://user-images.githubusercontent.com/79222856/162629854-14f153c4-adbd-4093-be1d-dd6b12c7b99b.png)



And yes, by using:
```
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost 
bandit14@bandit:~$ 
```
Boom! You've already entered the box for level 14! The password may then be read from the **/etc/bandit_pass/bandit14** directory if you want to know it. All level passwords are kept in that directory, as indicated on the level 0 introduction page, however they can only be viewed by the level's user. 

### Summary:
```
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost 

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```
The password to the level 14's box is **4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e**

## :triangular_flag_on_post: Bandit Level 14 - 15

### Problem Description:

![image](https://user-images.githubusercontent.com/79222856/162630045-f7d3d9c2-5abb-4415-b6e4-60a53130e18f.png)

### Solution:

![image](https://user-images.githubusercontent.com/79222856/162630140-ed246219-e59d-4352-8422-c5366f84cb63.png)

### Explanation:

As mentioned in the level 0 introduction page, all level’s passwords are stored in **/etc/bandit_pass/** but they can only be accessed by the level’s user.

![image](https://user-images.githubusercontent.com/79222856/162630251-5ad2a479-78b1-4e53-b478-824b8492a64c.png)

Now that we are logged in to bandit14, we can retrieve its password, which is **4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e**, as I have done in the previous level. So, we need to submit it to port 30000 on localhost. We can do it using many ways, one of them is **echo** and **netcat**.

![image](https://user-images.githubusercontent.com/79222856/162630306-0aac2024-4d09-4306-935a-0de0f6768e18.png)

![image](https://user-images.githubusercontent.com/79222856/162630339-95b417b1-cc8c-404c-86d2-1b48e44fc98a.png)

Using pipes and redirectors, we can choose the input that is sent via the network, as well as what we do with the data once we receive them. On the command line we can use **nc** as a short name for the **netcat** program.
```
bandit14@bandit:~$ echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000
```
When we run this command, we take the **STDOUT** of echo and pipe it as the **STDIN** of netcat. The first argument for **netcat** is the **IP address** we want to send it to (which in this case, is **localhost** or **127.0.0.1**), and the second number is the **port** we want to send it to. **Netcat** will then send the password off to the correct location. 

### Summary:
```
bandit14@bandit:~$ echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr
```
The password to the level 15's box is **BfMYroe26WYalil77FoDi9qh59eK5xNr**

