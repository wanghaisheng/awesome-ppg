1. The Quest for Raw Signals: A Quality Review of Publicly Available Photoplethysmography Datasets

Citation
The Quest for Raw Signals: A Quality Review of Publicly Available Photoplethysmography Datasets, Florian Wolling and Kristof Van Laerhoven. In DATA'20: Proceedings of the 3rd Workshop on Data Acquisition To Analysis, DATA 2020, Virtual Event, Japan, November 2020, ACM, 2020.

https://ubicomp.eti.uni-siegen.de/home/datasets/data20/index.html.en

https://github.com/fwolling/PPGraw



2. Measuring Heart Rate During Physical Exercise by Subspace Decomposition and Kalman Smoothing

Citation

"Measuring Heart Rate During Physical Exercise by Subspace Decomposition and Kalman Smoothing", IEEE Transaction on Instrumentation & Measurement.



https://github.com/AlessandraGalli/PPG/tree/master



3. Welltory-PPG-dataset


Dataset consists of 21 records containing PPG with simultaneously collected RR intervals. PPG data was obtained via a smartphone camera using Welltory app. Signal lengths vary from 68 to 112 seconds.

Data collection protocol
Each participant attached index finger to a smartphone camera recording video. Each frame capture time (measured in milliseconds elapsed from the measurement start time) as well as the average values of red, green and blue channel in the frame were recorded. At the same time each participant was wearing the Polar H10 chest strap. After the end of the measurement the RR-intervals detected by the Polar device during the measurement were collected. Each dataset record consists of the following arrays:

camera frame capture times in milliseconds
values of the red, green, and blue channel in the camera frames
sequence of RR intervals (in milliseconds) collected from the Polar device during the measurement
Participants
Data was collected from 13 healthy volunteers of age 25-35. Each participant made 1 or 2 measurements using their own Android smartphone.

Data description
There are 21 recordings stored in folders "subject_01", .., "subject_21" Each folder "subject_.." contains:

PPG.csv: 3 channel PPG signal containing camera frame capture time and values of red, green and blue channels in the frame.

RR.txt: a text file containing RR intervals obtained by Polar device during the PPG measurements.

Citation


Neshitov, A.; Tyapochkin, K.; Smorodnikova, E.; Pravdin, P. Wavelet Analysis and Self-Similarity of Photoplethysmography Signals for HRV Estimation and Quality Assessment. Sensors 2021, 21, 6798. https://doi.org/10.3390/s21206798




https://github.com/Welltory/welltory-ppg-dataset/tree/master


4. CIME-PPG-dataset-2018


Citation

CIME PPG dataset described in "Ke Xu et al., 'Photoplethysmography Motion Artifacts Removal based on Signal-Noise Interaction Modeling Utilizing Envelope Filtering and Time-Delay Neural Network,' IEEE Sensors Journal, vol. 20, no. 7, pp. 3732-3744, Apr. 2020. https://doi.org/10.1109/JSEN.2019.2960370" (training set) and in "Ke Xu et al., 'Deep Recurrent Neural Network for Extracting Pulse Rate Variability from Photoplethysmography During Strenuous Physical Exercise,' 2019 IEEE Biomedical Circuits and Systems Conference (BioCAS), Nara, Japan, 2019, pp. 1-4. https://doi.org/10.1109/BIOCAS.2019.8918711" (testing set).


Since the data size is beyond the maximum size required by github, please go to the following Dropbox link for data files: https://www.dropbox.com/sh/6np4q7dg9iz46ki/AACZd58eD8iVVOHIR-9vEUbRa?dl=0





https://github.com/WillionXU/CIME-PPG-dataset-2018/tree/master

5. NR2/UFPR PPG Datasets



Suggested Citation If you use this dataset in a publication, please credit the author(s) using the following citation:

Fernando Nakayama, Paulo Lenz, Stella Banou, Michele Nogueira, Aldri Santos, and Kaushik R. Chowdhury, “A Continuous User Authentication System Based on Galvanic Coupling Communication for s-Health,” Wireless Communications and Mobile Computing, vol. 2019, Article ID 9361017, 11 pages, 2019.

**Backgound:
This PPG (Photoplethysmogram) dataset was build with an experimental environment within the context of the NSF/RNP U.S.-Brazil HealthSense project. https://www.healthsenseproject.net/**

