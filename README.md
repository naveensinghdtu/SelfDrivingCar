# SelfDrivingCar

The aim of the project is segmentation of real traffic images using Unet and CANet. The images and their corresponding json files for training the network was 
available in the following format:-

<pre>
|--- data
|-----| ---- images
|-----| ------|----- Scene 1
|-----| ------|--------| ----- Frame 1 (image 1)
|-----| ------|--------| ----- Frame 2 (image 2)
|-----| ------|--------| ----- ...
|-----| ------|----- Scene 2
|-----| ------|--------| ----- Frame 1 (image 1)
|-----| ------|--------| ----- Frame 2 (image 2)
|-----| ------|--------| ----- ...
|-----| ------|----- .....
|-----| ---- masks
|-----| ------|----- Scene 1
|-----| ------|--------| ----- json 1 (labeled objects in image 1)
|-----| ------|--------| ----- json 2 (labeled objects in image 1)
|-----| ------|--------| ----- ...
|-----| ------|----- Scene 2
|-----| ------|--------| ----- json 1 (labeled objects in image 1)
|-----| ------|--------| ----- json 2 (labeled objects in image 1)
|-----| ------|--------| ----- ...
|-----| ------|----- .....
</pre>

And each json file will have 3 attributes
    (i) imgHeight: Height of the image.
    (ii) imgWidth: Width of the image.
    (iii) objects: List of objects, each object having multiple attributes:-
        (a) label: the type of the object
        (b) polygon: a list of two element lists, representing the coordinates of the polygon
        
 The true masks of images were computed using the attributes of the json files corresponding to those images. The network was then trained on real images and their
 computed masks. The loss used for training the network was Focal Loss/Dice Loss.
 
 Finally the results of the two models i.e. Unet and CANet were compared. Unet performed better with a IoU of greater than 0.5 whereas CANet had an IoU of 0.4.
 
