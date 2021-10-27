# MRI--Semi-supervised-3D-Segmentation
In this project, we present a deep learning framework for hamstring Muscles Segmentation using
Magnetic Resonance Images (MRI) scans coming from Elite and Normal participants. Our goal is to
quantify the volume of each sub-structure of the hamstring muscles as a mean to support monitoring
of athletes conditions, such as detecting injuries and their performance level.
To meet our goal, we follow recent state of the art methods in the medical imaging domain. In particular,
our method is based on recent work published by SIMS team, the Interactive Few-Shot Siamese Network
(IFSS-Net) [1] at LS2N, ECN, where my internship took place. However, IFSS-Net model is applied on
low-limb muscle using images coming from Ultrasound (US) machine.
In this project, our role is to adapt the IFSS-net from US to MR modality and to introduce uncertainty
measure to the model. The uncertainty measure will be a tool to show the medical expert where the
segmentation performed by the IFSS-net was not certain and thus giving an opportunity for the expert
to correct or confirm the segmentation performance.
Since IFSS-net is a method that is built using advanced deep learning methods, in this thesis: I had
to study the required background, review state of the art, study in details the IFSS-net model and to
introduce the uncertainty measure. Apart from this, data manipulation and understanding is among the
most important part to make sure the success of the IFSS-net model and adaption. Hence, we developed
a pre-processing that crop and normalize the MR volumes, separate the left and the right legs from each
scan and validate if the ground truth segmentation of each participant was correct.
We validate our baseline framework over the 4 targeted muscles, we obtained a Dice Coefficient Score
(DSC) value around 66%. The semi-supervised framework was validate just over the femoris muscles
due to time constraints and achieved 68% as DSC, while the fully supervised IFSS-Net showed more
accurate results with DSC around 73%.
Key Words: Python, Medical Image Processing, Computer Vision, Segmentation, Semi-supervised
Learning, Bayesian Uncertainty, Monte Carlo Dropout, Siamese Networks.
