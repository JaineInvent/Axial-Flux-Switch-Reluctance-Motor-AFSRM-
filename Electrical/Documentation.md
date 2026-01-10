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
- Hopefully once I configure all the electrical paths, a proper PCB stator will be produced

Things learnt:
net_names- a name or class that defines an electrical connection. If two coils are connected to the same netname, they share the same electrical connection. 
vias- pcb tunnels that allow for electrons to pass through multiple layers of the PCB. 


Author: Jaine R.

## 1/3/25
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
<img width="900" height="900" alt="coil1" src="https://github.com/user-attachments/assets/7511d6f1-92c1-4b4b-8364-f6b5b6d0a599" />

Things Learnt: 
- Check the helper files for updates prior to debugging attempts
- A list can be changed into a dict. Those points can be rewritten as values, and a key can be assigned.
- Dict: a structure that stores pairs of keys and values instead of a long list of points
- Keys: classifications/names/identifiers

Issues with this PCB and the code:
- Input vias too close to shaft hole
- hole radius <8 mm
- Code doesn't handle scaling, rather, the author uses an unshared formula to change the geometry for larger PCB radii

Update: Upon closer inspection of the code, the template can be used in the geometric formulas for winding the pcb traces, however, templates are just an option specific to the user. Commenting out the template revealed that, due to geometric offsets, normalizations, and reference vectors; radius is taken into account. 

<img width="917" height="959" alt="b92572ce-021f-4720-8c92-ca1273e57e0a" src="https://github.com/user-attachments/assets/e4bf01c9-8ffc-41a6-ad8c-4b771e78e276" />

Next Steps: 

- rescale the above plot such that pads are visible and holes for pcb mounting can be inspected
- Use Biot-Savart code and modify the pcb to optimize for largest B-feild in the axial direction
- Calculate max torque and rpm with an assumed current and voltage (Assumptions listed in corresponding entry)
   




        
  
