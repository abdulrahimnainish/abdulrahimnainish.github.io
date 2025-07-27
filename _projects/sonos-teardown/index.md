---
layout: post
title: Systems Engineering Project 1
description: "For this project, my team created and constructed a physical arena for the AgileX LIMO mobile robot as part of a robotics systems engineering project. The environment was designed for the LIMO robot to perform tasks such as navigation, path planning, mapping, and localization. Additionally, understanding how the robot interacts with its environment, handling design trade-offs under time and financial constraints, and cooperating as a team were all necessary factors for this project. Hence, the final result would reflect reliable testing of SLAM and obstacle avoidance of the arena.<br><br> <b>Arena Design</b> <br><br> Before the actual implementation of the robot autonomous navigation, the arena had to be created. Our team's arena design was a collaborative and interative process which began with the survey of Changi Airport Terminal 1 to gather perspective of distinct landmarks such as the arrival/departure halls and Kinetic rain. With these references, we created an initial 3D layout on SolidWorks to model the arena layout. After which, our team reviewed and refined our design based on space constraint and material limitations. Key modifications included removing ramps to to simplify the making of the arena and focused on scalable elemnents like walls, flooring and decorative structures. Our team team then sourced materials such as foam board for the flooring and walls, clay for the Kinetic Rain Droplets (practical to build and aestheically accurate) and spray paint for finishing. Through trial aand error and feedbacks, the final arena design managed to capture the essernce of Changi Airport Terminal while also following the technical requirements of AgileX LIMO robot's navigation. <br><br> <b>Implementing System Approach</b> <br> <br> Our team applied Systems Approach from SEBok to guide the designing of the arena and overall the project execution. First off, we began with problem identification which involved identifying constraints like space limitations and material availability. For solution synthesis, we explored possible solutions to mitigate this problem for example, segmenting the arena into modular components(Kinetic Rain, Wall) and allocated tasks based on members expertise. Doing trade-off analysis such as choosing foam over pricier materias and excluding ramps from the arena for feasibility dictated our decisions. Verification was evident in SolidWorks design revision (v1.0 to v1.1) by contrasting it against stakeholders requirements and also validation involved testing the navigation in the physical arena. <br><br> <b>Robot Navigation</b><br><br>
 From the available tools, our team decided to use RTAB-Map navigation over GMapping and Cartographer, as our arena (and others') was more complex and required detailed scanning and mapping of obstacles.

  To implement RTAB-Map with the LIMO robot, we followed a workflow:<br><br>
  <code>roslaunch limo_bringup limo_start.launch</code><br>
  <code>roslaunch dabai_u3.launch</code><br>
  <code>roslaunch limo_rtabmap_orbbec.launch</code><br>
  <code>roslaunch rtabmap_rviz.launch</code><br><br>

One advantage of using RTAB-Map is that it eliminates the need to set the robot’s initial pose manually, as it auto-localizes using an existing map database (<code>~/.ros/rtabmap.db</code>). With this setup, we achieved accurate path planning and reliable obstacle avoidance.<br><br> <b>Post-Mapping and Navigation Process</b><br><br>After creating the 2d map and fine-tuning parameters in RViz. we can transition to testing. Firstly, from the saved map we can generate a 2d grip and 3d map data. Secondly, the robot is switched to localisation mode to navigate the pre-built map without changing it. For the LIMO's drive configuration, we set it to differential mode to allow 4-wheel drive (ensuring proper navigation and obstacle avoidance). In RViz itself, we manually correct the robot pose before sending navigation goal. To send target positions, we use 2D Nav goal to place a waypoint for the robot to reach it desired location."
  


skills: 
  - ROS

main-image: /Limo_pro.png
---






