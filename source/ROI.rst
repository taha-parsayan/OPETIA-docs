Feature extraction
=========================

**1. Overview:**

OPETIA provides a user-friendly interface for the quantification of the PET and MRI images and feature extraction. The software segments the bain into 115 ROIs (96 cortical and 19 subcortical ROIs) and extracts image features from each ROI.

*Input:*

- Folder containing the results of MRI and PET pre-processing (data/subject1/OPETIA_output)

*Outputs:*

- Images of 96 cortical ROIs (according to the Harvard-Oxford brain atlas)
- Images of 19 subcortical ROIs (according to the Harvard-Oxford brain atlas)
- Cerebral volume measurement (mm3) from each ROI
- Standardized Uptake Value (SUV) from each ROI (mean, min, max, SD)
- Standardized Uptake Value Ratio (SUVR) from each ROI (mean, min, max, SD)

**2. Running the ROI analysis:**

From OPETIA, run the ``ROI analysis`` tool.

.. image:: images/OPETIA_ROI.png
   :alt:  Image
   :width: 400px
   :align: center

.. raw:: html

       <br><br>

*Setting the parameters:*

- ``Folder including pre-processed data``: Path to the folder containing the MRI and PET image pre-processing results (data/subject1/OPETIA_output)
- ``Tracer radioactivity``: The remaining radioactivity of the radiotracer at the time of image acquisition (please refere to OPETIA paper, Equation 3).

.. admonition:: Note

    Best practice is to set the ``Tracer radioactivity`` to 1. This will still lead to correct SUVR calculation, although the SUV will not be calculated correctly. In this case, leave the body weight and height as default or any other value.

    This is due to the fact that SUVR = SUV / reference reigion SUV. Therefore ``Tracer radioactivity``, ``Body weight (kg)``, and ``body height (m)`` will cancel out.

- ``Body weight (kg)``: The weight of the subject in kg.
- ``body height (m)``:The height of the subject in m.
- ``Type of measurement``: Using the body weight or other options (if ``Tracer radioactivity = 1`` then leave it as default).
- ``SUVR reference``: The reference region to calculate SUVR.
- ``Brain atlas``: The brain atlas for ROI segmentation.

**3. Outputs:**

All the outputs will be saved in ``data/subject1/OPETIA_output/ROI_analysis`` and they include:

- ``OPETIA_cortical_all_info.txt``: SUV and SUVR (mean, min, max, SD) and cerebral volume for all crotical ROIs.
- ``OPETIA_subcortical_all_info.txt``: SUV and SUVR (mean, min, max, SD) and cerebral volume for all subcortical ROIs.
- ``Cortical_images``: Cortical ROI images of PET (SUV)
- ``Cortical_normalized_images``: Cortical ROI images of PET (SUVR)
- ``Subcortical_images``: Subcortical ROI images of PET (SUV)
- ``Subcortical_normalized_images``: Subcortical ROI images of pET (SUVR)







