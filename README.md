# linux-privilege-escalation-docker

A guided privilege escalation challenge solved inside a Docker container running Linux, built as part of a cyber security course

## Scenario

Starting as a low privilege user, the goal was to reach a root shell on the machine

## Approach

- Explored the file system starting from the low privilege user's home directory
- Located a scripts folder inside an admin user's home directory
- Checked cron configuration files and cron directories to find scheduled jobs
- Identified that a script in that folder was being executed automatically by cron with root privileges
- Edited the script to add a command that spawns a shell
- Waited for the cron job to run and obtained a root shell

## Commands used

    cd ..
    cd ..
    cd home
    ls -l
    cd jack
    ls -l
    cd scripts
    ls -l
    ls -l /home/jack/scripts
    cd user_scripts
    ls -l
    ls -l /home/jack/scripts/user_scripts
    cd /home/jack/scripts/user_scripts
    ls -l
    cat /etc/crontab
    ls -ld /etc/cron.hourly
    ls -ld /etc/cron.daily
    ls -ld /etc/cron.weekly
    ls -ld /etc/cron.monthly
    ls -l /etc/cron.hourly
    ls -l /etc/cron.daily
    ls -l /etc/cron.weekly
    ls -l /etc/cron.monthly
    nano admin_script.sh
    ls -l /bin/bash
    /bin/bash -p
    whoami

## Note

This was solved inside a controlled Docker lab environment provided as part of a course, and is intended only for authorized lab and educational use

## Skills demonstrated

Linux file permissions, cron jobs, users and groups, privilege escalation fundamentals
