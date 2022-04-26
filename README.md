# EE 157 Motor and Drives

## Introduction 

In this lab, we reviewed 3-phase systems and experimentally determined basic motor constants (Kb, K𝜏, etc.). We then calculated eddy current losses and hystersis loss. 

### Materials 

1. Current probe 
2. Voltage and current scope 
3. ESC
4. 1000 kV motor 
5. 14000 kV motor
6. Multimeter 
7. Power Supply

## Procedure 

For the set up, the input of the ESC was connected to a 5V power supply. The output of the ESC was connected to a hobby motor. The hobby motor was taped down so that it could spin in a stable manner. 

The contact resistance of the multimeter was measured and recorded. The coil resistance of the motor was measured across two terminals and was later used to calculate the line-to-line resistance.  

The current probe was connected to one wire of the hobby motor, the positive and ground voltage were then connected to the terminals of the other two wires of the motor. The ESC was turned on and then quickly turned off to measure the current, voltage frequency, and amplitutude as the motor slowed down. These measurements were then used to calculate the back EMF and motor constants. 

We then recorded waveforms at different speeds. We turned the ESC back on at different speeds and recorded at least one period of the voltage and current. These measurements were later used to calculate losses due to hysteresis drag and eddy current drag and the relationship between torque and angular velocity. 

The process above was then repeated for the 1400 kV motor. 



## Results 

### 1000 kV Motor

#### Part 1: Resistance measurements

##### 1a. Angular Velocity

We correlated electrical frequency to angular velocity by counting the number of poles in the stator. For the motors we used, the number of poles was equal to the number magnets.  

<img width="170" alt="Screen Shot 2022-04-20 at 4 16 52 PM" src="https://user-images.githubusercontent.com/71578472/164339934-72ad934d-b84c-4b9c-b290-884faa75513a.png">

np = 14

f = 673.93 Hz

w [rad/sec] = (pi)(673.93 Hz) / 14 = 151.23 rad/sec

### 1b. Line-to-line coil resistance

resistance of the leads = 0.1 ohms 


resistance of an individual phase winding = 0.26 ohms 


measured resistance of 1 phase winding - resistance of the leads =  0.26 ohms  - 0.1 ohms  = 0.16 ohms 

Measured line-to-line coil resistance =  2x the resistance of an individual phase winding = 0.16 ohms * 2  = 0.32 ohms

#### Part 2: Determining the back EMF constant 

##### 2a. Back EMF constant 

We measured the back EMF by spinning up the motor under power, and then cutting off the power to the ESC (the motor drive component) and then quickly capturing the back EMF as the motor spun down with the ESC off. 


