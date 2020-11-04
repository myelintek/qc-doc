.. _admin:

**************
Administration
**************

To enter administration settings click the bottom-left corner button.

Default login
=============

The default administration credentials are **admin/admin**.

.. image:: ../_static/admin/popup.png

Profile
=======

It shows current user profile and change password operation.

.. image:: ../_static/admin/profile.png

.. image:: ../_static/admin/change_password.png


Account
=======

User
----

In user managment tab

Allows create, edit and delete user.

Create
++++++

Click "Users" button.

.. image:: ../_static/admin/create_user.png

Click "Create" button.

.. image:: ../_static/admin/create_user2.png

Fill username and password.

Select single role from drop down list.

Gpu limit is how many gpus can this user occupy, "-1" means no restriction.

Manage group if user needs.

.. image:: ../_static/admin/create_user_modal.png

Edit
++++

Select user that needs to be edited, click "Edit" button.

.. image:: ../_static/admin/edit_user.png

Fill new info.

.. image:: ../_static/admin/edit_user_modal.png

Delete
++++++

Select user that needs to be deleted, click "Delete" button. Confirm.

.. image:: ../_static/admin/delete_user.png

Group
-----

Is group managment tab

Allows new and delete group.

Create
++++++

Click "Create" button.

.. image:: ../_static/admin/create_group.png

Fill group name and confirm.

.. image:: ../_static/admin/create_group_modal.png

Delete
++++++

Select group that needs to be deleted, click "Delete" button. Confirm.

.. image:: ../_static/admin/delete_group.png


Dashboard
=========

Task
----

Shows a list of currently running instances of labs and jobs.

.. image:: ../_static/admin/list_task.png

Stop
++++

Select the instance that needs to be stopped, and then click "Stop".

Only running status can be stopped.

.. image:: ../_static/admin/stop_task.png

Delete
++++++

Select the instance to be deleted, and click "Delete" to delete the task.

Only not running status can be deleted.

.. image:: ../_static/admin/delete_task.png

Project
-------

Project management tab. Shows list of projects.

.. image:: ../_static/admin/list_project.png

Create
++++++

Click create button.

.. image:: ../_static/admin/create_project.png

Fill project name and annotation, click "Create".

.. image:: ../_static/admin/create_project_modal.png


Members
+++++++

To edit project members click "Members" button next to the project name.

.. image:: ../_static/admin/members_project.png

To add user to the project click "Add member", then type their name, select permissions and click "Save", then click "Done".

.. image:: ../_static/admin/members_project_modal.png

To delete user from project click "Delete" next to the username, then click "Done".

.. image:: ../_static/admin/delete_members_project.png

Delete
++++++

Select needed project and click "Delete" button. Confirm.

.. image:: ../_static/admin/delete_project.png

Auditlog
--------

Log of system events in chronological order. Use "Search" box on top to look for specific events.

.. image:: ../_static/admin/auditlog.png

Device
======

Shows All hosts' hardwave informations.

.. image:: ../_static/admin/view_device.png


Setting
=======

Host
----

Shows list of hosts in the system.

.. image:: ../_static/admin/list_host.png

Create
++++++

First on the target host create a sudo user account.

Give it the password-less privilege for mount related commands. For this create fallowing file `/etc/sudoers.d/<account>` with content

.. code-block:: console

  <account> ALL=(ALL) NOPASSWD: /usr/bin/mount,/usr/bin/umount,/bin/sh

Then generate the pair of ssh-keys (select all defaults). For this on host machine console type:

.. code-block:: console

  ssh-keygen -t rsa -b 4096 -C "<your_string>"
  eval "$(ssh-agent -s)"
  ssh-add ~/.ssh/id_rsa
  cat ~/.ssh/id_rsa.pub > ~/.ssh/authorized_keys

On MLSteam webportal Host page click "Create". 

.. image:: ../_static/admin/new_host.png

Then fill the form with ip address, account name and for "SSH KEY" field copy the content of `~/.ssh/id_rsa`.

.. image:: ../_static/admin/new_host_modal.png

Delete
++++++

Select needed host and click "Delete" button. Confirm.

.. image:: ../_static/admin/delete_host.png

Certificate
-----------

Shows list of certificates in the system.

.. image:: ../_static/admin/list_certificate.png

Create
++++++

Click create button.

.. image:: ../_static/admin/create_certificate.png

Input certificate name and doamin name, click "Test anc Create". (Optional, email) 

.. image:: ../_static/admin/create_certificate_modal.png

Delete
++++++

Select needed host and click "Delete" button. Confirm.

.. image:: ../_static/admin/delete_certificate.png

Repository
++++++++++

License
+++++++

Shows current license file.

If license needs to be updated click "Edit" to input new license file.

.. image:: ../_static/admin/license_system.png

Input license text in the field and click "Save".

.. image:: ../_static/admin/license_system_modal.png
