# How To Log Into a Course Specific Account On `ieng6` 
Step 1: Install VS Code
---
![vscode](https://user-images.githubusercontent.com/94575562/149442477-ac12a6a9-69d8-47dc-a5af-840d59af8983.PNG)

* Download Visual Studio Code using [this link](https://code.visualstudio.com/download)
* Opening VS Code should lead to a screen that looks like this:                    
![vscode1](https://user-images.githubusercontent.com/94575562/149443219-3a1b3671-9a6e-456d-bff8-62d8c7449429.png)

Step 2: Remotely Connecting
---
* Be sure to download [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) if you're on Windows
* This program allows your computer to connect to other computers
* Then, look up your course specific account [here](https://sdacs.ucsd.edu/~icc/index.php)
* Next, you'll want to open the terminal in VS Code by pressing Ctr+Shift+` or just by clicking on the New Terminal button under the Terminal tab on the tool bar on the upper left corner of your window
* Enter the following command into the terminal but with the `zz` replaced by the letters in your course specific account:
```
$ ssh cs15lwi22zz@ieng6.ucsd.edu
```
* The terminal will prompt you for a password which should be the same as the one you use for your UCSD account. Once entered the result should look like this:         
![step2](https://user-images.githubusercontent.com/94575562/149444976-9d3b438d-d882-4844-9e9b-ab5c453b794a.png)
