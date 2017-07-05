habit horse ears still image detector training dataset 904

Developer: Dr Steve North - steve@stevenorth.com - 2017
 
This dataset was developed in 2017 for the HABIT (Horse Automated Behaviour Identification Tool) project [1] to provide training images of horses' ears in order to train a Haar Cascade to detect them.

The intention of the this dataset was to investigate 'shortcuts' to training a detector for complex, deformable target objects with high levels of intra-class shape variability... such as the horse.
By identifying 'salient features' (distinctive, minimally changing physical attributes) of the target object, it might be possible to produce a simpler, faster, more easily trained detector. 
In this case, I was investigating the use of horses' ears as a salient feature for detecting horses in images and video.
 
The process of training the detector required many examples of both ‘positive’ images (containing clear views of horses with ears) and ‘negatives’ (containing anything but horse ears).

In this case, my training dataset had a total of 904 images, of which 200 were positive and 704 were negative.

All of the images are a subset of the ‘HABIT horses still image detector training dataset 10978’[2] and retain the same image numbering. 

The developer does not claim or assert any copyright over many of the images in this dataset and it is the user’s responsibility to obtain any required licences or clearances.
 
The negative images (not showing horses' ears) are: grayscale, 100x100 pixels, JPG format in the directory: \neg\
 
The positive images (showing the ears of many horse breeds, ages, genders, viewpoints, scales, occluded, multiple instances of target object etc.) are: grayscale, 100x100 pixels, BMP format in the directory: \pos\rawdata\
 
The text file bg.txt contains a list of the negative images, with the relative paths to their location.
 
The text file \pos\info.txt lists each of the positive images (including the relative paths to their location) has an entry, with annotations detailing the coordinates of an ROI (Region of Interest) / bounding box, outlining the horse(s) in the scene.

This is for use when training a Haar Cascade detector, or similar.
 
Example entries from info.txt:
rawdata\image1200.bmp 1 34 12 74 24
rawdata\image1201.bmp 3 35 25 70 39 40 95 80 92 120 40 45 36
rawdata\image1202.bmp 2 10 24 90 90 45 68 99 82
The first number in each line defines the number of target objects (horses' ears) in the given image. For example, in the second line, the number 3 indicates that three separate bounding boxes for target objects (horses' ears) have been manually drawn for image1201.bmp. The next four numbers define the location of the first target object (horses' ears #1) in the image (top left of the drawn bounding box: x=35, y=24 , width=70 and height=39). If the first number in each line is greater than 1, then for each increment of +1, a corresponding set of four values (x, y, w & h) will appear, representing each bounding box (set of horses' ears) in the scene. So, for image1201.bmp there are two further sets of horses's ears enclosed by a bounding box: horses' ears #2 (x=40, y=95 , w=80 and h=92) and horses' ears #3 (x=120, y=40, w=45 and h=36).
 
Note: it would have been more straightforward to use the JPG format for both positive and negative images, but objectmarker.exe [3] - BUT the tool used for manually drawing the ROIs (Regions Of Interest) / bounding boxes around horses in positive images - only works with the BMP format. Therefore, positive images in 10978 [2] were converted to BMPs, whereas the negative images remained in JPG.

IMPORTANT: the ROIs manually drawn for the positive images in this data set (904) are not the same as for the original images (with the same numbering) in the ‘HABIT horses still image detector training dataset 10978’[2]. This is because 10978 ROIs are the entire horse and this dataset (904) is focused on horses' ears. As such, the bounding boxes have been redrawn using objectmarker.exe [3] and are around the ears (usually as a pair).

###########################################################################################################################

A little bit about how the images in 10978 [2] were originally derived...

10978 contains a total of 10,978 images, consisting of:
 
6183 x positive images of horses (many horse breeds, ages, genders, viewpoints, scales, occluded, multiple instances of target object etc.): grayscale, 100x100 pixels, BMP format.
 
The positive images were sourced from various places, including: the developer’s own images, Google Image searches, ImageNet [4] and the Weizmann Horse Databases [5][6][7].
 
4795 x negative images (not showing horses): grayscale, 100x100 pixels, JPG format.
 
The negative images were sourced using a Python script (download_neg_image_by_link.py, written by the developer) to bulk download targeted image synsets (for example: ‘athletics’, ‘raw vegetables’, ‘people’, ‘cars’, ‘devices’ etc.) from ImageNet [2].
 
The Python script also automatically resized each image to 100x100 pixels, converted it to grayscale, changed the format to BMP (if necessary) and renamed each one, with a sequential number. 

#############################################################################################################################
 
[1] Steve North, Carol Hall, Amanda Roshier, and Clara Mancini, 2015. HABIT: Horse Automated Behaviour Identification Tool – A Position Paper. In Proceedings of the proceedings of ACI@BHCI (Animal Computer Interaction Workshop), British HCI 2015 (Lincoln, UK, 13 July 2015), BCS, UK.  http://dx.doi.org/10.13140/RG.2.1.3395.0881.

[2] Steve North, 2017. HABIT horses still image detector training dataset 10978. v2.0. http://dx.doi.org/10.5281/zenodo.822849.

[3] Mahdi Rezaei. 2016. Software Program: objectmarker.exe - utility for manually drawing regions of interest. Available from: https://www.cs.auckland.ac.nz/~m.rezaei/Tutorials/Haar-Training.zip.
 
[4] Kai Li Li Fei-Fei, Olga Russakovsky, Jonathan Krause, Jia Deng, Alex Berg. ImageNet: an image dataset. 2017. Retrieved from: http://image-net.org/.

[5] E. Borenstein and S. Ullman, 2002. The Weizmann Horse Database.

[6] Jamie Shotton, 2007. Multiscale Weizmann Horse Detection Dataset.

[7] Jamie Shotton, 2007. Single-scale Weizmann Horse Detection Dataset.
 
