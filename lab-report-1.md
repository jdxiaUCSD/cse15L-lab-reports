# LS

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

---

# CD

## 1. 
Input: 
`cd`

Output:
No output

Absolute Path: /Users/goats

`cd` without arguments directs to the home directory. Here, that home directory is /User/goats. This is not an error.

## 2. 

Input: 
`cd lecture1`

Output:
No output

Absolute Path: /Users/goats

`cd` with an argument changes the working directory to the argument, in this case being "lecture1". This directory was successfully changed, and there is no error.

## 3. 

Input: 
`cd Hello.java`

Output:
`cd: not a directory: Hello.java`

Absolute Path: /Users/goats

`cd`, like `ls` expects a directory path as an argument. However, "Hello.java" is not a directory path so the command produces an error.

---

# CAT

## 1. 
Input: 
`cat`

Output:
No output

Absolute Path: /Users/goats

When 'cat' is called without arguments, it will wait to take in a filename from the user. This is not an error, it is still running according to its purpose.

## 2. 

Input: 
`cat /Users/goats/desktop/lecture1`

Output:
`cat: /Users/goats/desktop/lecture1: Is a directory`

Absolute Path: /Users/goats

`cat` looks for a file, not a directory as an argument. Since a directory was provided, it resulted in an error message.

## 3. 

Input: 
`cat Hello.java`

Output:
`import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}%         `

Absolute Path: /Users/goats/lecture1

When `cat` recieves a file as an argument, it prints the contents of that file. This is not an error.



