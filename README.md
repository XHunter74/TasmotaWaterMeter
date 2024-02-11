# TasmotaWaterMeter

Decided to use the next fluid flow sensor to measure water consumption using ESP and Tasmota. 

![image](https://github.com/XHunter74/TasmotaWaterMeter/assets/8713959/fc14041e-acdd-4a08-a7b2-2f5931868207)
  
Everyone uses a script that counts pulses and, 
depending on the number of pulses, water consumption is calculated. 
Each of the script developers complains that the sensor has nonlinear characteristics and that the number of pulses per liter is very 
dependent on water consumption. For this reason, developers, depending on the number of pulses, use one or another coefficient 
to obtain the flow rate in liters.
  
I decided to deal with this sensor. According to information from the manufacturer, 
the signal frequency F depends on the instantaneous flow rate Q as follows: F (Hz) = 6.6 * Q(litr/min). 
The question is, where is the total water consumption? But he’s simply not here! 
The sensor measures only instantaneous water flow and nothing else. The instantaneous water flow per minute is Q = F/6.6, then per second Q = F/6.6/60. 
To get the total water flow, we must integrate (sum up) the instantaneous water flow for each second. 
The script can be found in the FlowMeter-script.txt file. 

The ESP must use firmware with script support. 
You can find how to do this on the official page https://tasmota.github.io/docs/.
