### Design and Implementation of an Intelligent Travel Aid for The Visually Impaired (ITA-VI)
*Proposal by: Samuelson T. Atiba and Sarah F. Moses*


#### Summary
The visually impaired have little or no effective visual sensory input and have to rely on external assistance for navigation. Several electronic travel aids were developed to aid independent navigation of the visually impaired though these travel aids either offered some level of obstacle recognition or terrain analysis but not both. However, dangerous terrain features pose serious risks of hazard.

 This paper proposes the design and implementation of an Intelligent Travel Aid that combines the detection and recognition of objects with the analysis of terrain features for real-time identification of features that may pose a risk of hazard to visually impaired users.
 
This system will leverage artificial intelligence technologies. Machine vision will be used for object recognition and terrain feature detection. Two cameras for capturing object and terrain images respectively, a haptic device and a speaker connected to a Raspberry Pi development board form the core of the system. The system will notify users of obstacles and terrain features via haptic feedback and synthesized speech.

To visualize the terrain data and obstacle position in space during initial analysis and model fitting, cMapIT.io studio software will be employed. For real-time analysis of the surrounding environment, OpenCV will be used in conjunction with a Convolutional Neural Network running on an auxiliary Vision Processing Unit connected to the Raspberry Pi.

The completion of this research work will help shape the future of assistive technologies to facilitate the independent navigation of visually impaired individuals. Further, the completed research work will result in the creation of an open image dataset relevant to the African context and so further inclusion in the development of artificial intelligence.

#### Introduction
According to the World Health Organization (2018), an estimated 1.3 billion people live with some form of distance or near visual impairment, 36 million of whom are blind. For these people, seemingly simple tasks like driving, walking, reading and interacting with others could be extremely difficult. Navigation is especially tedious because it requires the ability to perceive distance, terrain and obstacles. It also requires the individual to analyze these to deduce necessary reactions and carry them out. 

Visual impairment or low vision is a severe reduction in vision that cannot be corrected with standard glasses or contact lenses. It reduces a person's ability to function at certain or all tasks. Legal blindness, a severe visual impairment, refers to a best-corrected central vision of 20/200 or worse in the better eye or a visual acuity of better than 20/200 but with a visual field no greater than 20° (i.e., side vision that is so reduced that it appears as if the person is looking through a tunnel). People classified as living with visual impairment typically have less than 20/100 vision i.e., the inability to see clearly from a distance of 20 feet what the normal eye can see clearly from 100 feet – at the best, they are unable to distinctly see far-off objects while retaining some visual perception of light and objects that are very close by and at the worst, they have no perception of light. (Gale Encyclopaedia of Medicine, 2008).

The visually impaired are unable to detect objects which may constitute obstacles from a distance because of their limited visual abilities. Since the visually impaired are unable to detect these objects, it is impossible for them to recognize such as may pose risks of hazard.

##### Problem Statement
In humans, vision is essential and always actively engaged during the navigation of the environment. The ability to gather and process visual input plays a core role in the human ability to get from one location to another successfully and efficiently. Successful navigation is being able to get from one location to a proposed location while efficiency ensures this is done in an optimum period of time and with no more energy than should normally be required. However, the visually impaired do not possess the ability to gather adequate and accurate visual information. Hence, successful and efficient navigation is not possible for the unaided visually impaired individual.

One of the earliest solutions to the problem of navigation for the visually impaired was a sighted assistant. The sighted assistant would often lead the visually impaired person by the hand. With time, this solution proved inefficient: not only did the visually impaired person and the sighted assistant have to continually adjust their schedule to avoid conflicts of engagements but issues also arose when the sighted person had to travel, was sick or had a commitment that made them unavailable. This left the visually impaired individual vulnerable and greatly dependent as the ability to move around was completely reliant on someone else’s willingness and ability to help.

To provide a solution to help the visually impaired completely achieve complete independence, the white cane was introduced. The white cane, although being in existence for so long with wide-spread use, had its own limitations. Some of these limitations included a limited range – it could only detect obstacles up to knee-level within a range of only two to three feet. Further, it could not detect overhead or overhanging obstacles and there existed a possibility of the cane cracking or breaking when subjected to extreme pressure. Also, there was a lack of fluidity as it could get stuck in cracks and holes.

The guide dog was also another option for the visually impaired. However, training was required for the new dog; proper care had to be provided and this was not only time consuming but also strenuous for a visually impaired individual. Further, a guide dog meant more expenses in terms of feeding, care and medical fees.

