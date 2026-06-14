Assignment 1: AI System Specification
Topic: PEAS Framework and Task Environment Analysis
Predictive Maintenance System for Factory Machines and Equipment
Task 1: PEAS Specification
Performance Measure: 
•	Failure prediction accuracy The percentage of equipment failures that the system correctly predicts before they happen (for example, 24–72 hours in advance). 
•	False alarm rate The percentage of maintenance alerts given for machines that did not actually need maintenance. 
•	Mean Time Between Failures (MTBF) improvement  The increase in the average time a machine operates before it breaks down unexpectedly. 
•	Maintenance cost reduction The decrease in maintenance costs, including parts, labor, and emergency repairs, compared to regular scheduled maintenance. 
•	Unplanned downtime hours The total number of hours that production stops because of unexpected equipment failures.
Environment: The agent works in an industrial factory where many machines are connected, such as CNC machines, conveyor belts, motors, pumps, and compressors. It operates under different conditions, including changing production schedules, varying temperature and humidity, electrical interference that may affect sensor data, vibrations from nearby machines, and the activities of operators and maintenance staff who use and maintain the equipment.
Actuators: Since the agent mainly provides support and alerts, its actions are mostly digital. It sends maintenance alerts and work orders to the maintenance management system (CMMS), sends email or SMS notifications to maintenance staff, adjusts machine settings such as motor speed or load through PLCs when a serious risk is detected, and updates dashboards so plant managers can monitor equipment status.
Sensors: The agent collects information about each machine using industrial IoT sensors. These include vibration sensors and accelerometers, temperature sensors, microphones that detect unusual sounds, current and voltage sensors, oil quality sensors, and machine data such as RPM, load, and operating hours obtained directly from machine controllers.
