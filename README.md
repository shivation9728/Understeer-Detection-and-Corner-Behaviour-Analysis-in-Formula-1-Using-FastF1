# Understeer Detection and Corner Behaviour Analysis in Formula 1 using FastF1.
This project analyses **understeer behaviour** in Formula 1 using publicly available telemetry from the FastF1 Python library.It explores how a Formula 1 car behaves through corners by analysing real race telemetry to identify places where the car is struggling to turn — a behaviour known as *understeer*. The result is a visual understanding of how an F1 car handles and why certain corners are more challenging than others.\
For this study, the following race data is used:\
<img width="264" height="67" alt="image" src="https://github.com/user-attachments/assets/d41b9c95-dc90-4348-a4e5-33dd0e869723" />\
Interlagos Circuit:\
<img width="495" height="751" alt="image" src="https://github.com/user-attachments/assets/c4cc844d-5bca-427b-ac76-28d0cd3fb585" />\
Because steering angle and IMU data are not available, understeer is identified using a combination of: 
* Speed profile
* Throttle delay after the apex
* Yaw-rate–based lateral acceleration estiamtion
* Cornering behaviour extracted from X–Y coordinates
* Track-map visualisation of understeer zones

The goal is to understand **where** the car struggles to rotate, **when** the front tyres saturate, and **how** throttle and spped behaviour reflect handling limitations.
## Project Features
  ✔ Speed–Throttle–Brake analysis\
  ✔ Low-speed region detection\
  ✔ Throttle-delay identification\
  ✔ Heading, yaw-rate, and lateral acceleration estimation\
  ✔ Corner segmentation using telemetry\
  ✔ Track heatmap with understeer hotspots\
  ✔ Clean engineering-style visualisations 
  
This workflow helps motorsport data analysts and engineers interpret **cornering behaviour** and **front-axle limitations** using open telemetry.

## Objectives
* Load and clean Formula 1 telemetry using FastF1
* Reconstruct heading (yaw angle) from X–Y coordinates
* Compute yaw rate and estimate lateral acceleration using:\
    <img width="117" height="37" alt="image" src="https://github.com/user-attachments/assets/dfad32d1-f6ee-4d4e-bb89-7efa251fb571" /> 
* Detect understeer zones using:
  * Low-speed thresholds
  * Throttle-delay behaviour
  * Suppressed lateral acceleration
* Visualise:
  * Speed–Throttle–Brake traces
  * Yaw-rate-based lateral acceleration
  * Track map with understeer points
  * Understeer heatmap along the circuit
* Summarise corner-by-corner behaviour

## Methodology 
1. ***Data Acquisition***\
Lap telemetry was obtained using the FastF1 API, including:
* Speed
* Throttle
* Brake
* Car position (X, Y)
* Distance
* Timestamps
The fastest lap of the selected driver was used for analysis.
2. ***Heading (Yaw Angle) Reconstruction***\
Since steering data is unavailable, heading (ψ) was estimated using:
<img width="224" height="58" alt="image" src="https://github.com/user-attachments/assets/e4b33675-80e1-43bf-a291-fa630d39d30e" />\
A Savitzky–Golay filter was applied to smooth heading and reduce noise from X–Y positional jitter.

3. ***Yaw Rate Calculation***\
Yaw rate (turning rate) was obtained by differentiating heading with respect to time: <img width="81" height="49" alt="image" src="https://github.com/user-attachments/assets/e47a06d7-bee9-4969-b6a5-009d888f67b0"/>

4. ***Lateral Acceleration Estimation***\
True IMU lateral-G is not available, so a yaw-rate-based estimate was computed:\
<img width="92" height="26" alt="image" src="https://github.com/user-attachments/assets/762a5084-d58c-4c1c-82a9-6894157958ba" />\
This method is commonly used in motorsport when only GPS or positional data is available.

5. ***Understeer Detection Logic***\
Understeer zones were flagged when:
* Speed < 20th percentile (slow corner apex)
* Throttle < 30% even after speed begins to increase
* Estimated lateral acceleration is suppressed
This combination reflects **front-axle grip limitation** and **rotation difficulty**.

6. ***Visualisation***\
Four main visualisations were produced:
    1. Speed–Throttle–Brake trace with understeer markers
    2. Track map showing understeer locations
    3. Yaw-rate-based lateral acceleration plot
    4. Track heatmap of cornering load + understeer hotspots\
These plots provide both numerical and spatial insight into corner behaviour.

## Tech Stack
| Category | Tools |
|---|---|
| Programming | Python |  
| Data Libraries | pandas, numpy |
| Motorsport Library |	fastF1 |
| Signal Processing | SciPy(Savitzky-Golay) |
| Plotting |	matplotlib, seaborn (optional) |
| Mapping	| fastf1 plotting utilities |

## Author
Shiva Shankaran - Automotive Engineer | Data Analyis | Vehicle Dynamics
