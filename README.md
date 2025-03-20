<div id="top"></div>

<h1 align="center">SteeAir - Steer the car with hand in air!</h1>
<!-- PROJECT LOGO -->:
<br />
<div align="center">
  <a href="https://jacobsschool.ucsd.edu/">
    <img src="/media/UCSDLogo_JSOE_BlueGold.png" alt="Logo" width="400" height="100">
  </a>
<h3>MAE148 Final Project</h3>
<p>
Team 13 Winter 2025
</p>

![image](https://github.com/JL2200/mae148_group8/blob/main/media/IMG_4898.JPG)
</div>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#team-members">Team Members</a></li>
    <li><a href="#final-project">Final Project</a></li>
      <ul>
        <li><a href="#original-goals">Original Goals</a></li>
          <ul>
            <li><a href="#goals-we-met">Goals We Met</a></li>
            <li><a href="#our-hopes-and-dreams">Our Hopes and Dreams</a></li>
              <ul>
                <li><a href="#stretch-goal-1">Stretch Goal 1</a></li>
                <li><a href="#stretch-goal-2">Stretch Goal 2</a></li>
                <li><a href="#stretch-goal-3">Stretch Goal 3</a></li>
              </ul>
          </ul>
        <li><a href="#final-project-documentation">Final Project Documentation</a></li>
      </ul>
    <li><a href="#robot-design">Robot Design </a></li>
      <ul>
        <li><a href="#cad-parts">CAD Parts</a></li>
          <ul>
            <li><a href="#final-assembly">Final Assembly</a></li>
            <li><a href="#custom-designed-parts">Custom Designed Parts</a></li>
            <li><a href="#open-source-parts">Open Source Parts</a></li>
          </ul>
        <li><a href="#electronic-hardware">Electronic Hardware</a></li>
        <li><a href="#software">Software</a></li>
          <ul>
            <li><a href="#embedded-systems">Embedded Systems</a></li>
            <li><a href="#ros2">ROS2</a></li>
            <li><a href="#donkeycar-ai">DonkeyCar AI</a></li>
          </ul>
      </ul>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
    <li><a href="#authors">Authors</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- TEAM MEMBERS -->
## Team Members

<div align="center">
    <p align = "center">Risab, Hugo, Roger, Ricardo</p>
</div>

<h4>Team Member Major and Class </h4>
<ul>
  <li>Risab -  - Class of 2026</li>
  <li>Hugo - Mechanical Engineering - Class of 2026</li>
  <li>Roger -  - Class of 2026</li>
  <li>Ricardo - Aerospace Engineering - Class of 2025</li>
</ul>

<!-- Final Project -->
## Final Project
Our final project aimed to develop a robocar capable of navigating using hand gestures for steering and control, while autonomously detecting and avoiding obstacles using LIDAR technology.

<!-- Original Goals -->
### Original Goals
Originally, our project aimed to implement hand-gesture-based steering control, integrate LIDAR technology for obstacle detection and avoidance, and enable autonomous repositioning to the original route without additional gestures. Our primary objectives included developing a robust gesture-recognition model to accurately respond to hand gestures for stopping, starting, steering control, and dynamically adjusting the robocar’s speed and turning angle. Additionally, we sought to utilize LIDAR technology for autonomous obstacle detection and navigation.
   
<!-- End Results -->
### Goals We Met
We successfully achieved our goal of maneuvering the robocar using hand gestures, enabling commands for the vehicle to start, stop, turn left, and turn right. Specifically, we implemented the OAKD camera to recognize gestures, allowing the vehicle to move forward upon receiving a thumbs-up gesture and turn right or left when recognizing one finger for right turns and two fingers for left turns. Furthermore, we effectively integrated LIDAR technology, allowing the robocar to autonomously detect and avoid obstacles. This was accomplished by integrating the depth.ai library, which provided pretrained hand gesture models, into the Jetson platform, thereby mapping specific hand symbols to corresponding vehicle directions. 

### Future Goals
#### Stretch Goal 1
Establish a robust remote connection and control system for the robocar. We plan to explore different wireless communication protocols and set up video streaming between the user's device and the robocar, enabling real-time remote troubleshooting and control.

#### Stretch Goal 2
We want automatic lidar stopping to be implemented for safety. Since chatgpt does not control the robot in real time, we need a way for the robot to stop if it is about to hit an object or person.

#### Stretch Goal 3
Develop a custom gesture recognition model capable of accurately capturing precise angles and subtle gestures for refined vehicle control. This involves training a new model with an expanded dataset that includes various hand angles and poses to achieve precise and intuitive steering adjustments.


## Features

- **Hand Gesture Steering**: Control the vehicle with different hand gestures.
- **Real-Time Gesture Recognition**: Process hand gestures using an OAK-D camera to detect and translate them into steering actions.
- **LiDAR Integration**: A LiDAR-based system monitors the environment for obstacles and tracks driving behavior to provide fail-safe corrections.
- **Efficient Processing**: The hand gesture recognition model runs on the OAK-D camera, reducing the computational load on the Jetson Nano, ensuring smooth performance.
- **ROS2 Integration**: The system is integrated with ROS2 to handle communication between the hand gesture control and the LiDAR system.

## Hardware List

- **OAK-D Camera**: For hand gesture recognition and depth perception.
- **Jetson Nano**: For running the control system and machine learning models.
- **LiDAR Sensor**: For environment scanning and safety monitoring.

## Implementation

The hand gesture recognition model is designed to run directly on the OAK-D camera, ensuring that the computational load on the Jetson Nano is minimized. The system uses dockerized hand gesture classification model to capture hand gestures, mapping hem into steering commands for the vehicle.

### Hand Gesture Recognition

- The OAK-D camera captures video input of the user's hand gestures.
- A pre-trained machine learning model processes the images to identify specific hand gestures (one, two, fist, etc...)
- These gestures are mapped to corresponding steering actions, allowing users to control the vehicle by simply moving their hands.


https://github.com/user-attachments/assets/5adb9c2c-4ca9-4d20-9c99-be9ab224acd8


### LiDAR Safety System

- A LiDAR sensor is used to monitor the environment and detect obstacles in real-time.
- The system tracks the vehicle's surroundings and provides corrective actions if unsafe driving behavior is detected.
- If the system detects a potential collision or erratic steering, it can trigger the fail-safe mode to correct the vehicle's trajectory.

### ROS2 Integration

- The entire system is connected via ROS2, allowing seamless communication between the hand gesture recognition module and the LiDAR sensor.
- ROS2 facilitates data exchange between the components and enables smooth operation of the gesture-based steering system alongside the safety features.

## Future Improvements

- **Remote Video Input**: The current setup requires the driver to stand behind the vehicle, making steering less convenient. We aim to stream video data to the Jetson Nano so that the driver does not need to move and can control the vehicle from a more comfortable position.
  
- **Memory Option**: This issue can also be addressed by storing gestures as a series of commands or saving a drawn path in the air, allowing the system to recognize and repeat the gesture commands without requiring real-time input every time.


## Final Project Documentation

<!-- Early Quarter -->
### Robot Design CAD
<img src="/media/full%20car%20cad.png" width="400" height="300" />

#### Open Source Parts
| Part | CAD Model | Source |
|------|--------|-----------|
| Jetson Nano Case | <img src="/media/jetson%20nano%20case.png" /> | [Thingiverse](https://www.thingiverse.com/thing:3518410) |

### Software
#### Chatgpt
!!!!!!! FIX THIS SECTION !!!!!!!

We connected Chatgpt to the robocar by using the Openai API, utilizing two seperate models. The first model was GPT4 with Vision, which processes commands from the user and images. Then this model creates an action plan for what the car can do. Since the image based models don't have function calling to trigger the drive commands, we used a second GPT4-Turbo model to read the vision models plan and turn those into functions. Chatgpt had acces to two functions, a drive command to control steering, speed, and motion timeout. Then it had control over a path function, which let chatgpt generate a csv path of x and y coordinates + a throttle for the car to follow. Chatgpt had access to the cameras, lidar data, gps data, and user prompts. We picked and chose which data to give Chatgpt based on the use case.

#### Embedded Systems
To run the system, we used a Jetson Nano with an Oakd depth camera, an ld06 lidar sensor, and a point one Fusion Engine gps. For motion we used a VESC Driver within the Donkey Car framework. https://www.donkeycar.com/

#### ROS2
For commands, we made a ROS2 Node called ChatgptDriveSubpub that works with the UCSD Robocar framework. Most of the files we created are in the basics2 package of the ros2_ws (ros2 workspace). We altered the nav2 config files to add the chatgpt node to start up automatically, but never finished this. So, if you follow the steps to get Ros2 running from the UCSD robocar framework, you are mostly complete.

In our project files, we had to add the fusion engine driver for gps manually, so the nodes for fusion gps are prone to error. One will need 4 to 5 terminals to run this system. One for starting up gps, one for launching all_nodes, one for launching the chatgpt node, one for sending chatgpt messeges over a chat topic, and finally one to use donkeycar's manage.py drive command to drive the car in a desired path. 

#### DonkeyCar AI
For path following, we used the DonkeyCar AI framework and tuned our own PID values. With the donkey car framework, we connected through gps and used PID following of chatgpt generated waypoints for the car. Some example paths are in the donkey_paths folder. Often, chatgpt's paths were innacurate or straight lines, so you may have to be descriptive in your prompts to chatgpt. We found that the system worked best when chatgpt had a good reference understanding of its area size, how many path points to use, and that you want it to use funciton calling.

### How to Run
Use the UCSD Robocar Docker images and add the projects folder yourself. Python3 is required, install any reposotries not there.

Step 1: In the first terminal, start the fusion client. First source ros2. Note, in the build_ros2 file, we exluded the build for the fusion client as each build takes an extra 50 seconds with it.

```source_ros2```

```build_ros2```

```ros2 run fusion-engine-driver fusion_engine_ros_driver --ros-args -p connection_type:=tty -p tty_port:=/dev/ttyUSB1```


Step 2: In a second terminal, build and source ros2 as usual from the ucsd robocar process. Then launch all nodes.

```source_ros2```

```ros2 launch ucsd_robocar_nav2_pkg all_nodes.launch.py```


Step 3: Adjust the chatgpt_drive_node.py in the basics package with your OPENAI API KEY. Launch the chatgpt node. Source ros2 in a third terminal and launch this command.

```source_ros2```

```ros2 launch ucsd_robocar_basics2_pkg chatgpt_drive_launch.launch.py```


Step 4: You are ready to talk to chatgpt. Make sure the terminals output no errors and chatgpt has said "finished init". Then, you publish to a /chat_input topic to communicate with the chatgpt node.

```source_ros2```

```ros2 topic pub -1 /chat_input std_msgs/msg/String "data: 'YOUR MESSEGE HERE'"```


The messege should show up in the chatgpt terminal and if it does not, it did not work. First the vision model will respond with an action plan. Responses can take up to 20 seconds. Then a Function tool caller will work. Sometimes the tool caller gets stuck and you must restart the chatgpt node. Its recommended to restart all nodes, as another error can be no image input being recieved from the all_nodes.

Step 5: If you desire a path to be made, then chatgpt will have outputed the path to the donkey_paths folder in the basics2 package. You can take this csv, and use its path in the donkey car manage.py config files for donkey car to drive on this desired path. Make sure your path starts at 0,0 or to zero the car and drive to the path start. The donkey command to run in a 5th terminal is

```manage.py drive ```

For more information, see the donkey car framework on running with your own car. When manage.py runs, use x to zero the car, b to load a path, and double tap start for the car to follow the path.

Here is a link which contains many photos and videos of our robot doing different chatgpt powered actions:
https://photos.google.com/u/0/share/AF1QipNbnRdItg1uGULNdo4saggAoKI3nbOa-YogXLWNfc9HYORkTFDVzfL07XVTVJIqRg?key=WGtpSk1jdEJXZjJ6cHpObENFQU9MSzItVG1jOXN3 

<!-- Authors -->
## Authors
Risab, Hugo, Roger, Ricardo

![image](https://github.com/UCSD-ECEMAE-148/winter-2024-team-2aka8/blob/main/media/148groupphoto.jpg)

<!-- Badges -->
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

<!-- ACKNOWLEDGMENTS -->
## Acknowledgments
*We would like to recognize the help from Professor Jack Silberman, TA Alexander, Winston, Vivek for an amazing Winter 2024 class! Thank you Alexander for the amazing readme template.*

<!-- CONTACT -->
## Contact

* Risab | Rsankar@ucsd.edu
* Hugo | hdemendoza@ucsd.edu 
* Roger | kel030@ucsd.edu
* Ricardo | rir007@ucsd.edu
