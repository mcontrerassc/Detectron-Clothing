# Fashion Classification: Training Strategy with Detectron2
Authors: Sonora Halili, Michelle Contreras Catalan, Gema Mercado

Through use cases like inventory management, trend analysis, personalized recommendations on apps like Vinted and Depop, as well as price prediction for vintage reselling, fashion classification is an important task in computer vision. In this project, we present a method to detect and classify fashion articles quickly and accurately, building upon our experience with training a model using the Fashion-MNIST dataset.

The main constraint of the widely used Fashion-MNIST dataset that we aim to address is that all images are 28x28 pixels and in grayscale. Therefore, it does not work nicely on real user inputs because fashion photographs come in different formats and sizes, sometimes showing clothes worn on models and other times photographed separately.

## Approach:
Our approach uses Detectron2, a state-of-the-art library developed by Facebook Research, along with COCO-Detection, a pre-trained model for detection and segmentation. We opted for the `COCO-Detection/faster_rcnn_R_101` version for faster results. This model can be used to detect, segment, and caption objects in pictures. We trained this model on a custom fashion dataset to enable it to classify clothes into one of these categories: Tops, Blouses, Trousers, Shorts, Skirts, Pullovers, Jackets, Jumpsuits, and Coverups.

## The Dataset:
To train our model, we used the DeepFashion2 dataset, a comprehensive collection of 491,000 images spanning tens of popular clothing categories. Each image in the dataset is labeled with its respective attributes, including scale, occlusion, viewpoint, category, style, bounding box, dense landmarks, and per-pixel mask. Besides the category attribute, scale and bounding box were of particular interest, as they enabled us to keep the original images from the dataset, with no need to resize. However, we did some heavy pre-processing before our dataset was ready to be fed into the COCO-Detection model.