The failure of these three to proffer solutions to ease mobility and navigation led to the first generation of electronic travel aids (ETAs, also called mobility or navigation aids). These included the Russell Path-Sounder (Russell, L., 1966) – a chest-worn device that used ultrasonic energy to detect obstacles within about six feet and beeped or vibrated to alert the user, the Laser Cane (Benjamin, J. M., 1973) – a regular white cane with a built-in laser ranging system and the Mowat Sensor (Pressey, N., 1972) – a pocket sized device containing an ultrasonic air sonar system that used vibrations to signal the user when it detects an obstacle. This first generation of mobility aids were criticized on grounds of cost-effectiveness and the masking of natural echo and location cues since most of them required the user to use some form of headphone.

Many other researches have been carried out and many projects undertaken in the development of travel aids for the visually impaired. Ultrasonic sensors, infrared sensors, lasers and cameras have been employed as sensing devices in the construction of these electronic travel aids. Some other developed travel aids include vOICe (Meijer, P. B., 1992), Tyflos (Bourbakis, Keefer, Dakopoulos and Esposito, 2008) and more recently JUVO (Gianani, Mehta, Motwani and Shende, 2018). However, of these class of devices, none combines effective terrain navigation with obstacle detection and recognition seamlessly.

##### Aim
The aim of the project is to design and implement an Intelligent Travel Aid for the Visually Impaired (ITA-VI) to provide a means of independent navigation for the visually impaired.

##### Objectives
1.	To achieve real-time recognition and notification of obstacles, objects and points of interests in the implementation of the ITA-VI.
2.	To achieve real-time analysis of terrain data and real-time notification of dangerous terrain features in the implementation of the ITA-VI.
3.	To achieve approximate distance and spatial orientation of detected environmental features.

##### Scope of the Project
While there are many objects to consider and many different types of obstacles and dangerous terrain features, the scope of this research is limited to the recognition of obstacles, accessibility aids, points of interest and terrain features as are laid out in Appendix One.

The research will be carried out with area around the Faculty of Engineering and Technology, Ladoke Akintola University of Technology, Ogbomoso, Oyo State, Nigeria as a test location. The area has an appropriate mix of objects, points of interests and terrain features as are relevant to the research project.
 
#### Methodology
The Intelligent Travel Aid for the Visually Impaired (ITA-VI) is decomposed into functional modules that will perform interrelated tasks. The functional modules are:
1.	Object Recognition Module
2.	Terrain Analysis Module
3.	Range Finding and Spatial Orientation Module
4.	Extraneous Data Suppression Module
5.	Haptic Feedback Module 
6.	Digital Voice Instruction Module

The Extraneous Data Suppression, Haptic Feedback and Digital Voice Instruction Modules combine to form the Artificial Intelligent Navigation Assistant (AINA) – a smart decision making subsystem that provides haptic feedback and voice instructions to the ITA-VI user.

##### Object Recognition Module (ORM)
This module is concerned with the recognition of a predetermined set of above ground obstacles including walls, cars, trees etc., accessibility aids including doors, corridors, stairs etc. and points of interest such as parasols, storefronts and motor parks. It is the first processing block responsible for the detection and recognition of all predetermined objects.

This module will comprise an input camera sensor, a vision processing unit (VPU) and a trained Convolutional Neural Network (CNN) for performing real-time object recognition on images. The CNN model will run on the VPU core to achieve a high frame rate i.e. number of images processed per second – this is to enable real-time performance. The CNN model will be trained on local image datasets of predetermined objects and places to improve recognition accuracy of the module. The image captured by the camera is passed to the CNN for processing and the CNN detects and recognizes objects within the picture. The recognized objects in the image input will have a bounding box and a label specifying the class of object overlaid on each object recognized in the image. The image with the bounding boxes and labels of the recognized objects form the image output of this module. The processed image output will be passed on to the Range Finding and Spatial Orientation Module for further processing.

##### Terrain Analysis Module (TAM)
The terrain analysis module will carry out analysis of the terrain of the user’s pathways. This module analyzes the terrain for presence of features such as pits, open gutters, gutter gratings, stairs and drop-offs.

The terrain analysis module will be made up of a camera sensor as input, a VPU core and a CNN to perform the terrain feature recognition. The dedicated VPU is to facilitate real-time operation of the module. The module will work by passing an input image of the ground in front of the user to the CNN. The CNN processes the image to recognize potentially hazardous terrain features. The output of the terrain analysis module is an image overlaid with a bounding box and a label describing the class of feature recognized. This output image will also be passed to the Range Finding and Spatial Orientation Module for further processing of the image.

