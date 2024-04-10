# CD

## 1. 
Input: 
`ls`

Output:
`Hello.java	README		messages`

Absolute Path: /Users/goats/desktop/lecture1

This output was a result of the `ls` command listing all of the current files in the directory "lecture 1". The command defaults to lecture 1 because I didn't include another argument (directory) for it to examine. This is not an error.

## 2. 

Input: 
`ls /Users/goats/desktop`

Output:
`Learn_AI-Assisted_Python_Programming.pdf
Screen Recording 2023-11-27 at 6.19.28 PM.mov
Screen Recording 2023-11-27 at 6.19.54 PM.mov
Screen Recording 2023-12-06 at 2.42.20 PM.mov
Screen Recording 2023-12-06 at 2.44.51 PM.mov
Screen Recording 2023-12-06 at 2.47.36 PM.mov
desktop
lecture1
project_github
secure-23-24_StatevBFDPC_12.12.23.pdf`

Absolute Path: /Users/goats

This output was a result of the `ls` command listing all of the current files in the directory "desktop". The command selects "desktop" as a directory because I included it as an argument. This is not an error.

## 3. 

Input: 
`ls Hello.java`

Output:
`ls: Hello.java: No such file or directory`

Absolute Path: /Users/goats/desktop/lecture1

This output is a result of leaving a filepath in an argument requiring a directory path. `ls` looks for a directory path as an argument, but I only provided it with a file path, resulting in an error.

