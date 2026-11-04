<h1>Line Follower and Obstacle Avoidance Robot</h1>

Arduino-based autonomous robotic system integrating infrared line tracking, ultrasonic obstacle detection via a servo-mounted sweep, and H-bridge motor control.

<h2>Design</h2>
<img width="802" height="425" alt="image" src="https://github.com/user-attachments/assets/122709a4-7ec2-47b4-80b3-a9c48cc47b17" />

<h2>Explanation</h2>

<h3>Overview</h3>
<p>
This project implements an autonomous Line Follower Robot (LFR) equipped with real-time obstacle avoidance capabilities. The system utilizes infrared sensors to track path lines and an HC-SR04 ultrasonic sensor mounted on a micro servo motor to scan for and maneuver around obstacles in its path.
</p>

<h3>Components Used</h3>
<ul>
  <li><b>Arduino Uno Microcontroller:</b> Core processing board utilizing the ATmega328P microcontroller to coordinate sensor inputs and motor control logic.</li>
  <li><b>H-Bridge Motor Driver (L298N):</b> Controls the speed and directional rotation of the four DC geared motors.</li>
  <li><b>Infrared (IR) Sensors:</b> Positioned downward at the front to detect surface contrast between the black line and white background.</li>
  <li><b>Ultrasonic Sensor (HC-SR04) & Servo Motor:</b> Measures frontal distance via ultrasonic pulses; mounted on a TowerPro 9g micro servo to sweep and inspect side clearances when an obstacle is detected.</li>
  <li><b>Power & Chassis:</b> Powered by a 9V battery pack supplying a 4-wheel robotic chassis platform.</li>
</ul>

<h3>Control Logic & Operation</h3>
<ul>
  <li><b>Line Tracking:</b> When both IR sensors detect white space, the robot moves forward. If the left or right IR sensor encounters the black line, the robot corrects its trajectory by turning left or right respectively.</li>
  <li><b>Obstacle Avoidance:</b> When the ultrasonic sensor detects an obstacle within the threshold distance, the robot stops, uses the servo motor to scan left and right distances, compares clearance, and executes a bypass routine before returning to the line.</li>
</ul>

<h3>Circuit Wiring & Pinout Summary</h3>
<ul>
  <li><b>Motor Driver Pins:</b> Connected to digital pins 5 through 10 (`enA`, `in1`, `in2`, `in3`, `in4`, `enB`).</li>
  <li><b>Sensor Pins:</b> IR sensors connected to analog pins `A0` (Right) and `A1` (Left); Ultrasonic Echo and Trigger connected to `A2` and `A3`; Servo control connected to pin `A5`.</li>
</ul>
