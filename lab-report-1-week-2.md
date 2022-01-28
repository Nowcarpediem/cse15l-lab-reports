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

Step 3: Trying Some Commands
---
Try running some commands like `cd`, `ls`, `pwd`, `mkdir`, and `cp` a few of different ways listed below:
* `cd ~`
* `cd`
* `ls -lat`
* `ls -a`

This is what running `ls -lat` and `ls -a` looked like for me:

![step3](https://user-images.githubusercontent.com/94575562/149446408-17afff79-498b-4554-b140-84b057408048.PNG)

Step 4: Moving Files with `scp`
---
* The `scp` command will allow you to copy files from your computer to a remote computer
* Create a file on your computer called `WhereAmI.java` and put the following contents into it:
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
* Then, run this command using the terminal from the directory where you made this file
```
$ scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/
```
* The result should look something like this:

![step4](https://user-images.githubusercontent.com/94575562/149448188-c71fe741-0046-4cb0-aad8-07e5cfbf1b48.PNG)
* Once you log into `ieng6` with `ssh` again and use `ls`, the file should be in your home directory:

![step4 2](https://user-images.githubusercontent.com/94575562/149449359-48dbbecc-f631-44f1-90c8-bc360c98bdb8.PNG)
* This allows you to run the program on the `ieng6` computer using `javac` and `java`

Step 5: Setting an SSH Key
---
By setting an SSH key, you no longer need to put in your password when logging into your `ieng6` account

Run this to set it up:
```
# on client (your computer)
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/joe/.ssh/id_rsa.
Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+
```

If you are on Windows, follow the extra `ssh-add` steps [here](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

Now, you need to copy the public key to the `.ssh` directory of your user account on the server:
```
$ ssh cs15lwi22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/joe/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```

You should now be able to `ssh` or `scp` from thie client to the server without entering your password:

![step5](https://user-images.githubusercontent.com/94575562/149450188-354bce29-4d94-4dad-9064-86117710c326.png)

Step 6: Optimizing Remote Running
---

Now, Try running the following code with your own account:

```
$ scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/
```
```
$ ssh cs15lwi22zz@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"
```

![step6](https://user-images.githubusercontent.com/94575562/149452574-a08ddad2-ca79-443d-91a3-d5573da1e38c.PNG)

This allows you to make a local edit to `WhereAmI.java`, then copy it to the remote server and run it in about 14 keystrokes.