![IMG_2102](https://user-images.githubusercontent.com/71578472/164606303-4c5eb612-d552-4ecc-8643-792ce59b5b27.jpeg)


Meaaure values using scope:

Vpeak-to-peak = 1.8 V (amplitude)

I = 20.1mA

Vphase = Vpeak = 0.9V

Vline-to-line = sqrt(3) * Vphase

Vline-to-line,rms = sqrt(3/2) * Vphase

Vline-to-line,rms = 1.102 

<img width="153" alt="Screen Shot 2022-04-20 at 7 35 26 PM" src="https://user-images.githubusercontent.com/71578472/164360349-870272a1-09a6-45bb-8c0a-055328aab3d6.png">

Kb = Vline-to-line,rms/omega = 1.102 / 151.23 rad/sec = 0.00729 

##### 2b. Back EMF Voltage


<img width="172" alt="Screen Shot 2022-04-20 at 8 03 14 PM" src="https://user-images.githubusercontent.com/71578472/164363404-6062548d-7bff-4e94-93a3-b4d40b6ab98a.png">

Vemf = Vline-to-line - IRline-to-line = (sqrt(3) * 0.9V) - (20.1mA * 0.32 ohms) = 1.559 V

#### Part 3: Km

Now that we have Kb (and can deduce Kt), we found the motor constant, Km, using the resistance we measured.

for a 3-phase motor:

k_T = sqrt(3) * k_b = sqrt(3) * 0.00729 = 0.0126 

k_m = Tavg / sqrt(Ploss) = (k_T* i_rms) / sqrt(i_rms^2 * Rcoil = k_T / sqrt(Rcoil) = 0.0126 / sqrt(0.32 ohms) = 0.0223 Nm/ sqrt(w) 


#### Part 4 Characterizing drag torque (hysteresis and eddy current)

<img width="135" alt="Screen Shot 2022-04-21 at 12 51 17 AM" src="https://user-images.githubusercontent.com/71578472/164406364-04889d11-aaad-4980-ad71-8d5f8e8b1321.png">


![Open lab2](https://user-images.githubusercontent.com/71578472/165274512-b5d3c7e6-e2de-4d61-984c-10d85d18af0f.jpeg)



We fitted an ideal EMF curve for one cycle of Vphase when the angular velocity was equal to 1428.57 rad/sec. 

We used Kb to plot the ideal EMF curve over one cycle of the measured phase-to-phase voltage given the equation Vphase = Kb,phaseline-to-neutralwsin(Np/2wt). 

Since, dlambda/dtheta = Vphase/w = Kb,phaseline-to-neutralwsin(Np/2wt +/- pi/6), there's a phase shift of +/- pi/6 because this is a 3-phase motor. The current was multiplied by dlambda/dtheta in order to obtain the instantaneous torque. To calculate Tavg, we averaged the instantaneous torque and multiplied by three. We repeated the process to show that eddy current and hystersis drag torque increases in an approximate linear manner with respect to angular velocity. 



![Screenshot 2022-04-26 at 2 39 08 AM](https://user-images.githubusercontent.com/71578472/165271229-6ad1a0e3-11fc-494a-b4f0-c8bf819a3439.jpeg)

For an angular velocity of 1121.857 rad/s, there was 0.0006745 Nm of torque calculated. For an angular velocity of 1428.571 rad/s, there was 0.001277 Nm of torque calculated. For an angular velocity of 1714.285 rad/s, there was 0.001582 Nm of torque calculated.



### 1400 kV Motor

#### Part 1: Resistance measurements

##### 1a. Angular Velocity

We correlated electrical frequency to angular velocity by counting the number of poles in the stator. For the motors we used, the number of poles was equal to the number magnets.  

<img width="170" alt="Screen Shot 2022-04-20 at 4 16 52 PM" src="https://user-images.githubusercontent.com/71578472/164339934-72ad934d-b84c-4b9c-b290-884faa75513a.png">

np = 14

f = 592.78 Hz

w [rad/sec] = (pi)(592.78 Hz) / 14 = 133.02 rad/sec

##### 1b. Line-to-line coil resistance

resistance of the leads = 0.1 ohms 


resistance of an individual phase winding = 0.3 ohms 


measured resistance of 1 phase winding - resistance of the leads =  0.3 ohms  - 0.1 ohms  = 0.2 ohms 

Measured line-to-line coil resistance =  2x the resistance of an individual phase winding = 0.2 ohms * 2  = 0.4 ohms

#### Part 2: Determining the back EMF constant 

##### 2a. Back EMF constant 

We measured the back EMF by spinning up the motor under power, and then cutting off the power to the ESC (the motor drive component) and then quickly capturing the back EMF as the motor spun down with the ESC off. 

Meaaure values using scope:

Vpeak-to-peak = 1.2 V (amplitude)

I = 307.2 mA

Vphase = Vpeak = 0.6 V

Vline-to-line = sqrt(3) * Vphase

Vline-to-line,rms = sqrt(3/2) * Vphase

Vline-to-line,rms = 0.735 V 

<img width="153" alt="Screen Shot 2022-04-20 at 7 35 26 PM" src="https://user-images.githubusercontent.com/71578472/164360349-870272a1-09a6-45bb-8c0a-055328aab3d6.png">

Kb = Vline-to-line,rms/omega = 0.735 V / 133.02 rad/sec = 0.0055

##### 2b. Back EMF Voltage


<img width="172" alt="Screen Shot 2022-04-20 at 8 03 14 PM" src="https://user-images.githubusercontent.com/71578472/164363404-6062548d-7bff-4e94-93a3-b4d40b6ab98a.png">

Vemf = Vline-to-line - IRline-to-line = (sqrt(3) * 0.6V) - (307.2 mA * 0.4 ohms) = 0.916 V

#### Part 3: Km

Now that we have Kb (and can deduce Kt), we found the motor constant, Km, using the resistance we measured.

for a 3-phase motor:

k_T = sqrt(3) * k_b = sqrt(3) * 0.0055 = 0.0095

k_m = Tavg / sqrt(Ploss) = (k_T* i_rms) / sqrt(i_rms^2 * Rcoil = k_T / sqrt(Rcoil) = 0.0095 / sqrt(0.4 ohms) = 0.0150 Nm/ sqrt(w) 


#### Part 4 Characterizing drag torque (hysteresis and eddy current)

<img width="135" alt="Screen Shot 2022-04-21 at 12 51 17 AM" src="https://user-images.githubusercontent.com/71578472/164406364-04889d11-aaad-4980-ad71-8d5f8e8b1321.png">

![Open lab2-1](https://user-images.githubusercontent.com/71578472/165275280-7f73b69c-bcd4-4552-9799-c7d99dd4e4c7.jpeg)



We fitted an ideal EMF curve for one cycle of Vphase when the angular velocity was equal to 385.71 rad/sec. 

We used Kb to plot the ideal EMF curve over one cycle of the measured phase-to-phase voltage given the equation Vphase = Kb,phaseline-to-neutralwsin(Np/2wt). 

Since, dlambda/dtheta = Vphase/w = Kb,phaseline-to-neutralwsin(Np/2wt +/- pi/6), there's a phase shift of +/- pi/6 because this is a 3-phase motor. The current was multiplied by dlambda/dtheta in order to obtain the instantaneous torque. To calculate Tavg, we averaged the instantaneous torque and multiplied by three. We repeated the process to show that eddy current and hystersis drag torque increases in an approximate linear manner with respect to angular velocity. 

![Open lab2-3](https://user-images.githubusercontent.com/71578472/165275326-eb930da1-9bdf-4202-9974-c8fab7b45fd8.jpeg)



For an angular velocity of 385.714 rad/s, there was 0.003828 Nm of torque calculated. For an angular velocity of 964.285 rad/s, there was 0.004127 Nm of torque calculated. For an angular velocity of 1257.142 rad/s, there was 0.006189 Nm of torque calculated.


## Conclusion 

In conclusion, we learned how to measure important values of a motor without a datasheet. This can prove to be useful when it comes to our project that involves building a Halback motor. 





