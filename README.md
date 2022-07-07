# predicting-fashion-attributes
Steps to run this project 
1. Upload images with folder name as "images"
2. Split the image dataset into two datasets as train and val by running "dataset_distribution(train_and_val).ipynb"
3. Run "Flixstock_assignment.ipynb".
Output will be stored as "submission.csv" in the same directory

# My Approach
1. the null values were replaced by mode of each attribute( the frequency of specific value in each attribute was very high so the best probability for the given null values could be given by mode)
2. Values in each attribute are converted from float to string
3. Values of all the attributes are concatenated and stored into a new attribute(New_class) in the same dataframe. Example: there are attributes with values a:1,b:2,c:3 then the value in New_class will become 123.
![Screenshot 2022-07-07 175031](https://user-images.githubusercontent.com/51014994/177771811-0900a89b-8b44-4d3d-beec-0a6027205323.png)
4. New_class has 19 categories in the given dataset
5. Now this problem is converted into a simple multi-class classification problem with input X as the image and output Y as one of the classes from New_class
6. We have used the InceptionResNetV2 architecture with imagenet weights as base and fine-tuned it for our problem. Our final model looks as follows:

![Screenshot 2022-07-07 180051](https://user-images.githubusercontent.com/51014994/177773800-4e788cd4-dd58-4408-bd82-15cee712efd8.png)

7. We have used val folder for testing and its output are saved in "submission.csv"

# Naive Approach
1. This task can also be done using cnn for each attribute(In this case 3). Code for this approach has also been uploaded as file names: neck.ipynb,sleeve_length.ipynb and pattern.ipynb
2. Although this is an inefficient approach as with large number of attributes making a cnn for each attribute will be a very tedious and time consuming task. Also the real time use will consume a lot more time therefore won't be much productive.

Things I am unable to do in the given timeframe:
1. I coudn't work on more nets like AlexNet, VCG-16 etc.


Reasons for incomplete task is I had to study for my college end-term examination, therefore was preoccupied in the aforementioned.
