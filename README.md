# Deep Learning-based Thigh-limb Muscle Segmentation for Reproducible Volume Quantification
In this project, we present a deep learning framework for hamstring Muscles Segmentation using
Magnetic Resonance Images (MRI) scans coming from Elite and Normal participants. Our goal is to
quantify the volume of each sub-structure of the hamstring muscles as a mean to support monitoring
of athletes conditions, such as detecting injuries and their performance level.

![Screenshot from 2021-10-27 21-25-23](https://user-images.githubusercontent.com/53334878/139141826-f48b9047-632b-4e0b-b8f7-55582fe1381a.png) ![Screenshot from 2021-10-27 21-50-23](https://user-images.githubusercontent.com/53334878/139144937-808e50db-d709-4f33-82f9-a9209a306a0c.png)

Our method is based on recent work published by SIMS team, the Interactive Few-Shot Siamese Network
(IFSS-Net) (Dawood et al., [2020](https://arxiv.org/pdf/2011.13246.pdf)).
 at LS2N, ECN, where my internship took place. However, IFSS-Net model is applied on
low-limb muscle using images coming from Ultrasound (US) machine.
In this project, our role is to adapt the IFSS-net from US to MR modality and to introduce uncertainty
measure to the model. The uncertainty measure will be a tool to show the medical expert where the
segmentation performed by the IFSS-net was not certain and thus giving an opportunity for the expert
to correct or confirm the segmentation performance.

![Screenshot from 2021-10-27 21-26-00](https://user-images.githubusercontent.com/53334878/139141851-6be280d4-516d-4549-a6aa-4792d837be98.png)

After model training and during the test time we activate Dropout provability around 0.1 and 0.2, here a prediction is done for x times, so at each forward pass through the trained neural network a Monte Carlo sample from the posterior distribution is generated. Then we compute the average prediction to have the final map and we apply the standard deviation (STD) over the x generated maps to measure the spread of the distribution and obtain the uncertainty information.

![Screenshot from 2021-10-27 21-47-00](https://user-images.githubusercontent.com/53334878/139144568-91f8d20b-6245-4f53-81f9-9d92488cabe1.png)

We developed a pre-processing that crop and normalize the MR volumes, separate the left and the right legs from each
scan and validate if the ground truth segmentation of each participant was correct.
We validate our baseline framework over the 4 targeted muscles, we obtained a Dice Coefficient Score
(DSC) value around 66%. The semi-supervised framework was validate just over the femoris muscles
due to time constraints and achieved 68% as DSC, while the fully supervised IFSS-Net showed more
accurate results with DSC around 73%.
Key Words: Python, Medical Image Processing, Computer Vision, Segmentation, Semi-supervised
Learning, Bayesian Uncertainty, Monte Carlo Dropout, Siamese Networks.
