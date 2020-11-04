########
PyCharm
########

The following tutorial is based on Windows 10, 2019.3.3 (Professional Edition)

.. caution::

  Please note that remote connection feature only supported at PyCharm Professional!

Install PyCharm
================

Download PyCharm according to your operating system from `jetbrains.com/pycharm <https://www.jetbrains.com/pycharm/download/>`__


.. image:: ../_static/remote_ide/pycharm/install.png

SSH key
=========

Open your lab and make sure the ssh key is generated. Click the ssh key to download to your PC.

.. figure:: ../_static/remote_ide/sshkey.png
  :width: 600

  SSH Config, download SSH key by clicking the ssh key link

.. tip::

  downloading will start automatically, if it does not press the ssh key link.

.. note:: 

  In Linux, you need to change the sshkey file to 600 mode.

PyCharm Project
===============

Open the PyCharm and create a new project.

.. image:: ../_static/remote_ide/pycharm/pycharm_open.png

Create a new *SSH Interpreter* from **Pure Python** -> **Existing interpreter** -> **...**

.. image:: ../_static/remote_ide/pycharm/pure_python.png

Setup Remote Interpreter
------------------------

Type in the SSH host IP, port and user information in **SSH Interpreter** section. (Fill in the information based on *SSH Config* above)

.. image:: ../_static/remote_ide/pycharm/ssh_interpreter.png

Click *Next* and PyCharm will try to connect to the Lab, click *Yes* to continue.

.. image:: ../_static/remote_ide/pycharm/connect.png

PyCharm will ask you for authentication, select the downloaded SSH Key at **Key pair** -> **Private key file**.

.. image:: ../_static/remote_ide/pycharm/private_key.png

Once PyCharm successfully connect to the lab, you can set the interpreter path */usr/bin/python3*. Then, click *Finish* to complete the interpreter setup.

.. image:: ../_static/remote_ide/pycharm/python_interpreter.png

Now the remote interpreter is added, click the *Create* button to open the project page.

.. image:: ../_static/remote_ide/pycharm/create.png

.. tip::

  You can select the *remote project location* at this page or later.

Project Files Synchronize
==========================

In PyCharm, all the file editions happen in you PC. We have to download lab files to your PC first. Click **Tools** -> **Deployment** -> **Configuration** to select remote folder.

.. image:: ../_static/remote_ide/pycharm/configuration.png

Select remote folder by clicking *remote host* -> *Mappings* -> *Deployment path*.

.. image:: ../_static/remote_ide/pycharm/deployment.png

Choose the remote path **/mlsteam/lab** and click *OK*.

.. image:: ../_static/remote_ide/pycharm/deployment_path.png

Now we can download the remote */mlsteam/lab* folder to your PC.

First, select your project folder, in this case is **untitled** at left column of PyCharm. Then, click **Tools** -> **Deployment** -> **Download from** -> remote host.

.. image:: ../_static/remote_ide/pycharm/download_file.png

The download should proceed and you will see the following messages if the lab has many files.

.. image:: ../_static/remote_ide/pycharm/download_log.png

You can browse and edit the loaded files in left column of PyCharm. Any modification in the files will be synchronized to remote folder automatically.

.. note::

  If you want to synchronize(upload) local PC files to remote manually by clicking **Tools** -> **Deployment** -> **Sync with Deployed to ...**
