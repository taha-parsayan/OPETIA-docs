Installation
======================

OPETIA can be installed on macOS/Windows/Ubuntu systems using the following steps:

1. **Install Conda**

   You can install Conda from the official website:

   `Conda Installation Guide <https://www.anaconda.com/download>`_

   (Choose Miniconda for your OS: Windows, macOS, or Linux.)

   Check if Conda is installed correctly by running the following command in your terminal (macos/Ubuntu) or Anaconda Prompt (Windows):

   .. code-block:: bash

      conda --version

2. **Install git**

   In the terminal (macOS/Ubuntu) or Anaconda Prompt (Windows), run the following command to install git:
   .. code-block:: bash

      conda install -c anaconda git
      git --version

3. **Download OPETIA**

   You can download OPETIA from its GitHub repository by running the following command in the terminal or Anaconda Prompt:

   .. code-block:: bash

      git clone https://github.com/taha-parsayan/OPETIA.git
      cd OPETIA


4. **Install the packages**

Run the following command in your terminal or Anaconda Prompt to install the required packages:

   .. code-block:: bash

      conda env create -f environment.yml

5. **Run OPETIA**

   Activate the OPETIA environment and start OPETIA by running the following commands:

   .. code-block:: bash

      conda activate opetia
      python OPETIA.py

   You should see the OPETIA interface as shown below:

.. image:: images/OPETIA_MRI.png
   :alt: OPETIA Interface
   :width: 800px
   :align: center

.. raw:: html

   <br><br>
