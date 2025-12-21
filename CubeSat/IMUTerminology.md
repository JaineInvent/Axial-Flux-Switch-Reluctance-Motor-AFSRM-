## Objective
- The IMU on the PyCubed is no longer in production
- Need to replace it with a new IMU
- The IMU my team found has **VDDIO = 1.9 V**
- The rest of the components on the PyCubed require **3.3 V**
- The solution is to use a **Low Dropout Regulator (LDO)**
- "All the pins need a ratio of VDDIO of 1.9v, so they need a" **bidirectional-level shifter**

## Inertial Measurement Unit (IMU)
- Uses sensors to measure orientation
- Most IMUs are **9-axis**

## 9-Axis IMUs
- **Accelerometer (X, Y, Z)**  
  - Measures linear translation
- **Gyroscope**  
  - Measures angular velocity
- **Magnetometer**  
  - Measures position relative to Earth’s magnetic field  
  - This is the coolest one


