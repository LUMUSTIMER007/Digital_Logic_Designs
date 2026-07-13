# Digital Flight Control System

A digital logic project that simulates a fault-tolerant flight control system for a sub-orbital rocket. The system combines combinational and sequential logic to perform hazard detection, flight sequencing, deployment control, and telemetry error checking.

## Features

### Phase 0 - Hazard Detection
Implements a **2-out-of-3 voting logic** using three hazard sensors:
- Low Fuel Pressure
- High Tilt
- Structural Strain

**Purpose:** Prevents false aborts caused by temporary sensor noise.

---

### Phase 1 - Priority Deployment Controller
Controls parachute deployment based on flight conditions.

A **Manual Override** signal always has the highest priority over automatic inputs.

**Purpose:** Ensures the parachute can always be deployed during emergencies.

---

### Phase 2 - Redundant Sensor Monitoring
Compares two identical tilt sensors.

- Turns ON a Fault LED if the sensors disagree.
- Enters SAFE mode if the mismatch continues for more than two clock cycles.

**Purpose:** Detects sensor failures and improves system reliability.

---

### Phase 3 - Flight State Machine
Implements a 2-bit FSM with four flight states:
- Standby
- Ascent
- Descent
- Recovery

The state machine only allows forward transitions and corrects invalid states automatically.

**Purpose:** Tracks the rocket's flight stage safely.

---

### Phase 4 - Telemetry Parity Generator
Generates an **even parity bit** for the mission status data.

**Purpose:** Detects transmission errors during telemetry communication.

---

## Concepts Used

- Boolean Algebra
- Karnaugh Maps
- Logic Gates
- Combinational Logic
- Sequential Logic
- D Flip-Flops
- Finite State Machines (FSM)
- Even Parity Generator

---

## Tools Used

- Digital Logic Sim

