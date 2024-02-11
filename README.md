# TasmotaWaterMeter

I have chosen to utilize a fluid flow sensor for monitoring water consumption through ESP and Tasmota.

<img src="https://github.com/XHunter74/TasmotaWaterMeter/assets/8713959/fc14041e-acdd-4a08-a7b2-2f5931868207" width=400/>

Many developers employ a script that tallies pulses, and based on the pulse count, calculates water consumption. However, a common challenge arises as the sensor exhibits nonlinear characteristics, causing the number of pulses per liter to be heavily influenced by water flow. Consequently, developers use varying coefficients depending on the pulse count to derive the flow rate in liters.

In an effort to address this issue, I delved into understanding this sensor. According to information from the manufacturer, the signal frequency (F) is correlated with the instantaneous flow rate (Q) as follows: F(Hz)=6.6×Q(liters/ minute). However, there is no direct measure of total water consumption. The sensor solely gauges instantaneous water flow. The instantaneous water flow per minute is Q=F/6.6, and per second, Q=F/6.6/60. To obtain the total water flow, we need to integrate (sum up) the instantaneous water flow for each second. You can find the script for this process in the FlowMeter-script.txt file.

For the ESP, it is crucial to use firmware that supports scripts. Detailed instructions on how to achieve this can be found on the official page: Tasmota Documentation.
