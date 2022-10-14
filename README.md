# PhantomViewer
Analysis package written in Python to analyze MRI phantoms developed by NIST and collaborators at NCI, RSNA, NIBIB

General workflow:
    1. Open image set, DICOM, TIF.   
        The program will guess at the type of analyis that is desired by file names and parmaeters varied in the header info 
    2. Select phantom type, not the calibration data set being used.
     
PhantomViewer: Main class to display and analyze phantom data, mostly MRI data, although also used to analyze CT data on phantoms

Modules required (can be installed using 'pip install package' or  'pip install package --upgrade':
verify module version using "pip show module"

**Required Modules**

   Anaconda 3 with Python 3.7    (64 bit, Python, PyQT5, Numpy, Scipy, Pillow )
   
   pydicom Version: 1.4.2:       (for DICOM file import/export)
   
   pyqtgraph Version: 0.10.0     (for plotting and image windows)
   
   lmfit Version: 1.0.0          (for nonlinear least squares fitting routines)
   
 **Optional Modules**
   unwrap Version: 0.1.1        (for phase unwrapping)
   
   scikit-image  Version: 0.11.3: uses unwrap_phase from skimage.resoration
   
   PyOpenGL                      (Used for 3D rendering of images and data)
   



The main Gui is PhantomViewerGui5.py created from PhantomViewer.ui by Qt Designer

  You can convert ui file to python by executing (this is not necessary unless you are modifying the GUI):
  
      "designer\pyuic4 designer\PhantomViewerGui.ui -o PhantomViewerpy\PhantomViewerGui4.py"
      
  or  "designer\pyuic5 designer\PhantomViewerGui.ui -o PhantomViewerpy\PhantomViewerGui5.py"
  
  from system shell to regenerate PhantomViewerGui.py from PhantomViewerGui.ui
  
@author: Stephen Russek

Units: times in ms, distances in mm, ADC in mm2/s, Temperature in C,

VPhantom: class to describe phantoms, several virtual phantoms, including the NIST/ISMRM system phantom are available.
PV structure is shown below:

![PV Structure](https://github.com/StephenRussek/PhantomViewerNew/blob/master/icons/PVstructure.jpg)