This dataset was employed to test the BEAT - (Biosignal Enhanced Authenticator) authentication system. An authentication system based on PPG Biosignals.

Sensor employed in captures - [Gravity: Heart Rate Monitor](https://wiki.dfrobot.com/Heart_Rate_Sensor_SKU__SEN0203 "Gravity: Heart Rate Monitor")

Sensor technical details are available at:[Gravity: Heart Rate Monitor - Datasheet](https://github.com/DFRobot/DFRobot_Heartrate/raw/master/Hardware/SON1303%20Datasheet.pdf)

Sensor Schematic is available at:[Gravity: Heart Rate Monitor - Schematic](https://github.com/DFRobot/DFRobot_Heartrate/raw/master/Hardware/SEN0203%20Heart%20Rate%20Sensor%20Schematic.pdf)

MCU employed in captures is - [Arduino Uno](https://www.arduino.cc/en/Guide/ArduinoUno "Arduino Uno")

Datasets encompass data from 30 healthy individuals from 23 to 53 years old and with no record of cardiac issues. Each individual had their PPG signal collected and recorded in two positions: standing and sitting. The NR2/UFPR#1 dataset contains data from the seated individuals, whereas the NR2/UFPR#2 dataset contains data from standing individuals. User registrations were made at different time as would occur in a real situation. Datasets hold three-minute sample per individual.



https://github.com/Healthsense-Project/NR2-UFPR-PPG-Dataset




6. PPG-DaLiA

PPG-DaLiA contains data from 15 subjects wearing physiological and motion sensors, providing a PPG dataset for motion compensation and heart rate estimation in Daily Life Activities.


PPG-DaLiA is a publicly available dataset for PPG-based heart rate estimation. This multimodal dataset features physiological and motion data, recorded from both a wrist- and a chest-worn device, of 15 subjects while performing a wide range of activities under close to real-life conditions. The included ECG data provides heart rate ground truth. The included PPG- and 3D-accelerometer data can be used for heart rate estimation, while compensating for motion artefacts. Details can be found in the dataset's readme-file, as well as in [1].




https://archive.ics.uci.edu/dataset/495/ppg+dalia


7. PPG-Dataset

These are PPG datasets for emotional analysis.
The target emotions of this study were joy, sadness, anger, and relaxed.
The PPG datasets were recorded from 18 participants while watching short video clips.



https://github.com/PKNU-PR-ML-Lab/PPG-Dataset

8. PPG_Dataset




https://github.com/wesengin/PPG_Dataset/tree/master


9. PPG_BP_dataset


A new, short-recorded photoplethysmogram dataset for blood pressure monitoring in China


Data Descriptor: A new, shortrecorded photoplethysmogram dataset for blood pressure monitoring in China



https://github.com/sanqiaiziji/PPG_BP_dataset/tree/master

10. others

BioSec: https://www.comm.utoronto.ca/~biometrics/PPG_Dataset/

CapnoBase PRRB: https://dataverse.scholarsportal.info/dataset.xhtml?persistentId=doi:10.5683/SP2/NLB8IT

PPG_ACC: https: https://www.sciencedirect.com/science/article/pii/S2352340919314003


GYRO_ACC_PPG: https://github.com/hooseok/gyro_acc_ppg

PulseID: J. Luque, G. Cortès, C. Segura, A. Maravilla, J. Esteban and J. Fabregat, "END-to-END Photopleth YsmographY (PPG) Based Biometric Authentication by Using Convolutional Neural Networks," 2018 26th European Signal Processing Conference (EUSIPCO), 2018, pp. 538-542, doi: 10.23919/EUSIPCO.2018.8553585.


PPG-BP: https://www.nature.com/articles/sdata201820

Vortal: https://peterhcharlton.github.io/RRest/vortal_dataset.html

BIDMC: https://www.physionet.org/content/bidmc/1.0.0/

Vortal: https://peterhcharlton.github.io/RRest/vortal_dataset.html

TROIKA: Z. Zhang, Z. Pi, B. Liu, TROIKA: A general framework for heart rate monitoring using wrist-type photoplethysmographic signals during intensive physical exercise, IEEE Transactions on Biomedical Engineering, vol. 62, no. 2, pp. 522-531, February 2015, DOI: 10.1109/TBME.2014.2359372

DEAP: https://www.eecs.qmul.ac.uk/mmv/datasets/deap/



