# COWPEA-DATABANK-WITH-CODE

#importing the libraries
import os 
import cv2
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline

#appending the pics to the training data list
training_data = []
for img in os.listdir(path):
    pic = cv2.imread(os.path.join(path,img))
    pic = cv2.cvtColor(pic,cv2.COLOR_BGR2RGB)
    pic = cv2.resize(pic,(200,200))
    training_data.append([pic])
    
    #converting the list to numpy array and saving it to a file using #numpy.save
np.save(os.path.join(path,'features'),np.array(training_data))

#loading the saved file once again
saved = np.load(os.path.join(path,'features.npy'))

plt.imshow(saved[0].reshape(200,200,3))
plt.imshow(np.array(training_data[0]).reshape(200,200,3))
<matplotlib.image.AxesImage at 0x7f5663539610>
<matplotlib.image.AxesImage at 0x7f5663539610>
![image](https://user-images.githubusercontent.com/98248337/215270668-9f8b8366-51e7-43fa-a145-de9f66228fe5.png)

plt.imshow(saved[1].reshape(200,200,3))
plt.imshow(np.array(training_data[1]).reshape(200,200,3))

![image](https://user-images.githubusercontent.com/98248337/215270692-f705fecd-067c-4773-b60f-ba5b9f8a974a.png)

plt.imshow(saved[10].reshape(200,200,3))
plt.imshow(np.array(training_data[10]).reshape(200,200,3))

![image](https://user-images.githubusercontent.com/98248337/215270727-63e00f70-0bf8-49dd-b506-bb1b462bae16.png)
