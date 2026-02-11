Size-Based Sorting System
CODESYS + Factory I/O Project

📌 Project Overview

This project is an automated size-based sorting system developed using CODESYS (PLC programming) integrated with Factory I/O (3D simulation environment).

The system detects and sorts boxes based on their size using photoelectric sensors and controls conveyor and pusher motors accordingly.

🏗️ System Components
🔹 Actuators

1 Conveyor Motor (Main transport line)

1 Pusher Motor (Diverts large boxes)

🔹 Sensors

Sensor 1 → First height detection (Lower level)

Sensor 2 → Second height detection (Upper level)

⚙️ Working Principle

The system classifies boxes into Small and Large categories based on sensor detection logic:

🟢 Small Box Logic

Sensor 1 = NOT activated

Sensor 2 = NOT activated

Pusher motor remains OFF

Box continues on main conveyor path

If the first sensor does not detect anything, the box is considered small, and the pusher mechanism is disabled.

🔵 Large Box Logic

Sensor 1 = Activated

Sensor 2 = Activated

If both sensors detect the box, it is classified as large.

When a large box is confirmed:

The pusher motor is activated

Pusher runs for 750 ms

After 750 ms, the pusher automatically resets

System returns to standby state for next box

🧠 Control Logic Details

Developed using Ladder Logic in CODESYS

Timer (TON) used for 750 ms pusher activation

Interlocking logic implemented to prevent:

False triggering

Small boxes activating pusher

Continuous conveyor operation with conditional diverter activation

🔄 Sequence of Operation

Conveyor runs continuously.

Box reaches Sensor 1.

If Sensor 1 is not triggered → Small box → Continue straight.

If Sensor 1 is triggered:

Wait for Sensor 2 confirmation.

If Sensor 2 is also triggered → Large box confirmed.

Pusher motor runs for 750 ms.

System resets and waits for next object.

🛠️ Tools & Technologies

CODESYS (PLC Programming)

Ladder Logic

TON Timer

Factory I/O Simulation

Digital Inputs / Outputs Mapping

Industrial Control Concepts

🎯 Learning Outcomes

Practical implementation of sensor-based decision logic

Timer-based motor control

Industrial sorting system design

PLC-to-simulation communication

Real-world automation logic structuring
