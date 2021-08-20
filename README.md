# Virtual-Object-Recognition-Robot-using-Webots

<ul>
<li>Project Name: Object Recognition Robot <h4>
<li>Project Type: Theoretical/Virtual <li>
<li>Software: Webots <li>
<li>Controller Code Language: C++ <li>
<li>Project Video Link: </li>
</ul>


<h4>Virtual Robot Body Building: </h4>
For creating a Robot we need to choose Robot from the base node, then we have to add it. After
that, we have to go to the children under the Robot and then choose the shape, from the base
node and we have to add it. Then we need to choose PVR appearance and then we need to
choose, here I am choosing a royal blue color for the Robot. Then we need to make sure that the
metalness is 5. For the geometry, we need to choose a box shape for our body parts. Then we
need to resize the robot, by choosing the coordinates values of x, y, z. Then we have to name the
shape as the body. After that, we need to go to the bounding object and then use, then body
shape. After that, we need to go to the physics and add the physics. <br> 
Now the body is completed and for the wheels we need to go to the children again and we have
to go to the add a node then select a hinge joint then go to joint perimeter and then select hinge
joint. Then we need to go to the device and choose a rotational motor for the robot wheel then we
have to choose solid. Then again go to the children and choose the shape and in the shape, we
have to add appearance as before. For the wheel, we are choosing brick red. And geometry
would be a cylindrical shape, we need to change the height and radius. Then we need to rotate
the position of the wheel by x, y, and z coordinate and also change the value of rotation and
scale, now our one wheel is ready next we need to do the same for the rest of the wheels.
Now we need to add a distance sensor to the robot, for this we need to go to the basic nodes then
again to the shape after that to the children then appearance and select the appearance than the
geometry which will be the box, then changing the size of the x, y and z coordinates. Then we
applied optional rendering to check if the x-axis is set properly and make the distance sensors
operate. <br> 
Then lastly, we have set up a camera from the base nodes section in the children node of the
robot body in the same way we created the distance sensor. In this case, we selected the white
color and spherical shape instead to put on the front. <br>
Thus our virtual body is created for further simulation. <br> <br>

<h4>Controller Code: </h4>
Now I'm going to explain the controller part of our robot. Here we can see the controller code in
C++. Initially, we imported all the necessary header files then we defined the time step which
64ms. <br>
After defining the robot and distance sensor pointer, we instructed the sensors to take input after
every time step. Then, we enabled camera and camera recognition.
Furthermore, we made a char array to make a list of the wheel names of the robot and assigned
initial velocity. <br>
For making the robot moving and avoiding obstacles, we made this while loop and gave the
motor some speed to get moving. We also created an obstacle-avoiding flag that tells the robot
to rotate when it senses some obstacles. <br> <br>

<h4>Mechanism and Simulation:</h4>
Now that we are done with the robot body-building and controller code part let’s jump onto the
simulation and mechanism part. First of all, we need to understand which components are
responsible for making the object recognition system work. <br> 
At first, we have the distance sensors set in front of the robot. The distance sensors work
according to the x-axis of their placement. They measure the distance in terms of the x-axis and
we have placed these in such a way so that it covers most of the front and side areas of the robot.
So that it can detect the presence of any obstacle or object right away whenever anything appears
in front of the robot. Basically, these work like the eyes for the robot. As we have implemented
the optional rendering too we can observe there are two rays that are coming from the distance
sensors according to their x-axes respectively. <br>
Then, we have the camera module that works like a visual capturing device for the robot and
represents whatever is within its field of view within a virtual window. The camera width and
height are set to 640 pixels each for better clarity. We have enabled the recognition feature within
the camera node for our system to recognize objects of any size and shape and have set the color
to red, the field of view to 2, and frame thickness to 3 respectively.
There are plenty of objects of different sizes and shapes (eg. soccer ball - spherical, soda can -
cylindrical, barrels - cylindrical) are placed all around the square arena. Now we can start the
simulation. <br> 
As, if we observe we will see that the camera is being able to capture whatever is within its field
of view and recognizing all of the objects. The red rectangular frames around the objects are
proof that the recognition part is working properly. The field of view was initially set to 2 and if
we change the field of view to 1 or 3 the range will decrease or increase accordingly and in all
the circumstances the robot can recognize the random objects. <br> 
On the other hand, whenever the robot is approaching any object/obstacle like a soda can, soccer
ball, or even arena wall the distance sensors instantly measures the distance between the robot
body and the obstacle and detect the presence. Then it immediately changes its path and rotates
using the rotational motos of the wheels. This mechanism proofs that the distance sensors are
also working properly in terms of detecting the physical presence of any object/obstacle
approaching the robot.
