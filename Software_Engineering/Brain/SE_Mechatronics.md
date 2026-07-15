---
tags: [software-engineering, year-11, hsc, mechatronics, cpu, microcontroller, sensors, actuators, control-systems]
aliases: [SE Mechatronics, CPU vs Microcontroller, Control Algorithms, Open/Closed Loop]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 Mechatronics
created: 2026-07-15
updated: 2026-07-15
---

# Mechatronics — Year 11 SE

> Self-contained note on what mechatronics is, CPUs vs microcontrollers (fetch-execute cycle), mechatronic hardware & software (sensors/actuators), planning & designing a mechatronic system (control algorithms, open/closed loop, PID), and electricity revision. Built from M1–M4 and the electricity starter/answers. Every definition sourced.

---

## 1. What Mechatronics Is

- **Definition (composition):** "Mechatronics = Mechanics + Electronics + Computing + Control Systems." [Intro]
- "Mechatronics is a fascinating field that combines mechanical, electrical, electronic, and software engineering to create smarter and more efficient systems." [M1]
- **Origin:** "The term 'mechatronics' was coined in Japan by Tetsuro Mori, an engineer at Yaskawa Electric Corporation. It's a combination of 'mechanics' and 'electronics'." [M1]
- **Where found:** robotics, automated systems, smart home devices; robotic arms, drones, self-driving cars. [Intro]
- **Benefits:** Efficiency and speed; Reduced human error; Can take on dangerous or repetitive tasks. [Intro]
- **Drawbacks:** Job loss in some sectors; High costs; Ethical concerns (surveillance, dependency). [Intro]
- **Disability applications:** exoskeleton suits (cerebral palsy), robotic prosthetic limbs (amputations), brain-machine interfaces (spinal injuries), custom robotic enhancements. [Intro]

---

## 2. CPUs vs Microcontrollers (M2)

### CPU components
- **Control Unit (CU):** "runs the CPU and thus the fetch-execute cycle."
- **Arithmetic Logic Unit (ALU):** "runs mathematical operations."
- **Registers** (a register = "a temporary memory location mainly accessible to the CPU"):
  - **PC — Program Counter:** "working out what line number or memory address is next to be executed."
  - **MAR — Memory Address Register:** "the memory address currently being accessed."
  - **ACC — Accumulator:** "contains the results of all the current operations."
  - **CIR/IR — Current Instruction Register:** "holds the current instruction being executed."

### The fetch-execute cycle (pseudocode) [M2]
```
BEGIN
    PC → MAR
    MAR sends address to RAM
    RAM sends data at address to MDR
    MDR → CIR
    CU decodes CIR contents
    OPCODE ← CIR[bits 0–3]
    OPERAND ← CIR[bits 4–7]
    IF OPCODE == 0101 THEN ... (load operand into ACC)
    IF OPCODE == 0001 THEN ... (ACC ← ACC + MDR)
    IF OPCODE == 0010 THEN ... (ACC ← ACC - MDR)
    PC ← PC + 1
END
```
Step-by-step (one cycle): CU copies PC to MAR → onto Address Bus → memory loads value to Data Bus → MDR → CIR → PC incremented → Decode Unit splits opcode/operand → opcode `0000` means end program. [M2]

### Opcodes / machine language
- Instructions and data stored as binary in RAM. Worked example: addresses `0010 1000` (=5) and `0010 1001` (=3) match the values typed in. [M2]
- Sample: Mem 6 contained `A1`; program added Mem 5 (`30`) → `A1 + 30 = D1` hex. [M2]
- Multiply Mem 5 by three into Mem 7:
```
LOAD  (Reg1, Mem 5)        ; Reg1 = Mem5 (x)
ADD   (Reg2, Reg1, Reg1)   ; Reg2 = x + x = 2x
ADD   (Reg3, Reg2, Reg1)   ; Reg3 = 2x + x = 3x
STORE (Reg3, Mem 7)        ; Mem7 = 3x
STOP
```

### CPU vs Microcontroller — core comparison
- "A CPU is just the processor and needs extra parts to work, handling many tasks fast. A microcontroller has a CPU, memory, and I/O in one chip for specific tasks." [M2]
- CPUs have more/faster registers and complex opcodes; microcontrollers have fewer registers and simpler opcodes for hardware control. [M2]
- **CPU:** general-purpose, many fast tasks (no built-in memory/I/O). **Microcontroller:** specific/embedded tasks, integrates CPU+memory+I/O in one chip, suited to mechatronic systems (e.g. Arduino). [M2]

---

## 3. Mechatronic Hardware & Software (M3)

### Core definitions
- **Sensor:** "a device that transduces a physical quantity such as pressure, light, motion, or temperature into an electrical signal that can be read by a control system."
- **Actuator:** "a mechanism that converts electrical input into a mechanical action, like motion or force."
- **End effector / gripper:** "grips objects using mechanical jaws or fingers, often driven by servos or pneumatics."

### Sensors / actuators across industries [M3]
- **Manufacturing** — Sensors: position, temperature, flow, pressure. Actuators: motors, valves, conveyor belts, robotic arms.
- **Healthcare** — Sensors: vital signs, movement, environment. Actuators: prosthetics, surgical tools, infusion/breathing pumps.
- **Agriculture** — Sensors: soil moisture, temperature, crop health, obstacle detection. Actuators: irrigation, spray systems, driverless tractors.
- **Construction** — Sensors: structural stress, orientation. Actuators: hydraulic machinery (excavators, lifts).
- **Transportation** — Sensors: speed, proximity, orientation. Actuators: braking, steering, doors, suspension, autonomous systems.

