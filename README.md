# Real-time Drone Camera feed based Object Detection simulation in Gazebo

I've always found Image Processing and Computer Vision applications fascinating at the same time I love watching drone flight videos on youtube. As my interest peaked I had to come through with implementing this project and enhance my theoretical and working knowledge at the same time. For a comprehensive Overview of the project, I suggest you check out the following article,

## [Drone simulation with object detection](https://iq.opengenus.org/drone-simulation-with-object-detection/)

Let's start with the exciting part, the outcome of the project looks something like this,

![Simulation Result](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/blob/main/Images/Simulation%20Result.png)

> ! Note unlike other projects this was implemented on a Linux (Ubuntu version 22.04) system

### Required Components for the project are,

1. ROS (Robot Operating System)
> Hosts the components
2. Mavros
> Serves as the communication bridge
3. Ardupilot
> Controls the drone
4. Gazebo
> Simulation environment
5. darknet_ros package
> Yolov3 model for object detection

They are structured in the following manner,

![Communication Pipeline](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/blob/main/Images/Communication%20Pipeline.png)

Finally, the underlying communication between nodes is described in the following diagram,

![rqt graph1](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/blob/main/Images/rqt%20graph%201.jpg)

![rqt graph2](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/blob/main/Images/rqt%20graph%202.jpg)

The main components and foundations used in this project were derived from **Intelligent Quads Repos** my work was just trying to figure out how to integrate each component and put them together to get the desired outcome.

## Documentation

The documentation of this project can be found [here](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/blob/main/Report.pdf)

## Run Locally

You can either try and explore the [Intelligent Quads Repo](https://github.com/orgs/Intelligent-Quads/repositories) to customize your implementation.


Nevertheless, for the exact implementation in this project, you can download the different components mentioned earlier from files provided in this repo (any missed files can be derived from the source) and follow the below-given steps,

> Create the CMake and XML file for your ROS package or derive and modify the sources.

1. Run the [runway.lauch](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/blob/main/runway.launch) launch file, this should load the world in gazebo
```
Roslauch "relative directory" runway.launch
```
2. Import the [drone_with_camera](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/tree/main/drone_with_camera) model into the world gazebo simulation.

> You should be able to see the drone present on the runway

3. Initialize [ardupilot](https://github.com/genpranav/Yolov3-Object-Detection-from-Drone-feed/blob/main/apm.launch) and set mode to guided before waiting a few seconds for it to load completely
```
Roslauch "relative directory" apm.launch
```

>You can now provide flight [commands](https://ardupilot.org/dev/docs/copter-sitl-mavproxy-tutorial.html) through ardupilot to the drone and watch it move around and also view the camera feed.

4. You can now run the [darknet package](https://github.com/leggedrobotics/darknet_ros
)

```
Roslaunch darknet daknet.launch 
```

>The simulation is complete you should now see the objects being detected over the camera feed.

The documentation also contains multiple drone swarm coordination but is not implemented completely.

### Socials plug

<details open>
<summary>B.E.Pranav Kumaar</summary>
Student ID @Amrita Vishwa Vidyapeetham - CB.EN.U4AIE20052

:fire: [twitter](https://twitter.com/bepranavkumaar1)

:zap: [LinkedIn](https://www.linkedin.com/in/pranav-kumaar/)

:snowflake: [Github](https://github.com/genpranav)

</details>

