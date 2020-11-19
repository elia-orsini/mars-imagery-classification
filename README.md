# mars-imagery-classification


I have here developed a convolutional neural network (CNN) that classifies into 24 distinct categories images taken by the Curiosity rover on the surface of Mars. The dataset of 6691 images has been provided by Wagstaff *et. al.* (2018). Wagstaff *et. al.* (2018) adopted a convolutional neural network getting the following results:

**Train &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Validation &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Test**<br />	
**98.7% &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 72.8% &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 66.7%**

Training a completely new neural network requires a high amount of computational power. For this reason, I decided to use a technique which has been adopted by Wagstaff *et. al.* (2018) as well. The technique is called transfer-learning and it consists of using a pre-trained neural network. The pre-trained neural network used (EfficientNetB7) was trained for a different scope from the one I was aiming for. Indeed, it was trained using a dataset called ImageNet, which contains more than 14 millions images of various categories (such as animals, people or objects). 
Therefore, to have the most efficient model I had to modify and train a portion of it with the dataset of images from Mars. Furthermore, to prevent the network from overfitting, I added some extra-layers like an image-augmentation layer and a dropout layer. These are the results I was able to get:

**Train &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Validation &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Test**<br />	
**99.76% &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 74.27%  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 78.77%**

These results represent an increase in the performances compared to the model previously used by Wagstaff *et. al.* (2018). These improvement is probably due to the higher efficiency of the pre-trained model I used.<br />
The source code of the neural network is in the Google Colab file.

<br /><br /><br /><br /><br /><br /><br /><br /><br /><br />

**REFERENCES:**

- Kiri L. Wagstaff, You Lu, Alice Stanboli, Kevin Grimes, Thamme Gowda, and Jordan Padams. "Deep Mars: CNN Classification of Mars Imagery for the PDS Imaging Atlas." Proceedings of the Thirtieth Annual Conference on Innovative Applications of Artificial Intelligence, 2018<br />	
- Dataset available online at: https://zenodo.org/record/1049137#.X65UipP7Red. DOI: 10.5281/zenodo.1049137
