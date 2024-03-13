# Lab Report Five

---

## Part 1 - Debugging Scenario

> **Title: can't find modules on ieng6 (works on my local machine)**

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/3c49f7a5-d19d-4435-8255-3d99315cf485)

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/c426da8d-3429-4dda-b7a8-ef3127c0d7c5)

> Tutor Respoonse: Hmmmm, thats interesting, do you have the correct paths to the files? You seem to be on a mac, so the command seems correct. Can you double check if the `./lib/` folder exists?

> User: Oh! so sorry, I forgot to include it. uhhhh how do I include it?

> Tutor Response: Well, you could try the `scp` command we used in week three to copy the folder from your local computer to the server.

> User: It works now! Thank you so much!

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/9dd83181-f088-4041-bab2-75ce73ba020d)

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/0bd786d3-a069-4cae-ae1c-50a5a92f9f63)

### Information about the setup

The following are the file & directory structure(s)

```
ieng6 (before)

lab7
|-- ListExamples.java
|-- ListExamplesTests.java
|-- test.sh

local machine

lab7
|-- ListExamples.java
|-- ListExamplesTests.java
|-- test.sh
|-- lib
   |-- homcrest-core-1.3.jar
   |-- junit-4.13.2.jar

ieng6 (after)

lab7
|-- ListExamples.java
|-- ListExamplesTests.java
|-- test.sh
|-- lib
   |-- homcrest-core-1.3.jar
   |-- junit-4.13.2.jar
```

The bug was triggered only by `bash test.sh`, and without the `.jar` files, it wouldn't compile

Fixing the bug was simply copying the needed folders in, which was done using the `scp -r` command (recursivly as it was a folder).

___

## Part 2 - Reflection

Scripting, specifically in bash, wasn't something that I knew before. It was super useful to automate a chain of commands, especially with some control flow. How I used to execute terminal commands would be to type them one by one, getting the output manually and inspecting behavior manually, which was tedous and slow.

However, with scripting, a lot of that can be automated, and can also be testable and more reliable. 
