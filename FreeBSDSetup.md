## FreeBSD Reset or Recover Root Password

[FreeBSD reset password](https://www.cyberciti.biz/tips/howto-freebsd-reset-recover-root-password.html).

#### Procedure: Reset FreeBSD root user password

Step # 1: Start FreeBSD server/workstation.

Step # 2: Press Enter key at boot loader.

At Welcome to FreeBSD! boot menu press spacebar key to pause default booting

Type number 4 key (type 4 number) to boot into **single user mode**

![Image](img/freebsd.webp "icon")

Next you will see the following prompt from system:

`When prompted Enter full pathname of shell or RETURN for /bin/sh:`

Press **Enter key** to boot into a single user mode. Next, you will be immediately dropped into a single user mode without a root password.

You need to remount / (root) file system in read and write mode with mount command, type the following commands:

```
# mount -u /
# mount -a
```

Setup a new password with the passwd command for root user:

```
# passwd
```

Next type exit command to boot FreeBSD into multi-user mode environment:

```
# exit
```

OR You can just reboot the system:

```
# sync;sync
# reboot
```

For more information see man pages of passwd and mount commands.

## How To Add and Remove Users on FreeBSD

[Add/Remove Users](https://www.digitalocean.com/community/tutorials/how-to-add-and-remove-users-on-freebsd).

#### Introduction

On FreeBSD, like other Unix-like OSes, user accounts can be created to provide interactive access to the system. User accounts, when managed properly, can add a layer of system security by providing a way to limit individual user’s access to only the files and directories that it needs to accomplish its tasks.

In this tutorial, we will show you how to perform the following user management tasks on a FreeBSD server:

```
How To:
    Add a user
    Grant superuser privileges
    Remove a user
    Lock a user account
    Unlock a user account
```

#### How To Add a User

To add a user with adduser in interactive mode, which allows you to create one user at a time, simply run the command without arguments like this:

```
sudo adduser
```

At this point, you must provide information about the new user by responding to the series of prompts. Let’s take a look at an example of the prompts now, with example responses shown in red:

```
Username: gamer
Full name: Gamer
Uid (Leave empty for default):
Login group [gamer]:
Login group is gamer. Invite gamer into other groups? []: wheel
Login class [default]:
Shell (sh csh tcsh nologin) [sh]:
Home directory [/home/gamer]:
Home directory permissions (Leave empty for default):
Use password-based authentication? [yes]:
Use an empty password? (yes/no) [no]:
Use a random password? (yes/no) [no]:
Enter password: password
Enter password again: password
Lock out the account after creation? [no]:
```

After answering the prompts, a summary of the new user will be displayed:

```
Username   : gamer
Password   : *****
Full Name  : Gamer
Uid        : 1002
Class      :
Groups     : gamer wheel
Home       : /home/gamer
Home Mode  :
Shell      : /bin/sh
Locked     : no
OK? (yes/no): yes
```

If you respond yes, the user will be created and a confirmation will be provided:

```
adduser: INFO: Successfully added (gamer) to the user database.
```

Whether you create the user or not, you will see the following prompt:

```
Add another user? (yes/no): no
Goodbye!
```