### How specific sensors work [M3]
- **PIR:** detects changes in infrared radiation (body heat) across paired segments; differential signals amplified/compared.
- **Accelerometer** (micro:bit): measures acceleration/tilt via MEMS; 3 axes.
- **Gyroscope:** measures angular velocity via vibrating structures/rotating mass.
- **Ultrasonic distance:** emits pulses, measures echo return time → distance.
- **LDR:** resistance changes with light (dark = high, bright = low).
- **Analogue sensor:** output voltage varies continuously; needs ADC to interface with digital systems.
- **I2C Light Sensor:** uses I2C serial protocol for digital light reading.
- **Joystick:** potentiometers or hall-effect sensors → X/Y axis control.

### How specific actuators work [M3]
- **Rotary/linear servos/micro servo:** servos convert electrical signals to precise movement; rotary up to 180°, continuous rotate indefinitely.
- **Hydraulic actuator:** fluid pressure moves a piston → linear/rotary high-force motion.
- **Robotic gripper:** picks up, holds, releases (controlled by sensor signals).

### Device classification [M3]
- DC motor — Output, Actuator.
- "DC motor + gearing to clamp" — Output, End Effector (and actuator).
- Accelerometer (3 axes) — Input, Sensor.
- Photodiode — Input, Sensor.
- 180° positional servo — Output, Actuator.

### The software / data layer [M3]
- **Operational data:** real-time sensor readings (temperature, motion).
- **Diagnostic data:** error codes, system health metrics.
- **Optimisation data:** historical performance for predictive maintenance.
- "Sensors capture raw data. The controller processes this [via] filtering, analytics, decision logic to determine actuator responses. This feedback loop ensures adaptability, precision, and safety."

---

## 4. Planning & Designing a Mechatronic System (M4)

### Wiring diagram components [M4]
Capacitor (stores energy as electric field), Diode (one-way current), Resistor (limits current), Potentiometer (adjustable resistor), 2-way switch, On/off switch, Speaker, Motor, LED, Lightbulb, Integrated circuit (microcontroller), Voltage source, Operational amplifier.

### Wiring a real circuit [M4]
- **Variable speed via potentiometer:** one end to power, other to ground; centre tap to an analog input.
- **On/off via switch:** one end to power, other to digital input; resistor to ground prevents "floating" when open.
- **User feedback via LED:** one end to digital output, other to ground through a resistor (limits current).
- **Power the microcontroller:** USB to voltage source; negative side to ground.

### Control algorithms [M4]
"A control algorithm is code that controls the operation of a mechatronic system. It uses values from the available sensors to compute outputs that it then sends to connected actuators."
Typical structure:
1. **Set-up / calibration:** measure range of sensor values (e.g. line-follower measures reflected light from line vs background).
2. **Main control loop** (repeated): (a) Read sensors → current state; (b) Compute control values to approach a desired **set point** (e.g. room temp, car speed); (c) Output to actuators.
Worked comparison: first algorithm = jerky on/off control (constant overcorrection); second = smoother **proportional control** (correction depends on distance from line).

### Open-loop vs closed-loop control [M4]
- **Closed loop error:** comparing desired set point with actual sensor value.
- **Advantage of closed loop:** "more accurate because the system constantly monitors feedback and adjusts itself."
- **Disadvantage:** "more complex and expensive … require sensors, feedback mechanisms, and faster processing."
Classification:
| System | Loop |
|---|---|
| TV remote | Open |
| Vehicle cruise control | Closed |
| Vehicle steering | Closed |
| Ceiling fan speed | Open |
| Air conditioner temp | Closed |
| Washing machine cycle timing | Open |
| Traffic light control | Open |
| Robotic arm (predetermined) | Open |
| Line-following robot | Closed |

### Autonomous control algorithms (3 types, all closed-loop) [M4]
- **On/off ("bang-bang"):** switches abruptly between two extremes (fully on/off), no intermediate levels.
- **Proportional:** "adjusts the output continuously based on the size of the error" — reduces oscillations; weakness: small steady-state error may remain.
- **PID (proportional, integral, derivative):** Integral accumulates error over time to eliminate it; Derivative responds to rate of change, damping overshoot → more stable/responsive.

---

## 5. Electricity Revision (Starter + Answers)

Drawn from the student worksheet and its mark scheme. Accepted answers:
- **Complete vs incomplete circuits:** ammeter reads zero if wire missing between battery & bulb, battery wrongly connected, bulb blown; reads if "circuit is connected correctly / complete circuit."
- **Flywheel energy:** stored as **kinetic energy**. Brighter bulb (more energy/sec) → flywheel "slows down more quickly." Energy lost: from axle/bearings (heat/sound) and from wires (heat).
- **Resistance / Ohm's law:**
  - Ammeter "drawn in series"; voltmeter "in parallel with the material."
  - Change current: "adjust / use the variable resistor."
  - Conducting putty at 25 cm, current 0.15 A → resistance = **37.5 Ω** (accept 36–39).
  - Potential difference = current × resistance → **37.5 × 0.15 = 5.625 V** (mark scheme 5.6(25)).
  - "the thicker the putty the lower the resistance."
  - Improve reliability: "repeat readings and take a mean" (not just "take more readings").
- **Energy resources:** fossil fuels = coal, gas (accept petrol/oil); solar panel source = the Sun; turbine blades turn due to wind; renewable = Sun/solar, waves, wind. Solar panel "cannot work at night because no light"; wind turbine "cannot generate all the time because it might not be windy."

---

> **See also:** [[SE_Software_Dev_Process]] | [[SE_Algorithms_and_Desk_Checks]] | [[SE_Numbering_Systems]] | [[SE_Programming_Paradigms]] | [[SE_Object_Oriented_Programming]]
