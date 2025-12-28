## 12/27/25: 
- Write a python script that uses/calculates electrical constraints to calculate max torque 
- Generate PCB/ PCB coils using this github repo: https://github.com/atomic14/kicad-coil-plugins.git
- Pretty amazing repo, can use the magnetic feild plots to improve torque
- HASL lead free, has a smoother surface than HASL w/lead. 
- Made progress in understanding how I'm gonna do the above

## 12/28/25
- Added netnames to the coil generator. This defined input-external traces as Connection [A,B,C]
- net_name= Coil [A,B,C ] ensures that coils on multiple layers are treated as one, that way both are energized to create a B-feild
- The notebook successfully produced a 2-layer and 4-layer CSV
- Using this CSV I will rewrite my max torque code(which wasnt pushed earlier due to branching issues) to take the CSV geometrical vaues and apply them to the max torque inductrance approximation
- Hopefully once I configure all the electrical paths, a proper PCB stator will be produced --2:51pm  
  
