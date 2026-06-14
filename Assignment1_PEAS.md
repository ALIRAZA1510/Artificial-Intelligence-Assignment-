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
Task 2: Environment Classification
Factor	Selected Option	Justification OR Reason
System Visibility	Partially Observable	Sensors like vibration, temperature, and sound only show the current condition of machine parts, while hidden problems like internal wear or small cracks cannot be directly seen.
Agents	Multi-agent	The system works together with human maintenance technicians, plant operators, and automated systems like ERP or inventory tools. Their actions can influence the agent’s decisions and plans.
Predictability	Uncertain	Equipment wear depends on unpredictable factors like load changes and material defects, so the same sensor readings do not always lead to the same failure..
Step-by-step vs History-based	History-based	Each decision depends on past machine performance and previous maintenance, not just the current state alone.
Static vs Dynamic	Dynamic	Machine conditions change continuously even while the agent analyzes data, since production lines keep running and new readings keep arriving.
Type of Data	Continuous	
Sensor data like vibration, temperature, and pressure changes smoothly over time, not in fixed steps.

Task 3: Critical Analysis
1. Which dimension is the biggest challenge?
The biggest challenge is that equipment failure is uncertain. Similar sensor readings can lead to different outcomes, so fixed warning limits are difficult to set. Strict limits cause false alarms, while loose limits miss real failures. Engineers use probabilistic models (like Bayesian and survival analysis) and continuously update them with new data. Internal machine damage also cannot be directly observed, making prediction harder.
2. Utility Function (Speed vs Safety Trade-off)
This function balances production speed and machine safety:
U = w1 × Production Continuity w2 × Failure Risk
Production Continuity means keeping machines running, while Failure Risk refers to the likelihood and severity of failure. Increasing w2 makes the system more cautious, causing earlier shutdowns to prevent failures, even if it increases downtime. This prioritizes safety over speed in high-risk situations.
Task 4: Structured Representation.

{
  "assignment": "AI System Specification",
  "topic": "PEAS Framework - Predictive Maintenance System",

  "PEAS": {
    "performance_measures": [
      "Failure prediction accuracy",
      "False alarm rate",
      "MTBF improvement",
      "Maintenance cost reduction",
      "Unplanned downtime hours"
    ],

    "environment": "Industrial factory with connected machines (CNC, motors, pumps). Conditions change due to production schedules, temperature, humidity, electrical noise, vibrations, and human operators.",

    "actuators": [
      "CMMS alerts and work orders",
      "Email/SMS notifications",
      "PLC machine control adjustments",
      "Dashboard updates"
    ],

    "sensors": [
      "Vibration and accelerometers",
      "Temperature sensors",
      "Acoustic microphones",
      "Current and voltage sensors",
      "Oil quality sensors",
      "Machine operational data (RPM, load, runtime)"
    ]
  },

  "environment_classification": {
    "visibility": "Partially Observable",
    "agents": "Multi-agent",
    "predictability": "Uncertain",
    "decision_type": "History-based",
    "dynamics": "Dynamic",
    "data_type": "Continuous"
  },

  "critical_analysis": {
    "main_challenge": "Uncertain failure behavior from similar sensor readings",
    "solution": "Use probabilistic models (Bayesian, survival analysis) and continuous updates",
    
    "utility_function": "U = w1(Production Continuity) - w2(Failure Risk)",
    
    "tradeoff": "Higher w2 makes system more safety-focused, causing earlier shutdowns"
  }
}

