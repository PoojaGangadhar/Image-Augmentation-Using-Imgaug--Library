# Image-Augmentation-Using-Imgaug-Library


Imgaug is a image augmentation library used to augmentb datasets in machine learning projects. Imgaug supports augmentation of images, keypoints/landmarks, bounding boxes, heatmaps and segmentation maps in a variety of different ways.

# To install imgaug using command prompt:
pip install imgaug

# Here is the link for imgaug documentation 
https://imgaug.readthedocs.io/en/latest/

### Augmentation Methods
1. Affine Translation, Flip upside down, Mirror flip, Gaussian Blur, Rotate
augmentation = iaa.Sequential([
    iaa.Rotate((-30, 30))  
    iaa.Fliplr(0.5),
    iaa.Flipud(0.5),
    
    iaa.Affine(
        translate_percent={"x":(-0.2, 0.2), "y":(-0.2, 0.2)},
        rotate=(-30, 30),
        scale ={"x":(0.5, 1.5), "y":(0.5, 1.5)}
    ),
    
    iaa.Multiply((0.8, 1.2)),
    
    iaa.LinearContrast((0.6, 1.4)),
    
    iaa.GaussianBlur((0.0, 3.0))
])

augmented_img = augmentation(images=datasets)
    
