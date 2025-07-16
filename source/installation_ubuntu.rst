Installation on Ubuntu
======================

OPETIA can be installed on Ubuntu systems using the following steps:

1. **Install Python 3.8 or higher**

Ensure you have Python installed on your system. You can check your Python version by running in a terminal:

.. code-block:: bash

    python3 --version

If Python is not installed, you can install it using:

.. code-block:: bash

    sudo apt update
    sudo apt install python3 python3-pip

2. **Install Required Python Packages**

Install the required Python packages using pip. You can do this by running:

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install python3-tk
    sudo apt-get install eog

3. **Install FSL**

OPETIA relies on FSL for image processing. You can install FSL by following the instructions on the FSL website: `FSL Installation Guide <https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FslInstallation>`_.

4. **Clone the OPETIA Repository**

Clone the OPETIA repository from GitHub:

.. code-block:: bash

    git clone https://github.com/taha-parsayan/OPETIA.git

5. **Navigate to the OPETIA Directory**

Change to the OPETIA directory: 

.. code-block:: bash

    cd OPETIA

6. **Run OPETIA**

You can run OPETIA by executing the following command:

.. code-block:: bash

    python3 OPETIA.py

This will launch the OPETIA graphical user interface.

.. image:: images/OPETIA_main.png
    :alt: OPETIA Interface
    :width: 200px
    :align: center

.. raw:: html

    <br><br>