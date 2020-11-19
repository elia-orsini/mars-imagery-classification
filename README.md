# mars-imagery-classification


I have here developed a convolutional neural network (CNN) that classifies into 24 distinct categories images taken by the Curiosity rover on the surface of Mars. The dataset of 6691 images has been provided by Wagstaff *et. al.* (2018). Wagstaff *et. al.* (2018) adopted a convolutional neural network getting the following results:

**Train &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Validation &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Test**<br />	
**98.7% &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 72.8% &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 66.7%**

Training a completely new neural network requires a high amount of computational power. For this reason, I decided to use a technique which has been adopted by Wagstaff *et. al.* (2018) as well. The technique is called transfer-learning and it consists of using a pre-trained neural network. The pre-trained neural network used (EfficientNetB7) was trained for a different scope from the one I was aiming for. Indeed, it was trained using a dataset called ImageNet, which contains more than 14 millions images of various categories (such as animals, people or objects). 
Therefore, to have the most efficient model I had to modify and train a portion of it with the dataset of images from Mars. Furthermore, to prevent the network from overfitting, I added some extra-layers like an image-augmentation layer and a dropout layer. These are the results I was able to get:

**Train &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Validation &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Test**<br />	
**99.76% &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 74.27%  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 78.77%**

These results represent an increase in the performances compared to the model previously used by Wagstaff *et. al.* (2018). These improvement is probably due to the higher efficiency of the pre-trained model I used.

Graph 3 shows the total number of cases for each category in the test set and the number of wrong predictions for each of those categories. Graph 4 shows the percentage of errors for each category on the test set. It results from this that the most exact predictions are performed on the categories 24 and 8 of the dataset which are respectively a wheel and the ground. It is probably not a coincidence that these two categories have the most distinctive features in the dataset.

![alt text](https://github.com/elia-orsini/mars-imagery-classification/blob/main/graph-3.jpg?raw=true)
![alt text](https://github.com/elia-orsini/mars-imagery-classification/blob/main/graph-4.jpg?raw=true)
