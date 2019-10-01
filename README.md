# Age Group Prediction

# Dataset

I used IMDb-Wiki Dataset. This dataset contains 10k+ images across 100 different folders with each containing images of the actors of that age number. Train-Test split is 80-20.

# Preprocessing
Images containing more than one person or are very small in size were removed.
<br/>Viola-Jones face detection algorithm was used for extracting the face of the person from the image.
<br/> Local Binary Pattern is a texture operator used for feature extraction, was applied to the extracted face from the input image of the person.
<br/> Age Groups were (0-20), (21-50) and (51-100).

# Training and Testing
One vs all approach was used for classification of the age group.
<br/>So, for three class classification problem, three Support Vector Machines were used for the prediction.
<br/>Feature Vectors obtained from the Preprocessing step were used as input to the SVM.
<br/>Each SVM has to find the probablity of the image belonging to their age group. 
<br/>For training, each svm was fed with the feature vectors of training images labelled as positive if they belong to that particular age group else negative.
<br/>Similar to training, testing feature vectors of testing images are labelled as positive for images having same age group as that svm on which it is tested.

# Prediction
Image is converted to a feature vector as mentioned in the above steps and is fed into three SVMs.
<br/>SVMs finds the probablity of that feature vector belonging to their age group.
<br/>Age Group will be of the SVM representating the age group having maximum score.
