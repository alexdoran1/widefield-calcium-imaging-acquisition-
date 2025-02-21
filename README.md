# widefield calcium imaging acquisition

Github documentation – Synchronized Multi-Cam Image Acquisition with Teledyne FLIR camera and Python

Summary: This is python code for synchronized image collection for widefield calcium imaging using one Teledyne Prime BSI Scientific CMOS camera and one FLIR Flea3 USB3 camera. This code can be adapted to acquire using two FLIR Flea3 USB3s, available upon request (ard2218@columbia.edu). 

Hardware:  Teledyne Prime BSI Scientific CMOS camera, FLIR Flea3 USB3, Thorlabs blue LED, additional Thorlabs LEDs (we used UV LED) to collect calcium and non-calcium signals, respectively.

Software/platforms used: 
A.	Image J (Micro-Manager 2.0.0) to configure Prime BSI (set ROI, exposure time/FPS, binning) and number of frames to collect using Multi-Dimensional Acquisition. 
B.	SpinView (3.1.0.79) to configure FLIR Flea3 USB3. We matched FPS in SpinView to calculated FPS in Micro-Manager. 
C.	Windows Powershell or other terminal. One tip is to set priority of Micro-Manager to “high priority” in Windows task manager to eliminate frame skipping during acquisition (but note, effectiveness of this strategy may vary based on computer specs). Micro-Manager may be listed as Java(™) Platform SE binary (4) or javaw.exe in Windows task manager.
D.	A local python environment with the python packages: pyspin 1.1.1, numpy 1.21.6, matplotlib 3.7.2, pycromanager 34.6 and pyserial 3.5. 
E.	We use Google Colab for integrated team code access, connecting to the local runtime via jupyter lab for each acquisition so that the operations are run on our local machine not on Google’s servers. 

Important note: this code includes interaction with a custom-built circuit board designed to control sensory stimulation (e.g. auditory tones) and collect treadmill data. Each line of the code that communicates with the custom serial board is specifically annotated as such. Although your serial board commands will probably be different than ours, the order of the commands presented serve as an example. 