##### Range Finding and Spatial Orientation Module (RFSO)
This module performs range finding and determines the spatial orientation of detected objects i.e. distance estimation and determines spatial orientation of recognized images and terrain features using the bounding box as the primary input. Using the bounding box on the input image, this module will decipher the approximate distance and direction of the recognized object/feature enclosed within the box. This module generates an image output with distance and orientation appended to the label on each image.
Then, the fully annotated image output is passed to the next stage of processing so it can be transformed into a form that will be easily understood by the user.

##### Extraneous Data Suppression Module (EDS)
The input to this module is the fully annotated image of the terrain or objects. However, this data will contain a lot of pixel information which are not relevant to the decisions of the Artificial Intelligent Navigation Assistant subsystem (AINA). Hence, the extraneous data suppression module suppresses these extraneous pixel information and will extract only the data such as are useful to the AINA subsystem.

The EDS module will extract the data values corresponding to the classes of objects/terrain features detected and estimated distance and spatial orientation data about each detected object/feature. Using these data, the EDS module will compute severity levels using the detected object/feature classes and the proximity of the detection. The output data of the EDS will be communicated to the user through the Haptic Feedback Module (HFM) and the Digital Voice Imperative Module (DVI).

##### Haptic Feedback Module (HFM)
The Haptic Feedback Module receives the processed data from the EDS and alerts the user of impending obstacles and terrain features that pose a risk of hazard. The HFM controls a set of two haptic feedback units consisting of a loaded motor which vibrates when energized. The HFM is able to communicate different types of objects/features detected as well as their proximity/severity by varying the duration and repetition of the energizing pulses sent to the units.

##### Digital Voice Instruction Module (DVI)
This module provides audio feedback to help the user navigate the surrounding environment. The digital voice is synthesized by the DVI module based on the information it receives from the EDS module. The DVI module gives its feedback as imperative statements to the user to ensure that the delay between the digital sensory input and the corresponding user reaction is reduced to the minimum. Further, the DVI will be a smart module which will perform the role of a smart personal guide. It will describe recognized object features to the user and give a computed best course of action as an imperative when needed. The DVI will also announce nearby points of interest to the user when there are no imminent risks.

##### System Design
The ITA-VI system will be designed around a Raspberry Pi 3 B+ development board with Movidius Neural Compute Sticks (NCS) and the Google Coral Accelerator. The Raspberry Pi board includes an ARM System on Chip (SoC) with a 64-bit, 1.4-GHz quad-core CPU and 1-GB RAM. The SoC also features multithreading support which makes the board suitable for running multiple computations in parallel. While multithreading is an added advantage, the CPU is not especially tuned for running the Deep Neural Network (DNN) hence, the CPU delegates the specialized task of running the network to the Movidius NCS/Coral Accelerator. The NCS consists of highly specialized vision processing units (VPU) for accelerating neural networks by running parts of the Neural Network in parallel.

This System design enables the Object Recognition Module and the Terrain Analysis Module Neural Networks to run in parallel to achieve real-time performance. Further, the multithreading capability also enables both the Haptic Feedback Module and the Digital Voice Instruction Module of the Artificial Intelligent Navigation Assistant Subsystem to work fully independently of each other at the same time. This will also enhance the user experience since feedback will be timely and without latency.

#### Impact of the Work
Globally, there are no Electronic Travel Aids developed that offer object recognition and obstacle detection in addition to terrain analysis to alert the user of uneven terrain that represent a risk of hazard. This research presents the design and implementation of an Intelligent Travel Aid for the Visually Impaired (ITA-VI) to provide recognition of obstacles and objects and also provide an awareness of uneven terrain to facilitate independent navigation of the visually impaired.

This research will enable the visually impaired to lead a better life with benefits including but not limited to: reduced mortality rates due to fall and other impairment related accidents, access to new opportunities for work, travel and recreation and an increased sense of self-worth.

#### Contribution to Knowledge
The execution of this research work will lead to the creation of an open repository of African terrain images dataset, a first of its kind globally. The creation of such image repository will lead to increased interests in further research into rapidly progressing fields of artificial intelligence since interests in this area have been hitherto stifled by the absence of datasets to work with.
 
#### Budget
An estimate of some of the required resources for the research work is outlined below:

*Table 2.1 Estimate of Required Resources for the Research Work*

