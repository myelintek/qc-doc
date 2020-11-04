.. _how_to_do_system_backup:

How to do system backup?
========================

In this guide, assuming you have a GPU server running MLSteam service and another Linux server as the backup server.
Following steps will show you how to do regular backup in case the GPU server malfunctioned.

1. Setup passwordless ssh login
-------------------------------
First login GPU server and generate a pair of authentication keys as root user. Do not enter a passphrase:

.. code-block:: bash

   sudo su
   ssh-keygen -t rsa

Now use ssh to create a directory ~/.ssh in remote backup server. (The directory may already exist, which is fine):

.. code-block:: bash

   ssh <user>@<remote IP> mkdir -p .ssh

Finally append ssh public key to remote backup server *.ssh/authorized_keys* and enter the ssh password one last time:

.. code-block:: bash

   cat ~/.ssh/id_rsa.pub | ssh <user>@<remote IP> 'cat >> .ssh/authorized_keys'

From now on you can login into remote backup server without password:

.. code-block:: bash

   ssh <user>@<remote IP>


2. Add cron job to backup folder daily
--------------------------------------
On the GPU server, use rsync to backup the sysem folder manully for the first time.
Assuming the data path is */mnt/sdb*, to backup entire folder to remote server path */mnt/backup*:

.. code-block:: bash

   rsync -av --delete /mnt/sdb <user>@<remote IP>:/mnt/backup

You should see the message showing data is backing up to the remote server.

.. note:: Please consult your system provider if you don't know where the *data path* is?

Now, edit the cron table file as root user, run:

.. code-block:: bash

    crontab -e

You will need to be familiar with vi in order to edit this file. Type "i" for insert, and then begin editing the cron table file.

Cron uses the following syntax: minute of hte hour, hour of the day, day of the month, month of the year, day of the week, command.

The following command will run the rsync command every night at 10 PM:

.. code-block:: bash

   0 22 * * * rsync -av --delete /mnt/sdb <user>@<remote IP>:/mnt/backup

The first "0" specifies the minute of the hour, and "22" specifies 10 PM.

After you are done configuring Cron, press escape, and then type ":wq"(without the quotes)
and press enter. This will save your changes in vi.

.. note:: If your server timezone is UTC and your timezone is UTC+8, please change 22 to 14 for running cron jobs in desired time.

