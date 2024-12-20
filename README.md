**Knee Osteoarthritis Classification Using Bone Distance**

Introduction:

Osteoarthritis (OA), a prevalent degenerative joint disease, a6ects older adults and causes pain, disability, and reduced quality of life. The knee is particularly vulnerable, making accurate assessment of knee OA severity crucial for timely diagnosis and treatment. Traditionally, severity evaluation relies on the subjective Kellgren-Lawrence (KL) grading scale, which is inconsistent and time consuming. Automated, objective approaches are needed to streamline the diagnostic process. Femur-tibia bone distance measurements are an indirect biomarker for cartilage thickness. Unlike direct cartilage measurement, bone distance analysis is more accessible and e6icient. By leveraging MRI-derived bone masks, this method facilitates automated severity classification through machine learning workflows.

This study presents a novel pipeline for knee OA severity classification using automated femur-tibia bone distance measurements integrated with a Convolutional Neural Network (CNN) framework. Advanced image segmentation techniques and machine learning improve classification accuracy and reliability, paving the way for scalable clinical applications.

Method:

Custom algorithm identified approximately valid slices per patient by selecting slices with complete femur and tibia structures and excluding irrelevant ones. Followed by adaptive thresholding and morphological closing operations to enhance segmentation, bone contours were detected using external contour methods, with the largest contour identified as the femur and the second largest as the tibia. Distance measurements were restricted to the gap region between the femur and tibia, where Euclidean distances were computed for all boundary points. The average distance across gap-specific points were calculated per slice and aggregated into feature vectors for each patient. These vectors were used to train machine learning models, including CNN and Random Forest classifiers in distinguishing binary classifications of non-OA (KL 0–2) from OA (KL 3–4) cases.

Steps to recreate:

Dataset: Please drop a request mail for dataset and test class. {jshan@pace.edu}

Steps:
1. Dataset Preparation: 
• Ensure you have the MRI dataset with bone masks and that the images are in the correct directory structure.

• Update the “image_path” in the scripts to point to the directory where the images are stored.

• Update the feature_vector_1, featire_vector_2, feature_vector_3 to find di6erent accuracies.

• Feature importance is only recommended for feature_vector_1 i.e. step =1.

2. Feature Extraction:

• The feature extraction step will compute the femur-tibia distances for each valid slice. The output will be a CSV file containing the feature vectors for each patient.

3. Machine Learning:

• Run the machine learning section using the feature vector and assigning test class.

Conclusion:

This project offers a method to classify knee osteoarthritis using femur-tibia bone distances derived from MRI images, providing a less invasive alternative to direct cartilage measurement. The model's performance can be further improved by refining the feature extraction process and using advanced machine learning models.
