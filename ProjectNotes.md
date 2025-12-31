# Mechanical 
1. Identify dimensions: 
Due to the 3D printers have a max bed size of 150mm x 150mm, I chose a radius of 65mm. 
- r = 65mm 
2. Identify Power(output) and torque requirements: 
- I'll find an interesting robot online, and base my actuator goals based on that of the existing actuator
- Based on electrical constraints, I can calculate max torque for my actuator
- Then I can improve on that torque(ie make it useful using planetary gears and dynamics)
3. Design Casing 
- Room for electronics/wiring, sensors, bearings, gears for ratios if needed  
- Thermal considerations
4. Model the heating prior to first assembly, and figure out a way to reduce heating in such a compact motor.
- Laminated Steel plates for the rotor
- PLA for the outercasing
# Electrical/Magnetism --> <3 
 ## Variables/Inputs: 
 - Airgap 
 - Coil resistance 
 - etc, I'm sure I'll find some more lol
## Tools/ general set-up
1. Use KiCad plug-ins (Wedge shaped vs spiral coils) and compare the useful torque produced from using Biot-Savart, Magnetic Force, and Magnetic Reluctance. 
- I can use the Biot-Savart open source python to compare the 2 coil configs 
- Probably going to use 2-layer PCBs with coils on each side of the PCB 
2. Laminated Steel sheets 
- Will factor in eddy currents if losses and heating become extremely significant
- May need to go with alternative solution, as I'm not sure whether the machine shop can produce the steel-sheets
- Could sacrifice air-gap and do steel blocks as an alternative??
3. Back EMF
- Will be factored into the design, with a goal for 5V power supply. 
# Controls
1. Supply Voltage
- The goal is to use a low voltage, safe for prototyping. I think 5V shouldn't be too difficult. 
2. Switching Phases 
- Hall Sensor?
- Motor controller? 
- Still need to do more research on that. 

# Overall Flow: 
Electrical constraints --> Mechanical optimization, should be fun. 
## Constraints: 
1. Power Supply = 5V
2. trace spacing, resistance
3. Max Current, split between sensors and pcb traces. 