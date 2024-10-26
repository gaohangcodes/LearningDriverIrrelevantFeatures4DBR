# LearningDriverIrrelevantFeatures4DBR

The repository for our paper "[Learning Driver-Irrelevant Features for Generalizable Driver Behavior Recognition](https://ieeexplore.ieee.org/abstract/document/10530508)".

# Overview

There are two notebooks in training codes, each corresponding to the training and evaluation processes of MobileNetV2+FD on the StateFarm and AUC V2 datasets, respectively.

# Dataset Preparation

Since the original AUC V2 dataset did not provide driver IDs, I manually annotated the driver IDs. The file datasets/driver_IDs.csv contains the mapping of the original data to the driver IDs. Please note the following important points:

(1) In the original AUC V2 dataset, images 322.jpg to 415.jpg in the path "auc.distracted.driver.dataset_v2\v2_cam1_cam2_split_by_driver\Camera 1\test\c0" actually correspond to a driver who appears in the training set paths "auc.distracted.driver.dataset_v2\v2_cam1_cam2_split_by_driver\Camera 1\train\c1" to "...\c9". Therefore, this driver should belong to the training set. In the annotated dataset with IDs, I have corrected this minor issue. However, for fair comparison, in our paper, I still classified images 322.jpg to 415.jpg in the test set and ensured they did not appear in the training set (this can be verified in the public code).

(2) The driver IDs in the train and test folders under "Camera 1" and "Camera 2" are independently numbered. In other words, the ID001 in "Camera 1\train", "Camera 1\test", "Camera 2\train", and "Camera 2\test" corresponds to different drivers.

You can access the driver_IDs.csv file using the following code:
```
import pandas as pd
csv_file_path = 'driver_IDs.csv'
df = pd.read_csv(csv_file_path, encoding='utf-8')
```

The publication of the driver IDs has been approved by Dr. Hesham Eraqi, who was a key member in the collection and release of the AUC V2 dataset. Please note the following: 

(1) You should sign the license agreement (https://heshameraqi.github.io/distraction_detection ) to obtain and use the AUC V2 dataset.

(2) You should cite Dr. Hesham Eraqi's relevant work on the AUC dataset: 

[1] H. Eraqi, Y. Abouelnaga, M. Saad, M. Moustafa, "Driver Distraction Identification with an Ensemble of Convolutional Neural Networks," Journal of Advanced Transportation, Machine Learning in Transportation (MLT) Issue, 2019. 

[2] Y. Abouelnaga, H. Eraqi, and M. Moustafa. "Real-time Distracted Driver Posture Classification." Neural Information Processing Systems (NIPS 2018), Workshop on Machine Learning for Intelligent Transportation Systems, Dec. 2018. https://arxiv.org/abs/1706.09498

We also look forward to your citation of our work: 

[3] Gao, Hang, Mengting Hu, and Yi Liu. "Learning Driver-Irrelevant Features for Generalizable Driver Behavior Recognition." IEEE Transactions on Intelligent Transportation Systems (2024).

# Citation

Below is the BibTeX format citation for our paper:

```
@ARTICLE{10530508,
  author={Gao, Hang and Hu, Mengting and Liu, Yi},
  journal={IEEE Transactions on Intelligent Transportation Systems}, 
  title={Learning Driver-Irrelevant Features for Generalizable Driver Behavior Recognition}, 
  year={2024},
  volume={25},
  number={10},
  pages={14115-14127},
  keywords={Training;Vehicles;Feature extraction;Data augmentation;Data models;Testing;Public security;Generalization;driver distraction;behavior recognition;feature decomposition;co-training},
  doi={10.1109/TITS.2024.3396640}}

```

# Acknowledgments

This work was supported by National Key R&D Program of China (No.2021YFC3001500), National Natural Science Foundation of China (No.72174102,No.91646101, No.72334003), and High-tech Discipline Construction Fundings for Universities in Beijing (Safety Science and Engineering). We would like to express our sincere gratitude to the reviewers and the editors for their valuable suggestions.
