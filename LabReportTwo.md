# Lab 3

## Part 1

***
### Code 

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/6f0695d8-569f-437e-84fc-a0ff0fab8aa8)

### Examples

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/80f8110a-7880-4c47-b18f-1a59a756cbe3)

The methods run are `handleRequest()` and `printLog()`. The relevant argumetns passeed in were `s=Hello` and `user=jpolitz` where `s` refered to the message and `user` refered to the user. The List `chatlog` is changed as a string documenting this message is put into the List.

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/91df55b3-e861-43be-93df-2e5b447a6bff)

The methods run are `handleRequest()` and `printLog()`. The relevant argumetns passeed in were `s=How are you` and `user=yash` where `s` refered to the message and `user` refered to the user. The List `chatlog` is changed as a string documenting this message is put into the List; specifically, there is already an existing elmeent, and this is added strictly added after the previous messages.

## Part 2

***

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/57421f01-b1bd-4b8c-843b-1a983dcade49)

The private key is `id_rsa` whereas the public key is `id_rsa.pub` (denoted by the pub). 

- Absolute path of private key: `/Users/chris/.ssh/id_rsa`
- Absolute path of publid key: `/Users/chris/.ssh/id_rsa.pub`


![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/87cafb48-f575-436a-b3ad-2b244dc3ee7d)

Here, I log into an `ieng6` without needed to provide a password (because my public key is stored on the server).

> ignore `Fig` and `Kitty`, they are some issues from my local setup

## Part 3

***

I didn't know how to copy files between two machines. Now, using the `scp` command, I can interface between my machines, and not just work in sandboxes (the machines themselves). This enables me to work in one environment when its convinient to, and then switch to the other if I need something (or space) that doesn't exist on the original machine. 
