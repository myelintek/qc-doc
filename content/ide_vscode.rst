#######
VSCode
#######

Step by step tutorial to setup VSCode for connecting to a lab


Install VSCode
-----------------

Download VSCode according to your operating system from `code.visualstudio.com <https://code.visualstudio.com/Download>`__


.. figure:: ../_static/remote_ide/vscode/vscode-install.gif

  downloaded and install VSCode.


Install extenstions in VSCode
--------------------------------

Open VSCode, search and install extension of *remote SSH*

.. figure:: ../_static/remote_ide/vscode/vscode-ssh.gif

  install *remote ssh* extension

SSH key and SSH config
-----------------------

Open a lab you want to access. Make sure the lab is in running state, click SSH tab at right navbar and generate SSH conifg.

You will see the following content and click the ssh key to download to your PC.

.. figure:: ../_static/remote_ide/sshkey.png
  :width: 600

  download SSH key

.. note::
  
  In Linux, you need to change the sshkey file to 600 mode.

  *ex. chmod 600 u0f2fc5d_sshkey*


Copy the ssh config by clicking copy icon at top-right of the config

.. image:: ../_static/remote_ide/copyconf.jpg
  :width: 600

  copy SSH config


.. note:: Windows10 accepts both / and \ as path separator


Paste ssh config in VSCode
-----------------------------

Open remote explorer in VSCode. Click configure in ssh targets. 

Paste the copied ssh config to ssh config in VSCode. Save the config file and the new created host will shown on the *SSH TARGETS* section.

.. image:: ../_static/remote_ide/vscode/vscode-sshconfig.gif


Connect to remote lab
-------------------------

Click created ssh target to connect to remote lab

.. image:: ../_static/remote_ide/vscode/vscode-connect.gif

.. note:: if there is an error while connecting, try to remove *know_hosts* file in .ssh folder


Open remote folder
---------------------

Congradulation! You have successfully connected to a lab. You can open a remote folder in the *Explorer* at left side of VSCode.

.. image:: ../_static/remote_ide/vscode/vscode-openfolder.gif


Console in VSCode
-----------------

You can also open a console in VSCode by dragging up from buttom of the window. 

.. image:: ../_static/remote_ide/vscode/vscode-edit.gif


Visit VSCode website to find out more extensions!

https://code.visualstudio.com/docs/editor/extension-gallery

