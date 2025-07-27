---
layout: post
title: Systems Engineering Project 1
description: "A project to design an arena for the AgileX LIMO robot to test SLAM, navigation, and obstacle avoidance."
skills: 
  - ROS
main-image: /Limo_pro.png
---

For this project, my team created and constructed a physical arena for the AgileX LIMO mobile robot as part of a robotics systems engineering project. The environment was designed for the LIMO robot to perform tasks such as navigation, path planning, mapping, and localization. Additionally, understanding how the robot interacts with its environment, handling design trade-offs under time and financial constraints, and cooperating as a team were all necessary factors for this project. Hence, the final result would reflect reliable testing of SLAM and obstacle avoidance of the arena.

<br><br><b>Arena Design</b><br><br>

Before the actual implementation of the robot's autonomous navigation, the arena had to be created. Our team's arena design was a collaborative and iterative process which began with a survey of Changi Airport Terminal 1 to gather perspective of distinct landmarks such as the arrival/departure halls and Kinetic Rain. With these references, we created an initial 3D layout on SolidWorks to model the arena layout. 

After that, our team reviewed and refined the design based on space constraints and material limitations. Key modifications included removing ramps to simplify the construction of the arena and focusing on scalable elements like walls, flooring, and decorative structures. We sourced materials such as foam board for the flooring and walls, clay for the Kinetic Rain Droplets (practical to build and aesthetically accurate), and spray paint for finishing.

Through trial and error and feedback, the final arena design managed to capture the essence of Changi Airport Terminal while also following the technical requirements of AgileX LIMO robot's navigation.

{% include image-gallery.html images="profile-image/arena_design.jpg" %}

<br><br><b>Implementing System Approach</b><br><br>

Our team applied the Systems Approach from SEBoK to guide the designing of the arena and overall project execution. First off, we began with problem identification, which involved identifying constraints like space limitations and material availability. For solution synthesis, we explored possible solutions to mitigate this problem — for example, segmenting the arena into modular components (Kinetic Rain, walls), and allocating tasks based on members’ expertise. 

Doing trade-off analysis, such as choosing foam over pricier materials and excluding ramps from the arena for feasibility, dictated our decisions. Verification was evident in the SolidWorks design revision (v1.0 to v1.1) by contrasting it against stakeholders’ requirements. Validation involved testing the navigation in the physical arena.

<br><br><b>Robot Navigation</b><br><br>

From the available tools, our team decided to use RTAB-Map navigation over GMapping and Cartographer, as our arena (and others') was more complex and required detailed scanning and mapping of obstacles.

To implement RTAB-Map with the LIMO robot, we followed a workflow:

```bash
roslaunch limo_bringup limo_start.launch
roslaunch dabai_u3.launch
roslaunch limo_rtabmap_orbbec.launch
roslaunch rtabmap_rviz.launch
