####
Lab
####

A lab is a web IDE (based on JupyterLab). Here we listed all available operations in each section.

* :ref:`create_lab`
* :ref:`browse_lab`
* :ref:`stop_lab`
* :ref:`start_lab`
* :ref:`attach_dataset_lab`
* :ref:`pass parameters`
* :ref:`lab_tensorboard`
* :ref:`commit_lab`
* :ref:`delete_lab`


.. _create_lab:

Create lab
==========

To create a lab, click *Lab* tab in a project page and click *New Lab* button.

.. figure:: ../_static/lab/list_lab.png

  click *Lab* tab in project page

.. figure:: ../_static/lab/create_lab.png

  click *new lab* button

Select a container image to create a lab. The recommanded image is *myelintek/python-gpu* which built-in all common libraries for deep learning.
Then, set the number of GPU to use within the lab, add comments if needed.
Click *Submit* to create the lab!

.. figure:: ../_static/lab/create_lab_modal.png

  create a lab with 1 GPU and python-gpu:v12 image


.. caution::

  GPU number is exclusive for each lab and job. Be caution that system may run out of GPU resources and labs can not be launched unless GPU resources are released.

.. tip::

  Set GPU number to 0 means the lab only use CPU.

.. _browse_lab:
 
Browse labs
===========

To browse a lab, click *Lab* tab in a project page and click lab id or *browse* button at the action column.

.. figure:: ../_static/lab/view_lab.png

  click lab id or *browse* button to open the lab

.. figure:: ../_static/lab/detail_lab.png

  See the detail of the lab.

.. _stop_lab:

Stop lab
========

To start a lab, click *Running* button and select *Stop*

.. image:: ../_static/lab/stop_lab_in.png

or click *Stop* at the lab list page.

.. image:: ../_static/lab/stop_lab_out.png


.. _start_lab:

Start lab
=========

To start a lab, click *Done* button and select *Start* 

.. image:: ../_static/lab/start_lab_in.png

or click *Start* at the lab list page.

.. image:: ../_static/lab/start_lab_out.png

.. _attach_dataset_lab:

Attach dataset to the lab
=========================

To attach a dataset, select the desired dataset in dataset section and click *attach dataset*.

.. figure:: ../_static/lab/attach_dataset.png
  :width: 400

  attach *developer1/mnist* dataset for this lab.

.. note::

    Attaching dataset will automatically restart the lab, make sure all the files saved already.


.. figure:: ../_static/lab/attach_dataset_alert.png
  :width: 500

  confirm to restart the lab


Attached dataset info will appear on the dataset section.

.. image:: ../_static/lab/attach_dataset_done.png
  :width: 400

Dataset files can be browsed in the window on the left under `/input` directory.

.. figure:: ../_static/lab/attach_dataset_file.png
  :width: 300

  browse dataset files in /mlsteam/input folder

Add new directory to dataset, if needed.

.. image:: ../_static/lab/attach_dataset_folder.png
  :width: 300

Upload new files to dataset, if needed.

.. image:: ../_static/lab/attach_dataset_upload.png
  :width: 300

Upload a zip file to lab.

.. image:: ../_static/lab/zipfile.png

Launch the terminal and unzip the file.

.. code-block:: batch

  unzip <file_name.zip>

.. image:: ../_static/lab/unzipfile.png

.. _pass parameters:

Pass parameters
===============

Users can update parameters (hypter-parameters) of a model by defining parameters on web page. Parameters supports YAML format definition and also supports multiple values per key value. System will automatically create multiple jobs for all combinations and run created jobs in parallel on different GPUs.

In your model source code. Please import mlsteam function

.. code-block:: python

  from mlsteam import stparams

Replace code as below to enable parameter update from web page. in this example, we define 'train_bs' keyword.

.. code-block:: python

  -      default=128,
  +      default=stparams.get_value('train_bs', 128),

All parameters will show on the right hyperparameter section.

.. image:: ../_static/lab/list_params.png
  :width: 400

Use comma separator to pass multiple values, or select multiple values from a list to create multiple jobs.

.. image:: ../_static/lab/custom_params.png
  :width: 400

Click *Reset* button to reset to default parameters.

.. image:: ../_static/lab/reset_params.png
  :width: 400

Now you can define default keyword value in mlsteam.yml of a lab.

If you want to make a dropdown and selector, use "-" to perform it is list.

If you want to make a text editor, use type *String* or type *Int*.

.. image:: ../_static/lab/default_params.png
  :width: 400


.. _lab_tensorboard:

Use Tensorboard
===============
Users can open tensorboard for current lab. First, use classification template to open a lab. then, type following command in console to generate checkpoint files.

.. code-block:: console

  python2 trainer.py --num_gpus=1 --batch_size=32 --network=lenet.py --data_dir=../input/mnist --train_dir=backup

checkpoint files will located in backup folder. Now, click tensorboard -> start button on top-right corner of lab page.
    
.. image:: ../_static/lab/start_lab_tensorboard.png
  :width: 400

Click tensorboard button again, the dropdown list will show OPEN button. Click open button to open tensorboard in a new tab.

.. image:: ../_static/lab/open_lab_tensorboard.png
  :width: 400

The tensorboard will read current lab folder and display content accordingly.

.. note::

  If the new tab page shows 502, please reload page again.

To close tensorboard, click tensorboard -> close button to terminate tensorboard process.

.. note::

  tensorboard will been terminated when the associated lab is deleted.


.. _commit_lab:

Commit lab
==========

First attach dataset to the lab.

Write necessary code and adjust config file `mlsteam.yml`.

.. image:: ../_static/lab/lab_config.png

Click "Commit and run".

.. image:: ../_static/lab/commit_run.png

Check parameters if any wrong.

.. image:: ../_static/lab/check_params.png
  :width: 400

This will create a job from the code that lab contains.

Browse job to see output. In our case, output is the content of folder `/mlsteam/input`.

.. figure:: ../_static/lab/run_output.png

  a training job with output display


.. _delete_lab:

Delete lab
==========
On the project page click "Lab" button.
Stop needed lab.
On the list of labs page click on the trash icon on the side of the lab name.

.. image:: ../_static/lab/delete_lab.png
