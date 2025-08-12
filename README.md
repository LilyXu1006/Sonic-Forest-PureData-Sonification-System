# Sonic Forest: Pure Data Sonification System

## 📖 Project Overview
**Sonic Forest** is a real-time climate data sonification system implemented in Pure Data (Pd).  
It translates forest microclimate sensor data into musical parameters, enabling the public to perceive climate change and diurnal forest rhythms through sound.  
The system maps multiple environmental variables into pitch, rhythm, timbre, reverb, and modulation effects, producing perceptually distinct soundscapes under different times of day and extreme weather conditions.

---

## 🌍 Data Source
The environmental dataset originates from the **Sensing the Forest** project, collected at the **Alice Holt Forest, UK**.  
Measurements are acquired via a **customised Campbell Scientific CR350 data logger**, which records the following variables in JSON format:  
- Air Temperature (Avg, Max, Min)  
- Relative Humidity (RH)  
- Photosynthetically Active Radiation (PAR)  
- Net Radiation (NR)  
- Carbon Dioxide (CO₂, Avg, Max, Min)  
- Wind Speed (WS, Avg, Max)  

These data files can be loaded directly or streamed in real time to Pd via OSC.

---

## 🎵 Data-to-Sound Mapping

| Variable                         | Pd Parameter           | Perceptual Effect                | 
|----------------------------------|------------------------|----------------------------------|
| Air Temperature                  | Background root pitch  | Controls tonal register          |
| Relative Humidity (RH)           | Reverb wet/dry mix     | Controls spatial brightness      |
| CO₂ Average                      | Scale & harmonic mode  | Affects harmonic stability       |
| CO₂ Max–Min Range                | Pitch offset range     | Melodic tension indicator        |
| PAR                              | Tempo                  | Controls rhythmic activity       |
| Net Radiation (NR)               | Vibrato depth          | Adds shimmering texture          |
| Wind Speed Avg                   | EQ Q factor            | Enhances low-frequency resonance |
| Wind Speed Max                   | EQ centre frequency    | Alters background masking effect |

---

## 🖥 How to Use
1. Install **Pure Data (Pd)**, version **0.52** or higher.
2. Clone or download this repository:  
   ```bash
   git clone https://github.com/LilyXu1006/SonicForest_PureData.git
3. **Install the StF Data Logger abstraction**  
   - Copy the contents of the `StF-Data-Logger-Oct-2024` folder into your Pd project directory (or into Pd's external/abstraction search path).  
   - This abstraction handles JSON parsing and data buffering for environmental sensor input.  
   - Make sure Pd can locate these files when opening `MainPatch.pd`.
4.  Open MainPatch.pd in Pd and connect to the live OSC feed from the Sensing the Forest installation.
6. Press Start to begin sonification.

## 🔊 Audio Examples
Baseline condition (04/03/2025 12:18) -> https://freesound.org/s/819426/
Extreme conditions (e.g., high temperature, high CO₂, high wind speed) -> https://freesound.org/p/44081/
Diurnal forest rhythm (04/04/2025 00:00, 08:00, 13:00, 21:00) → Capturing the “breathing” cycle of the forest through changes in timbre, tempo, and pitch -> https://freesound.org/p/44081/

## 📜 Citation
If you use this patch in your research or creative work, please cite:
X. Xu, Sonic Forest: Mapping Environmental Sensor Data to Sound for Climate Engagement, 2025.
Sensing the Forest Project
