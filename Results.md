# Results
This section presents the key results from the telemetry analysis of Max Verstappen's fastest lap at the Sao Paulo Grand Prix(2025), focusing on understeer detection and cornering behaviour. The analysis highlights how telemetry can be used to quantify and visually identify challenging sections of the circuit for vehicle dynamics.
## 1. Speed, Throttle, and Brake profiles
<img width="1496" height="796" alt="image" src="https://github.com/user-attachments/assets/b5358d9a-a023-491e-a4d4-5a688f94f227" />
The first visualisation shows how the driver manages speed, throttle input, and braking throughout the lap:

* **Speed Profile:**\
Highlights low-speed sections, where mechanical grip is most critical and understeer is more likely to appear. Noticeable dips correspond to the slow and medium-speed corners at Interlagos.
* **Throttle Application:**
Highlights zones where the driver delays throttle pick-up after the apex. These late *throttle zones* often indicate that the car did not rotate sufficiently during cornering, a classic symptom of understeer.
* **Brake Application:**
Shows heavy braking moments, which are crucial for analysing entry-phase understeer. Sharp braking followed by long coasting or delayed throttle often indicates balance limitations.

These three profiles together offer a comprehensive view of how the car moves through corner entry, mid-corner rotation, and corner exit. 
## 2. Estimated Lateral Acceleration & Understeer Detection
<img width="879" height="419" alt="image" src="https://github.com/user-attachments/assets/f79e7d4c-11f9-419c-8975-9c1abbc4ae5e" />\
The second plot uses a simple estimation of lateral acceleration (LatAcc) derived from speed and curvature of the racing line.

Key insights:
* Understeer zones (red points) appear where lateral acceleration drops unexpectedly while steering demand remains high, indicating that the front axle is losing grip.
* These events consistently occur in slow and medium-speed corners, matching the patterns seen in the throttle and speed profile.
* Sharp negative spikes correspond to moments where the car transitions abruptly or experiences rapid direction changes.

## 3. Track Maps with Understeer Hotspots
<img width="1172" height="759" alt="image" src="https://github.com/user-attachments/assets/ab4cb738-f16c-4879-a80b-35535a334dc2" />
The final visualization maps the telemetry data back onto the Interlagos circuit.

**Left – Track Path with Low-Speed & Understeer Zones**
* Shows the trajectory of the lap.
* Understeer zones (red points) align with braking zones and apexes.
  
**Right – Heatmap of Lateral Acceleration with Understeer Overlay**
* Points are color-coded by lateral acceleration intensity.
* High lateral loads occur in sweeping, high-speed sections.
* Understeer zones occur predominantly in lower-load, slower corners, consistent with car balance limitations rather than driver error.

This spatial visualisation allows easy identification of exact corners where the car struggled the most.
# Conculsion
This analysis demonstrates that telemetry data from FastF1 can effectively identify understeer zones and challenging corners on the Interlagos circuit. By combining speed, throttle, brake, and estimated lateral acceleration profiles, clear patterns of understeer emerge—especially in slower corners with delayed acceleration. These insights are valuable for optimizing car setup, improving driver technique, and understanding vehicle dynamics in Formula 1
