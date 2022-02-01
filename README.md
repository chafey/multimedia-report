# multimedia-report
Project for building multi-media reports for medical imaging

# Goals

* High level
  * Better information patient
  * Better information for physicians
  * Improve workflow for radiologist (follow-up / priors - better than hanging protocols)
    * Must reduce cognitive overload for radiologists (e.g. useless recons)
    * Must have little to no impact on radiologist report creation
    * Reporting can be slowed down due to context changes
  
* Low level
  * Free report from being a text blob 
  * Need to make reports more structured - still widely adopted (most reports are prose)
  * "Contextual Reporting" - take disease states and create an entire template around it 

# Notes
  * Difference between templated reports and storing reports in DICOM SR
  * IHE discussions from a few weeks ago
    * Need to be able to toggle off annotations/measurements/overlays, etc so underlying/raw image can be viewed 
  * vRAD has a very good report authoring system

# Requirements

* Ability to display images
    * Formats
        * Medical Images
            * DICOM
            * Non DICOM
            * 3D/4D Volumes
        * Web friendly images
            * JPEG
            * PNG
    * Interactivity
        * Static (image does not change)
        * Dynamic (e.g. window/level, zoom, scroll)
        * Cine (XA, US)
        * MPR/Slab
        * Volume Rendering
* Ability to display report text
  * Unstructured
  * Structured
    * Hyperlinks which update the display when clicked (e.g. shows a specific finding on an image)
    * Tooltips which provide more info (e.g. mouse over without click displays a tooltip window with hyperlink, text or image)
        * Text
        * Hyperlink
        * Image
* Hyperlinks
  * Image display (dedicated viewport that respods to redirects from interaction with report)
    * Key Images
      * Specific instanceUID in context of parent series
      * Specific frame within mulitframe image
      * Time point in a video (+/- scope)
    * Presentation States
      * image with specific W/L
      * arrow, circle or other graphics primative defined in PS
      * DICOM Planar MPR Volumetric Presentation State (Bookmark of custom MPR)
    * Structured Report Object
      * Segmentation
      * Parametric map
  * External Resources
    * Ability to display contact information (e.g. for DM, voice or video)
      * Reporting physician
      * Primary care physican
      * Other related staff?
    * Links to journal articles
    * Links to internal information
* Configurable Layouts (e.g. 2x1, 4x4)
  * Width/Height
    * Fixed Size
    * Percentage Based
* Targeted Departments
  * Radiology
  * Cardiology
  * Pathology
  * Dermatology
  * Wound Care
