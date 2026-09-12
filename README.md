# UAV Systems Integration with PX4 and ROS 2

This repository summarizes my hands-on work with UAV hardware, onboard computing, PX4, and ROS 2 at the ARM4L Lab in IRC-SML at KFUPM. My work focused on assembling and configuring a hexacopter autonomy platform built around a Pixhawk/PX4 flight controller and NVIDIA Jetson companion computer, integrating communication and sensing hardware, and establishing the software infrastructure for autonomous flight experiments. I also worked with SITL/HIL simulation, flight testing, calibration, and system-level debugging.

<p align="center">
<img src="assets/Hexa_flying_overview.jpeg" width="850">
</p>


---

## UAV Platform & Hardware Integration

- Assembled and configured a research hexacopter platform.
- Worked with a Pixhawk/PX4 flight controller and NVIDIA Jetson companion computer.
- Configured telemetry and manual RC control for flight testing and failsafe operation.
- Integrated optical-flow, RGB, and FPV sensing hardware.
- Performed flight-controller configuration, calibration, flight testing, and hardware troubleshooting.
- Prepared documentation for each of the steps for reproducibility, such as [PX4 and ROS2 Integration](ros2_px4_pixhawk_guide.md).

<p align="center">
<img src="assets/Just_pixhawk.jpeg" width="50%">
<img src="assets/Jusr_Jetson.jpeg" width="35%">
<img src="assets/hexa_assembled.jpg" width="730">
</p>

---

## PX4, ROS 2 & Onboard Autonomy

- Configured PX4 ↔ Jetson communication using MAVLink over Ethernet and serial.
- Set up XRCE-DDS communication between PX4 and ROS 2.
- Used ROS 2 Humble with Gazebo Ignition for SITL/HIL testing.
- Worked with QGroundControl for vehicle configuration and telemetry.
- Debugged networking, telemetry, and companion-computer synchronization issues.

<p align="center">
  <img src="assets/Moving_flight.gif" width="750">
</p>

<p align="center">
  <em>QGroundControl connection and telemetry monitoring during PX4 vehicle testing.</em>
</p>

<p align="center">
  <img src="assets/off_board.png" width="750">
</p>

<p align="center">
  <em>PX4 offboard-control testing with ROS 2, Gazebo Sim, and QGroundControl.</em>
</p>

<p align="center">
  <img src="assets/ros_setup29.png" width="750">
</p>

<p align="center">
  <em>ROS 2–PX4 communication verification through XRCE-DDS, showing PX4 topics and live sensor data.</em>
</p>

---

## Sensors & Peripherals

The platform included several communication and sensing components that I configured and tested:
- Optical-flow sensor
- RGB camera
- Holybro SiK telemetry radio with FPV camera and air unit
- Wireless Telemetry
- RadioMaster TX16S transmitter/receiver

### ARK Flow MR: Optical Flow and Range Sensing
<p align="center">
  <img src="assets/arc_flow_main.jpg" width="750">
</p>

<p align="center">
  <em>ARK Flow MR optical-flow and range-sensing module used for onboard motion and distance estimation.</em>
</p>

<p align="center">
  <img src="assets/ARC_PARAMS_ALL.png" width="750">
</p>

<p align="center">
  <em>PX4 parameter configuration for ARK Flow MR integration, including optical-flow, rangefinder, EKF2, and UAVCAN settings.</em>
</p>

<p align="center">
  <img src="assets/ARC_PARAMS_DISTANCE_TEST.jpeg" width="750">
</p>

<p align="center">
  <em>Live ARK Flow MR range-sensor verification in QGroundControl using MAVLink Inspector, showing real-time DISTANCE_SENSOR measurements.</em>
</p>

### RGB Camera and Jetson Integration
<p align="center">
  <img src="assets/camera_working.jpeg" width="750">
</p>

<p align="center">
  <em>RGB camera integration and live video-stream verification on the NVIDIA Jetson companion computer.</em>
</p>


### SIYI MK15 FPV and Camera System

- Integrated the SIYI air unit, dual-camera setup, ground controller, and Jetson-Pixhawk platform for live FPV/video monitoring and onboard system integration.

<p align="center">
  <img src="assets/SIYI_full_setup_norc.PNG" width="750">
</p>

<p align="center">
  <em>SIYI MK15 FPV system integration with the Jetson-Pixhawk platform, showing the air unit, dual-camera setup, power distribution, telemetry/data connection, and ground controller video feed.</em>
</p>

### Wireless Telemetry and QGroundControl
<p align="center">
  <img src="assets/telem_QGC.png" width="750">
</p>

<p align="center">
  <em>Wireless telemetry link setup between the Pixhawk flight controller and ground station for QGroundControl communication.</em>
</p>

### RadioMaster TX16S and RC Receiver
<p align="center">
  <img src="assets/RC_controller.jpeg" width="650">
</p>

<p align="center">
  <em>RadioMaster TX16S transmitter configured for manual UAV control and failsafe operation.</em>
</p>

<p align="center">
  <img src="assets/rc_connec.PNG" width="750">
</p>

<p align="center">
  <em>RC receiver integration through the S.Bus interface, connecting the air unit to the Jetson-Pixhawk platform for manual control input.</em>
</p>


 

---

## Mounting Hardware Design and Flight Testing
- Designed and adapted mounting hardware for the onboard electronics and was responsible for the fabrication process.
- The designs included:
  - Pixhawk 6X pro mounting plate
  - Jetson-Pixhawk mounting plate
  - ARC Flow MR mounting plate
 
<p align="center">
  <img src="assets/Jetson_plate_design.PNG" width="450">
</p>

<p align="center">
  <em>SolidWorks design of the custom mounting plate for the Jetson-Pixhawk onboard computing and flight-control assembly.</em>
</p>

<p align="center">
  <img src="assets/ARC_plate_Printed.jpeg" width="750">
</p>

<p align="center">
  <em>3D-printed mounting-plate prototypes developed for integrating the ARK Flow MR module with the UAV frame.</em>
</p>

<p align="center">
  <img src="assets/case_v2_1.jpeg" width="750">
</p>

<p align="center">
  <em>Installed Pixhawk and ARK Flow MR assemblies on the UAV using the custom-designed mounting plates.</em>
</p>

- Flight Testing included:
  - Progressed the UAV platform from bench integration to flight testing.
  - Performed vehicle configuration and calibration.
  - Verified communication links and system connectivity.
  - Conducted flight tests and evaluated system behavior.
  - Troubleshot issues encountered during unsuccessful tests.
  - Repaired or replaced damaged components when required.   

<p align="center">
  <img src="assets/airframe_1.jpg" width="750">
</p>

<p align="center">
  <em>PX4 airframe selection and geometry configuration in QGroundControl for the UAV platform.</em>
</p>

<p align="center">
  <img src="assets/motor_2.png" width="550">
</p>

<p align="center">
  <em>PX4 actuator configuration and motor assignment in QGroundControl, including output mapping and motor spin-direction verification.</em>
</p>


---

### FPV Drone Racing

Separately, I designed and assembled a custom FPV quadcopter from the frame and individual components and competed using Betaflight. I placed 2nd in the 8th International FPV Drone Racing Competition at the Military Technical College, Egypt, in August 2024.

<p align="center">
  <img src="assets/FPV_drone.jpg" width="750">
</p>

<p align="center">
  <img src="assets/FPV_drone_win.jpg" width="750">
</p>
