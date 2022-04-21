# EE 157 Motor and Drives

## Part 1: Resistance measurements

### 1a. Determine how to correlate electrical frequency to angular velocity.To do this we count number of poles in the stator. For the motors we will be using, the number of poles will equal the number magnets.  

<img width="170" alt="Screen Shot 2022-04-20 at 4 16 52 PM" src="https://user-images.githubusercontent.com/71578472/164339934-72ad934d-b84c-4b9c-b290-884faa75513a.png">

np = 14

f = 673.93 Hz

w [rad/sec] = (pi)(673.93 Hz) / 14 = 151.23 rad/sec

### 1b. Measure line-to-line coil resistance

resistance of the leads = 0.1 ohms 


resistance of an individual phase winding = 0.26 ohms 


measured resistance of 1 phase winding - resistance of the leads =  0.26 ohms  - 0.1 ohms  = 0.16 ohms 

Measured line-to-line coil resistance =  2x the resistance of an individual phase winding = 0.16 ohms * 2  = 0.32 ohms

## Part 2: Determining the back EMF constant 

### 2a. Back EMF constant 

We measured the back EMF by spinning up the motor under power, and then cutting off the power to the ESC (the motor drive component) and then quickly capturing the back EMF as the motor spun down with the ESC off. 

Meaaure values using scope:

Vpeak-to-peak = 1.8 V (amplitude)

I = 20.1mA

Vphase = Vpeak = 0.9V

Vline-to-line = rad3 * Vphase

Vline-to-line,rms = rad3/2 * Vphase

Vline-to-line,rms = 1.102 COME BACK

<img width="153" alt="Screen Shot 2022-04-20 at 7 35 26 PM" src="https://user-images.githubusercontent.com/71578472/164360349-870272a1-09a6-45bb-8c0a-055328aab3d6.png">

Kb = Vline-to-line,rms/omega = 1.102 / 151.23 rad/sec = 0.00729 














