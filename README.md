# Learning3DPrinterSystemDesign

# Metal 3D Printer

## FLOW
**General Flow**

1. Fill the metal powder tank to be used for 3d printing
2. Start the machine, initializing all the machine parameters, sensors and PLCs and PLC management system
3. Launch the control software loading the current machine configuration
4. Verify the PLC and Safety PLC configuration on launch
5. Inert the chamber with Argon gas until all the oxygen is out
6. Input a MTT file which has been processed from CAM/CAM files to make it 3D printable
7. Select the build file to be printed
8. start the build which periodically spreads the powder and laser sinters the powder
9. After laser has sintered the powder, one layer has been done and elevator should move down with every layer preparation
10. After all the layers have been sintered, remove the build

**Contigency Flow**
1. The machine should stop if oxygen level increases in between
2. There should be alarms raised in case of descripencies
3. Alarms should be categorised in low to critical level
4. In case of critical alarms the process should stop

**Other Inclusions**
1. The machine should be able to give us health parameters continously to be displayed over UI for monitoring purpose
2. There should be a calibration system in case of errors introduced due to shipping of machine - lasers
3. The control software can be installed in either in a workstation or a embedded hardware
4. Devices like PC, PLC, SPLC, Gas Pump and Powder Pump inverted should be connected via ethernet
5. There should be a cooling system for laser hardware module

## Software Requirements

1. **SQL database** for logging the events - static : for one time changing parameters and dynamic : for continous changing parameters
2. **JSON** file for configuration
3. Message Queues ????
4. Handle Concurrency to read health parameters from sensors along with sending commands for procedures
5. Microservices to Inert chamber, build file selection and 3d printer running
6. PLC management system
7. Build managment system
8. Health parameter management system
9. Command parameter manament system
10. Database managment system
11. Network configuation system
12. Login and Authentication System
13. MVC Architecture
14. Report generation in PDF form to give overall build details
15. There should be a log generation system for dianostics
16. Plugins for making tools for testing teams

**Code Quality Maintainance**
1. Unit tests for functional testing
2. Integration tests for loop testing
3. CD/CI pipeline like Azure pipeline for dev-ops
4. Machine Simulator for low cost testing 


# Microservices
Knowledge on Microservices is [here](https://www.youtube.com/watch?v=QrPvGdpcjXo&list=PL0zysOflRCelb2Y4WOVckFC6B050BzV0D&index=1)

## Chamber Inerting

