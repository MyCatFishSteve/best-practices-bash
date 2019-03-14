# Best Practices - Bash
This repository contains useful information everyone should know when creating bash scripts in order to maximise compatibility and writing reliable programs. Beginner topics will be covered first, such as preparing your bash script and how they can be executed and later, we will go into more complicated topics such as organising your code and making it secure.

This document owes a huge thanks to koalaman who provides ShellCheck, which is an amazing static analysis tool for inspecting your bash scripts and gives you recommendations for any changes you may need to make.

# Prerequisites
This tutorial assumes you are running a bash version higher than 3.2 (I am currently running these scripts on my mac)

# Shebangs
Shebangs are character sequences found at the beginning of files that help the operating system determine which program should be executed to handle a file. An example of this can be a file named "getindices" and it contains some bash scripting functions. When you execute this program via the system call exec(), it will most likely fail because the operating system is unable to figure out how to execute the program because it does not know which language you wrote it in.

By including a shebang in your script file, you can indicate to the operating system which program should be used to execute this file, this makes script files able to be executed by the operating system transparently without needing to parse it into an interpreter.

Instead of executing a function like this `/bin/bash getindices`, you can just write `getindices`. This reduces the amount of work needed to start a program since you do not need to explictly need to say which program should interpret a script.

A shebang in a bash file looks like this, it MUST exist on the first line of a file or else it will not be read by the operating system.

```
#!/bin/bash

commands here...
```
