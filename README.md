# ECE445


## **Date:** September 23, 2025  
Sensory Subsystem Initial Research  


### Work Completed
Reviewed the approved project proposal and clarified project requirements. The posture checker must be compact, wearable, low power, and capable of detecting changes in body posture over time.

Investigated into potential sensing approaches:
- Inertial Measurement Units (IMUs)
- Flex/stretch sensors
- Pressure sensors
- Tilt switches

Tilt switches were ruled out due to binary output. Pressure sensors were considered unreliable because of inconsistent contact with the body. Flex sensors were considered but noted to be prone to drift and mechanical fatigue.

### Notes
IMU-based sensing in combination with stretch sensors were considered as the most suitable approach for posture monitoring


---


## **Date:** September 30, 2025  
Sensor comparison and IMU Selection


### Work Completed
Compared sensor options based on accuracy, size, power consumption, compatibility and price. Then reviewed datasheets and designs for shortlisted IMUs. Selected the **ICM-20948** IMU as the most suitable option for this project


**Summary of findings on different sensor options:**
- **Flex sensors:** Low cost but inconsistent and subject to wear
- **Single-axis accelerometers:** Insufficient orientation information
- **6-axis IMUs:** Functional but limited options and compatibility
- **9-axis IMUs:** Best overall capability for posture detection

Reviewed commonly used IMUs including MPU-6050, MPU-9250, and ICM-20948

**Justification of choses IMU-20948:**
- Integrated accelerometer, gyroscope, and magnetometer
- Small form factor matches our project goals
- Low-power operating modes to help ensure battery life is maintained
- I²C communication compatible with the MCU 
- Lots of available libraries to help program the IMU

### Notes
9-axis IMUs selected as preferred sensor class due to its flexibility and future project progression. Withing the 0-acis IMU options the ICM-20948 was chosen as the primary posture sensor as it was the most suitable IMU


---

## **Date:** October 7, 2025  
IMU-20948 requirements and design choices

### Work Completed
How the Sensor subsystem interacts with other subsystems:
- **Microcontroller:** I²C communication for data processing
- **Power subsystem:** 3.3V and 1.8V supplied to the IMU
- **Feedback subsystem:** Connected through the MCU to provide a feedback to the user

### Notes / Decisions
Confirmed how the Sensor subsystem works with other subsystems to see how to design it

---

## **Date:** October 14, 2025  
Schematics layout design  


### Work Completed
Reviewed ICM-20948 reference schematics. Identified required other components required:
- Decoupling capacitors near power pins
- Pull-up resistors on I²C lines
- Voltage regulator for 3.3V and 1.8V supply (Came from power subsystem)
- Level shifting required to communicate with MCU

Discussed sensor placement to maintain a consistent coordinate frame relative to user posture.

### Notes
Schematic Completed based on datasheet and requirements. 

*Datasheets and schematics are uploaded in the Git repository for reference*

---

## **Date:** October 28, 2025  
PCB Layout and Sensor Placement  


### Work Completed
Reviewed IMU PCB layout guidelines:
- Short I²C traces
- Close placement of decoupling capacitors
- Avoidance of noisy digital signals near sensor

Determined IMU orientation on PCB to align axes with posture directions.

### Notes
IMU orientation selected and PCB design completed

*PCB designs are uploaded in the Git repository for reference*

---

## **Date:** November 4, 2025 
Testing and Verification Planning  
 

### Work Completed
Defined test procedures:
- Power-on verification
- I²C communication check
- Static orientation testing
- Dynamic movement testing

Planned to record raw sensor outputs and verify repeatability/accuracy across tests

### Notes / Decisions
Testing focused on stability and repeatability rather than full accuracy

---

## **Date:** November 11, 2025  
Sensory Subsystem initial Testing and Debugging  


### Work Completed
Verified IMU communication with the MCU and confirmed correct device identification. Observed stable accelerometer readings under static conditions.

Simulated posture changes by rotating the device and observing sensor output response.

### Issues Detected
Minor noise present in raw data, consistent with expected results and doesnt have a huge impact on the data

---

## **Date:** December 2, 2025 
Final Verification and Documentation  
 

### Work Completed
Confirmed IMU operation during integrated system testing. Sensor data successfully used to detect posture changes and trigger system feedback

Reviewed design decisions and the testing results for final documentation

### Notes
Sensory subsystem meets functional requirements

*Test results are uploaded in the Git repository for reference*

