# Motivation

In this notebook, I implemented a CNN from scratch to:
- classify the label in an image.
- localize it by drawing bounding boxes around it.

The [MNIST](http://yann.lecun.com/exdb/mnist/) dataset is used to synthesize a custom dataset for the task:
- Place each `digit` image on a black background of width 75 x 75 at random locations.
- Calculate the corresponding bounding boxes for those `digits`.

The bounding box prediction can be modelled as a `regression` task, which means that the model will predict a numeric value.

# Define the Network

Here, we define our custom CNN. 
- `feature_extractor`: these convolutional layers extract the features of the image.
- `classifier`:  This define the output layer that predicts among 10 categories (digits 0 through 9)
- `bounding_box_regression`: This defines the output layer that predicts 4 numeric values, which define the coordinates of the bounding box (xmin, ymin, xmax, ymax)
- `final_model`: This combines the layers for feature extraction, classification and bounding box prediction.  
  - Notice that this is another example of a branching model, because the model splits to produce two kinds of output (a category and set of numbers).  
  - Since you've learned to use the Functional API earlier in the specialization (course 1), you have the flexibility to define this kind of branching model!
- `define_and_compile_model`: choose the optimizer and metrics, then compile the model.

<p align="center"><img src="https://user-images.githubusercontent.com/3027146/144435483-5e8bb388-e276-44aa-bdd6-b4a5fa7f0256.jpg" width="800"></p>

# Make a prediction
<p align="center"><img src="https://user-images.githubusercontent.com/3027146/144435627-07feb8a3-d20a-4ad4-a86c-35c9ce3843b5.jpg" width="800"></p>

