.. MLSteam documentation master file, created by
   sphinx-quickstart on Thu Nov 21 17:17:02 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

#####################
Welcome to MLSteam!
#####################

Here is the complete guide for training and developing your deep learning application with our platform.

To have a quick tutorial for using our system is to use :ref:`quick_start`. You will create a lab in a project on MLSteam with same code in the lab.


***********
Terminology
***********
Here we list all terminology used in MLSteam web.


* :ref:`project_term`
* :ref:`dataset_term`
* :ref:`lab_term`
* :ref:`job_term`
* :ref:`template_term`

.. _project_term:

Project
=======

The project is a collection of all works when you developing a DNN models. 
You can launch a either a jupyterlab (we call them labs) or launch experiments 
and training iterations (we call them jobs) will be kept and organized.


.. _dataset_term:

Dataset
=======

Dataset is any collection of data. You can organized you data into different directories (we call dataset) and modify datasets by web portal.
You can preview images and upload/download dataset files on dataset pages.
All datasets can be used in your labs.

.. _lab_term:

Lab
====

A lab is a web IDE (based on JupyterLab) organized in container basis.
You can develop DNN models in a lab and start training in the same lab or create another training containers (we call jobs) for keeping records.

.. _job_term:

Job
===

A job is a run of specific code, can be connected to dataset.


.. _template_term:

Template
========

A template is an example of a lab with specific type of DNN model with already preloaded dataset connected to it. 
Serves as an example or template for users.



.. toctree::
   :hidden:
   :maxdepth: 2

   content/getting_started
   content/dataset
   content/project
   content/lab
   content/job
   content/image
   content/template
   content/remote_access
   content/admin
   content/guide
   content/release_notes

