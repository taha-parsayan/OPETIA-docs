MRI Image Analysis
====================

**1. Overview:**

OPETIA provides a user-friendly interface for the pre-processing of T1-weighted MRI images, which is essential for accurate analysis in multimodal neuroimaging studies. The tool automates the entire process, ensuring that users do not need extensive technical knowledge to perform complex image analyses. However, all the details of the image pre-processing are provided and can be modified by the user if needed.

*Input data:*

- T1-weighted MRI (T1.nii.gz)

*Pre-processing steps:*

- Skull stripping (brain extraction)
- Non-linear registration to the MNI-152 template (2x2x2mm voxel size)(12 degrees of freedom followed by >12 degrees of freedom)
- Gray matter (GM), white matter (WM), and cerebrospinal fluid (CSF) segmentation

.. admonition:: Note

    In the `OPETIA paper <https://www.sciencedirect.com/science/article/pii/S1053811925002812>`_, registration to the MNI-152 template is done using a linear method. However, this has been changed to non-linear registration in the current version of OPETIA.

**2. Running the Structural image Pre-processing:**

From OPETIA, run the ``Structural image pre-processing`` tool.

.. image:: images/OPETIA_MRI.png
   :alt:  Image
   :width: 400px
   :align: center

.. raw:: html

       <br><br>

All needed to be done is to input the path to the folder containing the T1-weighted MRI image (data/subject1) and click on ``Process``. All the parameters will be set automatically.

**3. Output files:**

All the **outputs** will be saved in the folder ``data/subject1/OPETIA_output`` (automatically created). These include:

- ``structural_brain_std.nii.gz``: The skull-stripped T1-weighted MRI image in the MNI-152 space.
- ``structural_brain.nii.gz``: The skull-stripped T1-weighted MRI image in the native space.
- ``fast_pve_0.nii.gz``: CSF
- ``fast_pve_1.nii.gz``: GM (Cortex)
- ``fast_pve_2.nii.gz``: WM

**4. Quality Control:**

By pressing the ``Show processed image`` button, an image will appear containing the MNI-152 template on the background and the pre-processes T1 image as an overlay. The user can visually inspect the quality of the pre-processed image.

.. image:: images/MRI_QC.png
   :alt:  Image
   :width: 800px
   :align: center

.. raw:: html

       <br><br>

**5. Advanced Options:**

*Brain extraction:*

- ``Fractional intensity threshold``: The threshold (-f) for the brain extraction. The default value is 0.5, and it ranges between 0 and 1. The smaller the value, the larger the brain mask. If 0.5 leads to not missing some brain parts, try smaller values such as 0.4 or 0.3.
- ``Vertical gradient``: The vertical gradient (-g) for the brain extraction. The default value is 0. and it ranges between -1 and 1. Negative values (such as -0.2) includes more brain tissuesat the top (superior). Positive values (such as 0.2) includes more brain tissues at the bottom (inferior).
- ``Function/modality``: The modality for brain extraction. By default, ``Standard brain extraction using bet2`` is selected. If the image contains nech and face, use the ``Biasfield and nech cleanup`` option. It might take a longer time to extract the brain compared to bet2.

*Registration (native structural space to tandard space):*

- ``Standard template``: This is the standard template to which the native structural image will be registered. The default value is ``MNI152_T1_2mm_brain.nii.gz``. You can change it to any other template, such as ``MNI152_T1_1mm_brain.nii.gz``. The template is located at ``OPETIA/Templates``.

.. admonition:: Note
    
    You need to be careful with changing the standard space template. OPETIA provides tools that segments the brain into ROIs and extracts features from these regions. The ROIs incorporated in OPETIA are in the MNI152 2mm space. If you change the template to a different one, you need to make sure that the ROIs are also in the same space by modifying the files and images.

