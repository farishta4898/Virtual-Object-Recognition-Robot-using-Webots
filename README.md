# Virtual-Object-Recognition-Robot-using-Webots

<center><img src="https://www.theconstructsim.com/wp-content/uploads/2015/10/webots-1-300x300.png" height="60px" width="60px"></center>

<ul>
<li>Project Name: Object Recognition Robot </li>
<li>Project Type: Theoretical/Virtual </li>
<li>Software: Webots </li>
<li>Controller Code Language: C++ </li>
<li>Project Video Link: <a href="https://www.youtube.com/watch?v=UzMLEb9Cm9w">Click Here</a></li>
<li>Project Contributors: <a href="https://github.com/AlphaDog707">Arman Hossain, </a><a href="https://github.com/farishta4898">Farishta Kabir, </a><a href="https://github.com/sameha23">Sameha Kamrul</a></li>
</ul>


<h4>‣ Virtual Robot Body Building: </h4>
For creating the robot we had to choose the robot node from the base nodes. After
that, we went to the children under the Robot section and then choose the shape, from the base
node and add it. For the geometry, we chose a box shape for our body part. Then we
resized the robot, by choosing the coordinates values of x, y, z. Then named the
shape accordingly. Then we choose PVR appearance and the colour. Here we have chosen a royal blue color for the robot body. Then set the
metalness is 5. After that, we went to the bounding object and then used the body
shape. After that, we added the physics. <br> <br> 
Now that the body is completed and for the wheels we went to the children again and added a node then select a hinge joint. The device was selected and a rotational motor was chosen for each robot wheel. After that we applied the solid property. Then again went children and choose the shape and in the shape, appearance was added as before. For the wheel, we choose brick red. And for the geometry a cylindrical shape
was chosen, the height and radius was changed. Then we rotated
the position of the wheel by x, y, and z coordinate and also change the value of rotation and
scale, now as of the one wheels is ready the same procedure is followed for the rest 3 and the translation points are set accoridngly. <br><br> 
Then we added two distance sensors to the robot, for this we needed to go to the basic nodes then
again to the shape after that to the children then appearance and selected the appearance then the
geometry (box shape) then changed the size of the x, y and z coordinates. Then we
applied optional rendering to check if the x-axis is set properly and make the distance sensors
operate. <br> <br> 
Then lastly, we have set up a camera from the base nodes section in the children node of the
robot body in the same way we created the distance sensor. In this case, we selected the white
color and spherical shape instead to put on the front. <br>
Thus our virtual body is created for further simulation. <br> <br> <br> 

<h4>‣ Controller Code: </h4>
Here comes the controller part of our robot. The controller code was implemented in
C++. Initially, we imported all the necessary header files then we defined the time step which
64ms. <br><br> 
After defining the robot and distance sensor pointer, we instructed the sensors to take input after
every time step. Then, we enabled camera and camera recognition.
Furthermore, we made a char array to make a list of the wheel names of the robot and assigned
initial velocity. <br><br> 
For making the robot moving and avoiding obstacles, we made this while loop and gave the
motor some speed to get moving. We also created an obstacle-avoiding flag that tells the robot
to rotate when it senses some obstacles.<br> <br>
<b>Code link: <a href="https://github.com/farishta4898/Virtual-Object-Recognition-Robot-using-Webots/blob/main/object_detection.cpp">Click Here</a></b> <br> <br><br>

<h4>‣ Mechanism and Simulation:</h4>
Now that we are done with the robot body-building and controller code part let’s jump onto the
simulation and mechanism part. First of all, we need to understand which components are
responsible for making the object recognition system work. <br> <br> 
At first, we have the distance sensors set in front of the robot. The distance sensors work
according to the x-axis of their placement. They measure the distance in terms of the x-axis and
we have placed these in such a way so that it covers most of the front and side areas of the robot.
So that it can detect the presence of any obstacle or object right away whenever anything appears
in front of the robot. Basically, these work like the eyes for the robot. As we have implemented
the optional rendering too we can observe there are two rays that are coming from the distance
sensors according to their x-axes respectively. <br><br> 
Then, we have the camera module that works like a visual capturing device for the robot and
represents whatever is within its field of view within a virtual window. The camera width and
height are set to 640 pixels each for better clarity. We have enabled the recognition feature within
the camera node for our system to recognize objects of any size and shape and have set the color
to red, the field of view to 2, and frame thickness to 3 respectively.
There are plenty of objects of different sizes and shapes (eg. soccer ball - spherical, soda can -
cylindrical, barrels - cylindrical) are placed all around the square arena. Now we can start the
simulation. <br> <br> 
As, if we observe we will see that the camera is being able to capture whatever is within its field
of view and recognizing all of the objects. The red rectangular frames around the objects are
proof that the recognition part is working properly. The field of view was initially set to 2 and if
we change the field of view to 1 or 3 the range will decrease or increase accordingly and in all
the circumstances the robot can recognize the random objects. <br> <br> 
On the other hand, whenever the robot is approaching any object/obstacle like a soda can, soccer
ball, or even arena wall the distance sensors instantly measures the distance between the robot
body and the obstacle and detect the presence. Then it immediately changes its path and rotates
using the rotational motos of the wheels. This mechanism proofs that the distance sensors are
also working properly in terms of detecting the physical presence of any object/obstacle
approaching the robot.

<h5>Reference: https://cyberbotics.com/doc/guide/index </h5>
