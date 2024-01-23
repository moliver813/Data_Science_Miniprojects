# Image Extrapolator

The goal of this project is to practice creating models for iamge transformation.
The objective is to be able to take an image, and try extrapolating outside the boundaries of the image.
Obviously, perfect extrapolation is impossible, but many features in images can be extrapolated.
'Errors' in extrapolation could also be of potential visual interest.

Part of the initial motivation for this project was to do something with images beyond classification. 
I was also motivated to start this when I realized how simple the setup for it would be: for each image
in a dataset, take the full image as the target and apply a crop to create the input features.
In the earliest versions, I used simple dense networks, and then switched to convolutional layers once
I figured one method to expand the size of the images in the model. These produced many reasonable results.

One aspect of the early versions of this was the model did not automatically forward the input to the middle 
of the output, so this was a task the model had to learn. Later, after gaining more experience and confidence with tensors,
I implemented the forwarding in a tensor friendly way, letting the model train more efficiently.
