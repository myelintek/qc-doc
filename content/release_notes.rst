*************
Realese notes
*************

v3.6.1
======


Features
++++++++

* Refactor dataset page
* Make lab ssh, dockerfile build and CVAT configurable in admin page
* Add home page for project

BugFixes
++++++++

* Fix tensorboard buttons not automatically update
* Close commit & run menu when click 'start'
* Fix image list page sometime shows 404 error
* Fix i18n translations
* Fix pie chart shows running tasks
* Bugfixes


v3.6.0
======


Features
++++++++

* UI/UX refactoring
* Add user storage space quota setting
* Add create/update timestamp in image table
* Add # of gpu setting when click "commit & run" in lab page
* Upport attaching multiple datasets in a lab


v3.5.2
======

BugFixes
++++++++

* Fix usage time api


v3.5.1
======

BugFixes
++++++++

* Fix time zone issue for query user usage API
* Fix can't delete image issue
* Security fixes


v3.5.0
======

Features
++++++++

* Add lab/job disk space limitation
* Add lab/job cpu, memory and max-openfile to 65535 limitation
* Show available disk space in dataset page
* Simplified lab page

BugFixes
++++++++

* Fix cookie timeout not redirect to logout page issue
* Fix auditlog timezone incorrect issue
* Fix lab attach dataset may error issue
* Fix job can't delete while in waiting state
* Fix certificate doesn't backup issue


v3.4.2
======

Features
++++++++

* Add calculate users usage time API

BugFixes
++++++++

* Fix MLSteam upgrade nginx not reload issue
* Fix frequently login system cause instability issue
* Add saving state in Lab when stopping, fix stop/restart timeout issue
* Add repository create timeout issue
* Fix https certificate won't automatically renew issue


v3.4.1
======

BugFixes
++++++++

* Fix entry.ipynb not found issue
* Fix MLSteam service startup failed issue (wtforms upgrade)
* Fix public dataset permission error for normal users issue
* Fix error when mlsteam.yml missing param_definition field
* Fix restart Lab looks like hanging issue
* Fix auditlog shows duplicate stop lab/job messages
* Fix delete job with tensorboard opening cause system crash issue


v3.4.0
======

Features
++++++++

* Add augmentation template
* Refactor template yaml format, yaml file will sync with right panels parameters
* Add dockerfile build page in project
* Add system restart button for administration
* Add fullscreen button in labs
* Make lab in full page
* Add datasets overview in admin dashboard

BugFixes
++++++++

* Fix device info doesn't show issue
* Fix project table overlap issue
* Fix background color in project member setting dropdown list


v3.3.2
======

Features
++++++++

* Launch lab can choose no GPU environment
* Better ssh config layout at Lab

BugFixes
++++++++

* fix right menu at lab collapse issue
* fix host status incorrect issue when host changed IP
* fix duplicated docker images in projects


v3.3.1
======

Features
++++++++

* add auditlog api
* lab dataset changed to dropdown list

Bugfixes
++++++++

* fix certificate expire date
* fix nfs delete files issue when using NFSv4


v3.3.0
======

Features
++++++++

* Image management per project  
* Save Labs environment when stop/restart a lab
* Self hosted image repository (optional)
* User groups management
* Confirm parameters when committing a job
* Parameter settings in a lab changed from YAML to Form
* Adjust project page layout
* [Classification template]: move tfrecord generation to training stage
* Add Iris Flower template
* Add admin API for list projects and tasks
* Custom log path for tensorboard
* Auto restart lab when attaching dataset

Bugfixes
++++++++


* Fix Job output missing print messages issue
* Fix cancel uploading datasets issue
* Fix labs crash if yaml file format incorrect issue
* Fix blank when loading lab page issue
* Fix elapsed time start from waiting issue
* Fix NFS cannot delete issue
* Fix jupyterlab header hidden issue
* minor bug fixes

v3.2.2
======

Features
++++++++

* session expire extends from 1hour to 5 hours

Bugfixes
++++++++


* Fix unclick gpu limit check not working issue.
* Fix jobs elapse time incorrect issue.
* Fix jobs gpu limit incorrect issue.
* Fix jobs disappear issue
* Fix can't find hostid for licensing issue

v3.2.1
======

Features
++++++++

* Add certificate setting page in admin page

Bugfixes
++++++++

* Show clear NFS mount error message
* Fix create user without roles defined error
* Fix run job from default lab becoming error state
* Minor bugfixs

v3.2.0
======

Features
++++++++

* Auto stop Lab or Job while GPU in high temperature (90 celsius)
* Refactor top-right menu
* Admin role and developer role become exclusive. Admin role users can do same things as developer role.

v3.1.1
======

Features
++++++++

* Add owner in system tasks list
* Add GPU and Disk monitor
* Add Chinese language

Bugfixes
++++++++

* Fix jupyterlab starts in blank screen issue
* Fix allocated GPU unreleased issue

v3.1.0
======

Features
++++++++

* Display elapsed and estimated time in job page
* Add tensorboard in job and lab pages
* Add example code for default jupyterlab page

Bugfixes
++++++++


* Fix NFS mount affects fstab issue
* Fix can't stop lab/job issue
* Fix upload large amount of files hang issue
* Minor bugs fix

v3.0.0
======

* Python3 version, refactor code.
* Introduce Lab, Job and templates.
* Fix dataset yolo annotations file works in relative path
* Add log_parser.py support for job metrics
* Add lab params syntax check
* In production mode
* Fix nfs not unmount when delete nfs dataset.





