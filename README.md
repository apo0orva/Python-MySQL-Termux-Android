# Python-MySQL-Termux-Android
- This is tutorial for those who want to use Python3 and MySQL (MariaDB) on Android!

- MySQL queries can run in MariaDB.

## Requirements
- [Termux](https://f-droid.org/packages/com.termux/) - Terminal emulator with packages
- [Pydroid 3](https://play.google.com/store/apps/details?id=ru.iiec.pydroid3) - IDE for Python 3

## Installing MySQL using Termux (Part-1)

_**Step-1:**_

Install Termux from [here](https://f-droid.org/packages/com.termux/).

\*_Download latest version._

\*_Do not install Termux app from playstore as it doesn't recieve the  updates and it doesn't support android 10 onwards._

_**Step-2:**_

Hold Termux app on homescreen and give storage permissions manually.

_**Step-3:**_

Check for any updates in-app. Type following commands line-by-line. You need to hit `Enter` key to run the command.

`pkg-get update`

`pkg-get upgrade`

_**Step-4:**_

Now download MariaDB using `pkg install mariadb`.

_**\*Step-5:**_

Now navigate to directory as mentioned below.

`cd /data/data/com.termux.files/usr/etc`

Then type `ls` and hit Enter.

If folder named `my.cnf.d` doesn't appears, you can create it with 

`mkdir my.cnf.d`

or else can skip this step.

_**Step-6:**_

After creating above directory, now it's time to install MySQL. For this execute following command.

`mysql_install_db`

_**Step-7:**_

- Now MySQL server has started at localhost level.
- Your MySQL doesn't have any password, hence you **cannot** connect it to Pydroid or any other programming language using connector!
- Now type following command to connect to MySQL database for _**1st time only**_!
`mysql`
- Now MySQL has started but it doesn't have any password, hence we will set it password manually by following commands.

```
use mysql;
ALTER USER 'root'@'localhost' IDENTIFIED BY 'your new password';
FLUSH PRIVILEDGES;
```

\*Hence, your username is `root` & password you entered in above code.

_**Step-8**_

**How to stop _MySQL_?**

- Now paste `ps aux | grep mysql` command in terminal & output will be as follow.

IMAGEIMAGEIMAGEIMAGEIMAGEIMAGEIMAGEIMAGEIMAGE

- Now you have to terminate two MySQL processes!
- Their id changes each time you run this command, so it is important to understand the output of the above code and get the id. In my case, id's are `20840` & `20920`.
- Now we terminate this process, for this we use `kill -9 <process id>` command.
- We terminate both this id's, in my case
```
kill -9 20840
kill -9 20920
```

Now MySQL DB is installed correctly with password.

_**Step-9**_

Now, whenever you want to intialize MySQL-DB, for this execute

`mysqld_safe -u root &` & Enter.

`mysql -u root -p` to connect to database.

`<password>` - Database password which you created above and hit Enter.

After using MySQL, you can stop database as mentioned in **step-8**.
