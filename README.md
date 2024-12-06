# Object_Detection_Using_RaspberryPI
The Repository describes the implementation of real time object detection on Raspberry PI using tensorflow lite model
The project is divided in the following chapters,
<details>
  <summary>1. Prerequisites needed to implement the project</summary>
For this project, a Raspberry Pi board, an external monitor, a keyboard, and a mouse are required to interact with the board. Alternatively, the board can be accessed by connecting it directly to a laptop, but the method for accessing the board differs in this case. We will discuss that approach in another repository.
  
![2024-12-06-15-08-47-192 1](https://github.com/user-attachments/assets/44fd84db-a7b4-4333-82db-d2d264a98fcc)

The Raspberry Pi board used in this project is the Model 3 B version. To connect the monitor, use an HDMI cable, and similarly, USB ports can be used to connect other peripherals such as the mouse, keyboard, and camera. Refer to the image provided to ensure the hardware connections are set up correctly.

</details>

<details>
  <summary>2.Setting up the board.</summary>

  1. Raspbery Pi Image <a href="https://www.raspberrypi.com/software/operating-systems/" target="_blank">Download here</a>
  Once the imager is download, user need to have an SD card over which the ISO file i.e image file needs to be burned.

![image](https://github.com/user-attachments/assets/ecc76540-a165-4dc6-a6d6-9949f387b970)

Select the operating system (OS) you wish to burn onto the SD card. For this project, I have used Raspberry Pi OS (64-bit), which is highly versatile and suitable for most applications. Please note that burning the OS onto the SD card will erase all existing data on it, so ensure you back up any important files beforehand.

![image](https://github.com/user-attachments/assets/4e7e79fe-0d6c-4753-9222-7aed4edb21c9)

Once the OS i.e ISO file is burned to the card, we will establish the hardware connection as discussed in the previous chapter. Once that is done we need to enable the camera settings and test whether the board is able to access the camera or not, for that we will click a picture, the same is demonstrated below.
Updating the Raspberry PI we need to run the following commands 

```
sudo apt-get update
sudo apt-get upgrade
```

![Screenshot 2024-12-06 152200](https://github.com/user-attachments/assets/1ecd7f59-b54f-4d3e-9c3a-6157ab01ef19)

</details>

<details>
  <summary>3.Setting up the environment</summary>
Once this is done we will proceed towards setting up the virtual environment, this holds the tensorflow lite dependencies and prevents the project to intervene the other projects.
  
```
sudo pip3 install virtualenv
```


After installing this we will make a new environment, to work on our project this is akin to creating a separate workspace for a new project.

```
python3 -m venv <new_env_name>-env
```
Activate the environment using 
```
source acitvate <new_env_name>-env/bin/activate
```
Everytime user closes the window, user needs to activate the environment using the above command 
</details>

<details>
  <summary>4.Downloading the model and installing the dependencies.</summary>
  Once the model dependencies are installed, we need to download the model, the model which is used here is coco_ssd_mobilenet_v1_1.0_quant_2018_06_29,

  The coco_ssd_mobilenet_v1_1.0_quant_2018_06_29 is a pre-trained object detection model from TensorFlow Lite that is optimized for mobile and embedded devices.
  
 # Model Architecture:
  - Based on SSD (Single Shot MultiBox Detector) for object detection.
  - Uses MobileNetV1 as the backbone network for feature extraction, which is lightweight and efficient.
 # Data Set:
  - Trained on the COCO (Common Objects in Context) dataset, which contains 80 classes of common objects such as people, animals, and everyday items.
 # Data Set: 
  - Post-training quantization is applied to reduce the model size and improve inference speed without significant loss of accuracy
  - This makes it suitable for deployment on devices with limited computational resources, like microcontrollers and mobile devices.
# Model Input and Output:
Input:
 - A single image, typically resized to 300x300 pixels.
 - The input image should be normalized (e.g., pixel values between 0 and 1).
Output: 
  A list of detected objects, including:
   - Bounding box coordinates (normalized values).
   - Class index (integer corresponding to the detected object category).
   - Detection confidence score (between 0 and 1).
# Size details
   - Small model size (~4 MB) due to quantization, making it efficient to load and run on constrained devices.
</details>

<details>
  <summary>5.Implementation and result observation.</summary>



https://github.com/user-attachments/assets/d6c40dfb-6051-45e4-8037-5ecf1c49248b


</details>

