# Understeer-Detection-and-Corner-Behaviour-Analysis-in-Formula-1-Using-FastF1
Detecting understeer in Formula 1 using speed, throttle &amp; yaw-rate telemetry.
This project analyzes understeer behaviour in Formula 1 using publicly available telemetry from the FastF1 Python library.
With no access to steering angle or IMU sensors, understeer is identified through:
Speed profile
Throttle delay
Yaw-rate–based lateral acceleration
Cornering behaviour extracted from X–Y coordinates
Track-map visualisation of understeer zones
The goal is to understand where the car struggles to rotate, when the front tyres saturate, and how driver inputs reflect handling limitations.
