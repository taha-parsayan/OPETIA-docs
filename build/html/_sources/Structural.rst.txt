MRI Image Analysis
====================

**1. Overview:**

OPETIA provides a user-friendly interface for the pre-processing of T1-weighted MRI images, which is essential for accurate analysis in multimodal neuroimaging studies. The tool automates the entire process, ensuring that users do not need extensive technical knowledge to perform complex image analyses. However, all the details of the image pre-processing are provided and can be modified by the user if needed.

Input data: T1-weighted MRI (T1.nii.gz)

Pre-processing steps:

- Skull stripping (brain extraction)
- Non-linear registration to the MNI-152 template (2x2x2mm voxel size)
- Gray matter (GM), white matter (WM), and cerebrospinal fluid (CSF) segmentation

.. admonition:: Note

    In the `OPETIA paper <https://www.sciencedirect.com/science/article/pii/S1053811925002812>`_, registration to the MNI-152 template is done using a linear method. However, this has been changed to non-linear registration in the current version of OPETIA.

**2. Running the Structural Pre-processing:**

From OPETIA, run the ``Structural pre-processing`` tool.

.. image:: images/OPETIA_MRI.png
   :alt:  Image
   :width: 400px
   :align: center

.. raw:: html

       <br><br>

All needed to be done is to input the path to the folder containing the T1-weighted MRI image (data/subject1) and click on ``Process``. All the parameters will be set automatically.

All the **outputs** will be saved in the folder ``data/subject1/OPETIA_output`` (automatically created). These include:

- ``structural_brain_std.nii.gz``: The skull-stripped T1-weighted MRI image in the MNI-152 space.
- ``structural_brain.nii.gz``: The skull-stripped T1-weighted MRI image in the native space.
- ``fast_pve_0.nii.gz``: CSF
- ``fast_pve_1.nii.gz``: GM (Cortex)
- ``fast_pve_2.nii.gz``: WM

**3. Quality Control:**

By pressing the ``Show processed image`` button, an image will appear containing the MNI-152 template on the background and the pre-processes T1 image as an overlay. The user can visually inspect the quality of the pre-processed image.

.. image:: images/MRI_QC.png
   :alt:  Image
   :width: 800px
   :align: center

.. raw:: html

       <br><br>
