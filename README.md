# YOLO_customer_dataset_for_object_detection
A tutorial for train/test a YOLO v5 model for customer dataset. 
TutorialForCustomizedDatasetForYOLOv5
We need download, label approximate 26 brands of price sign images, each one at least 200 images. Example images and scripts are in this repository. 35 major brands were defined in dataset_rev_12082022.txt by excluding 4 brands: Shell, Exxon, Chevron, and Mobil. Those 4 brands dataset is fine.

Step 1. Download prices sign + brand images from Internet.
Make sure the corresponding image include brand and price sign together. Price sign image categories are defined in the file class.txt, which has 90 classes. Corresponding category can be download from Google by search: For example, for Chevron, search: Image for Chevron Gas Stations PriceSign, find the corresponding website, then download manually one by one or automatically with scripts. An example image is chevron_3.jpg file. Important -- make sure downloaded image has price sign and band together, as shown in the example.
Directory can be defined based 35 major brands were defined in dataset_rev_12082022.txt, except Brand Exxon, Shell, Chevro, Mobil which are already detected: 31 brands:

    original_Images -> 7-ELEVEN
                       ALON
                       AMOCO
                       ARCO
                       CENEX
                       ...
Step 2. Original images should be scaled with width 640 pixel and keep original image ratio. Example scripts: scaleWithWidth_v1.py Execution: python3 scaleWithWith_v1.py

    normalized_Images -> 7-ELEVEN
                       ALON
                       AMOCO
                       ARCO
                       CENEX
                       ...
Step 3. Label images with labelImg tool. Download labelImg from the website: https://github.com/HumanSignal/labelImg Install labelImg follow instructions. Run labelImg by python command, then UI interface will show up. Important -- since we use our own customized dataset for 90 brands + price signs, in setup it is required to change/update labelImg default class file: labelImage/data/predefined_classes.txt with the class file defined in class.txt. In UI interface of labelImg, select format YOLO format. Important -- in labelling process, make sure bounding box contains brand and price sign together. An example image is ScreenshotForLabelChevron.png.

    label -> 7-ELEVEN
                ALON
                AMOCO
                ARCO
                CENEX

