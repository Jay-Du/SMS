# SMS

SMS
===============

*SMS* contains three parts. The first part is *SMSaligner*, which is composed of *SMSaligner2ref* and *SMSaligner2pairwise*. The second part is *SMScorrect*. And the third part is *SMSca*. All these three parts are compiled in *SMS*.

If you are already using Sphinx or Markdown for your docs, skip ahead to
:ref:`import-docs`.

Installation
----------------

.. _in-bst:

Before your start
~~~~~~~~~~~~~~~~~~~

SMS requires a recent version of the gcc(4.8+) or perl(5.8+). Gcc 4.7 or perl 5.8 earlier will not work. If you would like to build the code form source, you need to have the gcc or perl.

**Prerequisites**

* gcc or perl

Installation
~~~~~~~~~~~~~~~~~~~

The pre-compiled version is recommended to users who want to run SMS, without doing development. 

① You can download suitable pre-compiled tar from our website.
Or just run:

  ``$ wget http://.........../SMS.tar.gz``
  
And if wget not available, you can use curl instead:

  ``$ curl –L http://........./SMS.tar.gz > SMS.tar.gz``

②Extract the pre-compiled tar. Run:

  ``$ tar zxvf SMSAligner.tar.gz``

③ Enter the extracted subdirectory. Run

  ``$ cd SMS/``

④make

  ``$ make``

Then SMS will be installed sucessfully.
