# Lab Report Four

## Assumptions

- 1 trial
- no comparison
- not completely optimal
- preloaded commands onto the terminal

## Test

1. Typed `git clone git@github.com:AskewP/lab7.git <enter>` to clone the repository into `ieng6`
![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/4fa5de15-39a7-498a-ace2-8ffccdbb6383)

2. Running Tests
   - `cd lab7 <enter>` to enter the directory
   - `bash t <tab> <enter>` to run the premade test script to run the test
![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/833769c5-7dde-4017-9dc2-e5ee306df8be)

3. Fixing Tests
   - `nvim L <tab> .j <tab> <enter>` to enter `ListExamples.java` file to edit it
   - ![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/285daf50-33f9-481e-b9bc-c556a950f8c9)
   - (In normal mode) `43jf1r2` which goes to the 43rd line below the curser, find the first instance of the character 1, and replaces it with the character 2
   - ![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/d96186b8-ebbd-4afb-ac15-3e1c97ad391d)
   - (In normal mode) `:wq` to save and quit out of vim
   - ![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/4fd88b6e-617b-48c8-9a7c-ac52ca4ac49e)

4. Rerun Tests
  - `bash t <tab> <enter>` to rerun the test script
![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/8371c2b5-37fd-4145-8d34-e28e842693a4)

5. Push to Github
  - `git add .` to add (stage) all changed files
  - `git commit -m "lab"` to commit all staged files with the lessage "lab"
  - `git push` to push to the current branch (`main`)
![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/d1399a31-bdfa-4aef-bc05-9bd829824edd)



