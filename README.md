# EE 157 Motor and Drives

## 1000 kV Motor


## Part 1: Resistance measurements

### 1a. Angular Velocity

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

## Part 2: Determining the back EMF constant 

### 2a. Back EMF constant 

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

### 2b. Back EMF Voltage


<img width="172" alt="Screen Shot 2022-04-20 at 8 03 14 PM" src="https://user-images.githubusercontent.com/71578472/164363404-6062548d-7bff-4e94-93a3-b4d40b6ab98a.png">

Vemf = Vline-to-line - IRline-to-line = (sqrt(3) * 0.9V) - (20.1mA * 0.32 ohms) = 1.559 V

## Part 3: Km

Now that we have Kb (and can deduce Kt), we found the motor constant, Km, using the resistance we measured.

for a 3-phase motor:

k_T = sqrt(3) * k_b = sqrt(3) * 0.00729 = 0.0126 

k_m = Tavg / sqrt(Ploss) = (k_T* i_rms) / sqrt(i_rms^2 * Rcoil = k_T / sqrt(Rcoil) = 0.0126 / sqrt(0.32 ohms) = 0.0223 Nm/ sqrt(w) 


## Part 4 Characterizing drag torque (hysteresis and eddy current)

<img width="135" alt="Screen Shot 2022-04-21 at 12 51 17 AM" src="https://user-images.githubusercontent.com/71578472/164406364-04889d11-aaad-4980-ad71-8d5f8e8b1321.png">


<img width="371" alt="Screen Shot 2022-04-21 at 12 52 57 AM" src="https://user-images.githubusercontent.com/71578472/164406698-1f8601a4-7ada-4228-8430-741de62b73be.png">


![IMG_0110](https://user-images.githubusercontent.com/71578472/164612596-7488cfac-67b7-4b1a-9851-4c81a74bae73.jpeg)




## 1400 kV Motor

## Part 1: Resistance measurements

### 1a. Angular Velocity

We correlated electrical frequency to angular velocity by counting the number of poles in the stator. For the motors we used, the number of poles was equal to the number magnets.  

<img width="170" alt="Screen Shot 2022-04-20 at 4 16 52 PM" src="https://user-images.githubusercontent.com/71578472/164339934-72ad934d-b84c-4b9c-b290-884faa75513a.png">

np = 14

f = 592.78 Hz

w [rad/sec] = (pi)(592.78 Hz) / 14 = 133.02 rad/sec

### 1b. Line-to-line coil resistance

resistance of the leads = 0.1 ohms 


resistance of an individual phase winding = 0.3 ohms 


measured resistance of 1 phase winding - resistance of the leads =  0.3 ohms  - 0.1 ohms  = 0.2 ohms 

Measured line-to-line coil resistance =  2x the resistance of an individual phase winding = 0.2 ohms * 2  = 0.4 ohms

## Part 2: Determining the back EMF constant 

### 2a. Back EMF constant 

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

### 2b. Back EMF Voltage


<img width="172" alt="Screen Shot 2022-04-20 at 8 03 14 PM" src="https://user-images.githubusercontent.com/71578472/164363404-6062548d-7bff-4e94-93a3-b4d40b6ab98a.png">

Vemf = Vline-to-line - IRline-to-line = (sqrt(3) * 0.6V) - (307.2 mA * 0.4 ohms) = 0.916 V

## Part 3: Km

Now that we have Kb (and can deduce Kt), we found the motor constant, Km, using the resistance we measured.

for a 3-phase motor:

k_T = sqrt(3) * k_b = sqrt(3) * 0.0055 = 0.0095

k_m = Tavg / sqrt(Ploss) = (k_T* i_rms) / sqrt(i_rms^2 * Rcoil = k_T / sqrt(Rcoil) = 0.0095 / sqrt(0.4 ohms) = 0.0150 Nm/ sqrt(w) 


## Part 4 Characterizing drag torque (hysteresis and eddy current)

<img width="135" alt="Screen Shot 2022-04-21 at 12 51 17 AM" src="https://user-images.githubusercontent.com/71578472/164406364-04889d11-aaad-4980-ad71-8d5f8e8b1321.png">



<img width="380" alt="Screen Shot 2022-04-21 at 12 56 32 AM" src="https://user-images.githubusercontent.com/71578472/164407419-9d93b01a-83f0-43bd-9bf9-8210a4bcdc4c.png">









