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

_**\*Step-6:**_

After creating above directory, now it's time to install MySQL. For this execute following command.

`mysql_install_db`

_**\*Step-7:**_

Now you have to intialize MySQL, for this execute

`mysqld_safe -u root &` & Enter.

`<password>` - Database password which you will use to view database in future!

_**\*Step-8:**_

Now MySQL server has started at localhost level.
