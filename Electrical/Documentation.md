## 12/27/25: 
- Write a python script that uses/calculates electrical constraints to calculate max torque 
- Generate PCB/ PCB coils using this github repo: https://github.com/atomic14/kicad-coil-plugins.git
- Pretty amazing repo, can use the magnetic feild plots to improve torque
- HASL lead free, has a smoother surface than HASL w/lead. 
- Made progress in understanding how I'm gonna do the above

Author: Jaine R.

## 12/28/25
- Added netnames to the coil generator. This defined input-external traces as Connection [A,B,C]
- net_name= Coil [A,B,C ] ensures that coils on multiple layers are treated as one, that way both are energized to create a B-feild
- The notebook successfully produced a 2-layer and 4-layer CSV
- Using this CSV I will rewrite my max torque code(which wasnt pushed earlier due to branching issues) to take the CSV geometrical vaues and apply them to the max torque inductrance approximation
- Hopefully once I configure all the electrical paths, a proper PCB stator will be produced --2:51pm  

Author: Jaine R.

## 1/3/25
- Added and understood all the net_names and their physical connection on the PCB

Originally I wanted to modify the coil automation notebook to maximize coil fill on the PCB, however, I found that it is geometrically complex and that the original author's variable names did not align with mine. 

I realized that building an optimization code for N, vias_radius, etc would take longer than iterating constraints.

To iterate constraints I have/had to: 
- Add proper net_names
- Debug discrepancies between pcb_json.py and the notebook: 
    - components= was missing
    - "tracks_in1" was corrected to "tracks_in"
    - Stuck on json file expecting referncing by names instead of the discrete points produced by the notebook 
    
This seems like more work than manually drawing out the coils, however, the CSV is crucial to the simulations and this may reduce error later in the build-phase of the prototype. 

Next steps:
- Finish Debugging
- Start iterating and finding parameters that may produce highest torque(based on B-feild)

Author: Jaine R. 

## 1/9/25 
-Finished dubugging the coil generator, which produced this PCB Stator: 
<img width="1100" height="1100" alt="coil1" src="https://github.com/user-attachments/assets/7511d6f1-92c1-4b4b-8364-f6b5b6d0a599" />
