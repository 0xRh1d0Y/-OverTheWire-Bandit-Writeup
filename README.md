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
