<h3>Introduction</h3>
This repository holds the code (and previously used test code) for the functioning of the transfer system, or just the step motor rail. 

<h3>api_step_motor.py</h3>
The system is setup in such a way where the majority of the fucntional code is in api_step_motor, which creates a UI through flask (and handles subsequent interactions with said UI) that the user can input commands to. 

<h3>A4988.py</h3>
In order for the stepper motor to connect to the Raspberry Pi 4 it is necessary to utilize a A4988 controller, and the python file of the same name holds all the function definitions utilized in api_step_motor.py and the microswitches, and handles the connection between the Raspberry Pi 4 and the stepper motor on the rail.

<h3>Setup (Skip if setup already running)</h3>
The first step is to get start the flask and redis server, the redis server handling multiple calls at the same time to allow asynchronous running of the code. 
<br><br>
1. Activate the Virtual Environment
  
  * Navigate to the location of the code and activate the virtual environment:
    * cd /home/git/transfer_station
    * source foobar/bin/activate

2. In another terminal, start the redis server<br>

  * redis-server

3. Finally run the code through flask and open the link (first one is on local machine, second is on different machine on the same network

  * flask --app api_step_motor run --host=0.0.0.0
