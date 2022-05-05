# Shell Accounts Scripts

Date: Thu May  5 01:57:40 PM EDT 2022

## make_accounts

### Linux shell accounts

The ``make_accounts`` Bash script is meant to be run on the remote server.
It creates new shell users and puts those users in a pre-existing group.
It's best if that group exists prior to running this script,
but the script should handle creating a new group if it does not exist.

### MySQL shell accounts

I also use this script for a course that teaches relational databases using MySQL.
The script therefore produces a SQL script called **accounts.sql**
that will create MySQL accounts and individual databases for the new users.


Run it by logging into MySQL as root user and doing:

```
mysql> source accounts.sql
```

This course also requires a separate, course-wide MySQL database
that all students can access.
This script grants SELECT only privileges for the students on that database.
This script does not create that database but assumes it exists already.
The instructor for the course should be granted all privileges for the class
wide database.

**Warning:** Check the SQL script for any syntax errors before running.

The instructor's shell and MySQL accounts are not created with this script.
I've generally created this ahead of time and manually.

### To Do

The MySQL section of the script should be removed and made a standalone script 
since not all new shell users need MySQL accounts.

## remove_shell_accounts

I run this script at the end of the semester,
when all work has been completed and grades have been submitted,
to clear out the semester's users.

## remove_mysql_setups

This script is unfinished.
I've generally just logged into MySQL via phpMyAdmin,
selected all the relevant databases and users,
and deleted them there.
