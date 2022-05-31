## VITAL

The project involves increasing the precision of landing (one of the most dangerous maneuvers for flying machines) under operational conditions on a mobile platform and taking care of safety in its vicinity.

![team](https://putvision.github.io/assets/images/posts/2022/03/terrinet-we.webp)

### Concept
Systems that support the real-life landing of flying robots are of critical importance if precise docking to a base station is required. The combination of GPS positioning and RTK corrections allows for accurate action to the landing point, but the accuracy of the measurement, the noise and interference make it difficult to accurately target the base station if it is mobile.

Current vision-based unmanned aerial vehicle landing systems are mainly based on Aruco marker detection. The current development of edge devices and miniaturisation of resources allows performing neural network inference on-board the drone. Building a system based on deep learning would generalise such systems and improve their effectiveness in uncontrolled conditions. Additionally, the algorithm allows for the implementation of safety features, such as the ability to detect a human in the neighborhood and hold up the landing process.

The ultimate aim of the research visit is to determine if it is possible to use edge devices to build a vision-based system using deep neural networks to improve precision UAV landing. If not, we will try to answer how current constraints prevent the use of modern technology and indicate possible developments and pitfalls of existing approaches.

### Deep Computer Vision
We designed the algorithm split into two deep learning subtasks. Both utilise UNet-style architectures and meet the following tasks:

the first network was designed as the gaussian density estimator with two output channels: one for the landing pad and the second for people instances,
the second network was developed to regress defined keypoints of the landing pad; the clue of the approach is to add a self-criticised metric that provides the standard deviation of predictions.

### Devices
One of the aims of the project is to perform inference on the edge ai devices with time requirements of steering offboard mode. The utilisation of offboarding steering provided by the device connected to the flight computer limits it to guarantee at least 2 Hz of a signal. Due to this, we defined two cases to check:

NVIDIA Jetson Xavier NX - the goal was to achieve near-real-time performance (20+ frames per second),
Raspberry Pi 4 + Neural Computer Stick 2 - the goal was to break the barrier of 2 Hz.

### Aknowleages

We acknowledge the support of the TERRINet project and would like to express our gratitude to the GRVC team at Sevilla for their hospitality and help.
