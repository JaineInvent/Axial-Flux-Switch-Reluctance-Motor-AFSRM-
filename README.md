## Overview
Explore the use of Axial Flux Switch Reluctance Motors(AFSRM) for regenerative E-bike applications, by designing a scaled down AFSRM. 
Although PCB windings limit torque density compared to conventional coils, they were intentionally chosen to prioritize repeatability, geometric control, and fast design iteration for exploratory modeling and prototyping.
If torque does not meeting scaled objectives, other uses will be explored. 
## Objectives
- Utilize a PCB stator for prototyping feasibiliy, and create solutions to PCB coil limitations 
- Apply undergraduate Mechanics and Electricity & Magnetism to an electromechanical system
- Design/implement sensing and motor controls
- Model solutions for thermal management and learn to use FEA thermal simulations
- Implement a mock BMS(Battery Managment System)

This project is being developed incrementally as a long-term exploratory effort, with analytical and experimental results added over time.

## Table of Contents(Evolving)
[Detailed Project Plan](ProjectOutline.md)

[Mechanical](./Mechanical/): 
- Conceptual 3D Model of the AFSRM [ConceptModel](./Mechanical/ExplodedConceptAssembly.png)
- [Documentation](./Mechanical/Documentation.md)

[Electrical](./Electrical/):
- PCB creation and [coilAutomation](./Electrical/CoilAutomation/kicad-coil-plugins/)
- Biot-Savart [simulation](./Electrical/CoilAutomation/kicad-coil-plugins/simulations/)
- [Documentation](./Electrical/Documentation.md)

[Controls](./Controls/)
- [Documentation](./Controls/Documentation.md)




## Conceptual Approach 

1. [Electrical](./Electrical/)

    Determine coil geometries that produce the most Magnetic Flux using [Atomic14's Jupyter Notebooks](https://github.com/atomic14/kicad-coil-plugins.git)

    Use chosen coil geometry and other electrical constraints to find max torque and RPM. Calculations will be done using python scripts. 


2. [Mechanical](./Mechanical/) 

   - 3D Model the AFSRM including casing
   - Improve output torque & rpm
   - Perform Thermal Analysis(FEA) and create solutions to heating 


4. [Controls](./Controls/)

   - Integrate motor controls and sensors
   - Design a mock Battery Management System

For more information, please refer to: [Detailed Project Plan](ProjectOutline.md)

## Motivation
1. **Sustainability** 

    **E-bike Concept:**
  
    E-bikes are a solution to the last-mile problem, and are especially useful for those in urban deserts. However charging e-bikes requires practical storage.

    A regenerative E-bike can be kept outside since, ideally, they do not need to be charged. This saves space and makes sustainable transport in the outer-edges of the city more accessible. 

    **Axial-Flux Switched Reluctance Motors(AFSRMs)**

    Many electric motors rely on permanent magnets (PMs), whose extraction and processing can introduce significant environmental impacts, including water contamination and radioactive waste. In addition, PM supply chains are geographically concentrated, making them vulnerable to geopolitical disruption.

    AFSRMs avoid permanent magnets entirely, producing torque through magnetic reluctance and permeability differences between the stator and rotor (typically laminated electrical steel). This makes them an attractive candidate for magnet-free, sustainable motor designs.


2. **Technical**

    **PCB Stator AFSRMs and Prototyping** 

    AFSRMs are more compact, as their thickness is minimal compared to their diameter. Additionally, they are easier to prototype due to their "Stacked pancake nature" 

    Using PCBs as the coils, makes prototyping and testing easier than hand-winding coils.

    Advantages due to lack of PMs: 
    - Cheaper 
    - No risk of demagnitization due to heating
    - Lighter

    **Electromechanics and Magnetic-Feild modelling**

    This project was created becuase I: 
    - Wanted to delve into Electromechanics through an applicable project
    - Enjoyed undergrad Electricity & Magnetism and wanted to apply Circuits, Maxwell's Equations, and Biot-Savart Law
    - Learn PCB design
    - Model and perform calculations using Python 
    - Explore thermal limitations and thermal Fea Modelling 
    - Apply Mechanics and Dynamics
    - Design the AFSRM using CAD
    - Understand Motor controls  



## Credits
Readme Author: Jaine R.

Project Contributors: 
  - Jaine R. (Electrical & Mechanical) 
  - Kezia S. (Controls)

  Note: This is an ongoing project. Teammates and contributions will be added as the project progress.

External References:
- Atomic14 [Github Repository](https://github.com/atomic14/kicad-coil-plugins.git)