| Item | Unit Cost | Quantity	| Total - ₦360 ($1) |
| :--- | ---: | ---: | ---: |
| Raspberry Pi 3 B+ Board |	₦28,796.4 ($79.99) |	2 pcs |	₦57,592.8 ($159.98) |
| Raspberry Pi Camera Module	| ₦10,389.6 ($28.86) |	2 pcs |	₦20,779.2 ($57.72) |
| Coral USB Accelerator | ₦44,982.0 ($124.95) | 1 stick | ₦44,982.0 ($124.95) |
| Movidius Neural Compute Stick | ₦27,705.6  ($76.96)	| 2 sticks | ₦55,411.2 ($153.92) |
| **Spec. Subtotal** |  |  |	**₦178,765.2 ($496.57)** |
| USB Camera |	₦15,480 ($43) |	2 pcs |	₦30,960.00 ($86.00) |
| Bone Conduction glasses |	₦35,319.50 ($98.11) |	2 pcs |	₦70,639.20 ($196.22) |
| Haptic Feedback Units |	₦336.00 ($0.93) |	10 pcs |	₦3,348.00 ($9.30) |
| Soldering Kit |	₦11,769.97 ($32.69) |	1 pc |	₦11,768.40 ($32.69) |
| Anti-Static Wristbands and Gloves |	₦3,069.00 ($8.53) |	2 pcs |	₦6,141.60 ($17.06) |
| Battery Pack |	₦7,060.00 ($19.61) |	2 pcs |	₦14,119.20 ($39.22) |
| **Com. Subtotal**	| | | **₦136,976.4 ($380.49)** |
| *Shipping costs (incl. Import Duties and Taxes)* | | |	*₦101,152.8 ($280.98)* |
| Google Cloud for A.I.	| ₦387.72 ($1.077)/hr |	380 hrs |	₦147,333.60 ($409.26) |
| **Grand Total** | | |	**₦564,228.00 ($1,567.30)** |

#### Conclusion
To increase confidence and independence for the visually impaired in navigating and exploring familiar and new environments, development of travel and navigation aids that remove the need for dependence on human/animal guides is very important.

The design and implementation of the Intelligent Travel Aid for the Visually Impaired (ITA-VI) will further research into the area of developing working solutions to aid navigation for the visually impaired. This project will expand the Body of Knowledge and provide proven alternative methods to implementing navigation assistants for the visually impaired in a bid to facilitate accessibility. This will also facilitate development of a world where the visually impaired can easily navigate their surrounding environment without the need for a/an human/animal navigation guide.

#### Appendix
The predetermined Objects set comprised of obstacles, accessibility aids and places of interest are listed below:

1.	Obstacles
    -	Walls
    -	Hand Rails
    -	Trees
    -	Flower Bushes
  
2.	Accessibility Aids
    -	Doors (Open/Closed)
    -	Stairs
  
3.	Points of Interest
    -	Seat Spots
    -	Stalls

4.	Terrain Features
    -	Ditches and Holes
    -	Open Gutters
    -	Gutter Gratings
    -	Drop Offs
    
#### Get in Touch
Send us an email [here][1] or [here][2].

We'll make sure to get back in touch.

[1]: mailto://statiba@student.lautech.edu.ng
[2]: mailto://samuelsontijesunimi@gmail.com

#### References
Gale, T. (2006). Visual Impairment. In Gale Encyclopedia of Medicine, (3rd ed.). Retrieved May 14, 2019 from Encyclopedia.com:https://www.encyclopedia.com/medicine/encyclopedias-almanacs-transcripts-and-maps/visual-impairment

Bourbakis, N., Keefer, R., Dakopoulos, D. and Esposito, A. (2008). A Multimodal Interaction Scheme between a Blind User and the Tyflos Assistive Prototype. 20th IEEE International Conference on Tools with Artificial Intelligence, 487-494.

Gianani, S., Mehta, A., Motwani, T., and Shende, R. (2018). JUVO - An Aid for the Visually Impaired. International Conference on Smart City and Emerging Technology, 1-4.

Meijer, P. B. (1992). An experimental system for auditory image representations. IEEE Transactions on Biomedical Engineering, 39, 112–121.

Pressey, N. (1977). Mowat Sensor. Focus, 11(3), 35-39.

Russell, L. (1966). Travel Pathsounder and evaluation, In R. Dutton (Ed.), Procs. Conference on the Evaluation of Sensory Devices for the Blind, 293-297. St. Dunstan’s, London.

World Health Organization (2018). Blindness and Visual Impairment Retrieved 05-14-2019 from http://www.who.int/en/news-room/fact-sheets/detail/blindness-and-visual-impairment
