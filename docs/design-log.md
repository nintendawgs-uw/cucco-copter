# Cucco-Copter Design Log

This document tracks part selection, major design decisions, and the reasoning behind them.
> Assembly notes and trade-offs encountered during install will be tracked in [build-log.md](build-log.md)

---

## System Overview

Drone component decisions are highly interdependent. The process was approached iteratively to ensure compatibility, expandability, and efficient performance.

The following relationships influenced our decisions:

- **Frame size** determines:  
  - Maximum propeller size  
  - Mounting space for sensors, MCU, battery, etc.  
  - Total weight of the base structure

- **Weight estimation** affects:  
  - Required thrust  
  - Propeller and motor selection  
  - Battery capacity and ESC requirements  
  - Frame strength and space needs

- **Motor and propeller selection** drives:  
  - Power draw (affects ESC and battery ratings)  
  - Frame compatibility (prop clearance)  
  - Flight time vs performance trade-offs

- **Payload (GPS, camera, logging modules, etc.)** adds weight and electrical complexity  
  - Affects motor sizing and power budget  
  - Influences frame layout and sensor placement

Each section below documents how these constraints were evaluated and balanced.

---

# The Frame

## Design Dependencies

This decision affects and is influenced by:
- **Weight**: The frame itself contributes to AUW (All-Up Weight) and must support all mounted components
- **Prop size**: The frame must provide adequate clearance for target propellers (6"–7")
- **Component layout**: Must fit MCU, battery, sensors, and allow clean wiring and mounting
- **Flight performance**: Frame rigidity and size impact vibration damping and control responsiveness
- **Payload capacity**: Frame size impacts how much weight we can safely lift while preserving stability

## Criteria
We needed to choose a frame size that:

- Supports our MVP features (manual control, stability, telemetry)
- Leaves room for advanced features like GPS, data logging, video streaming, autonomous follow-me, and mapping
- Fits within a reasonable student budget
- Avoids needing multiple physical builds or hardware reconfigurations
- Supports a single, scalable platform design
  

## Sizes Considered

| Option       | Pros                                                                                   | Cons                                                                                       |
|--------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| **250mm**    | - Light and cheap<br>- Agile<br>- Indoor testable                                      | - Tight layout<br>- Lower payload<br>- Would require compromises or multiple configurations |
| **330–360mm**| - Extra mounting space<br>- Supports GPS, telemetry, camera, and SD logging simultaneously<br>- Better hover efficiency = longer flight time<br>- One build to support all features | - More expensive (~$50 more)<br>- Outdoor-only testing<br>- Slightly less agile             |
| **550mm**    | - Maximum payload<br>- Tons of space<br>- Great for gimbals or cinematic work           | - Overkill for our needs<br>- Heavier and costlier<br>- Slower to build and debug          |


## Rationale
The **330–360mm class** hits the sweet spot between cost, functionality, and scalability. It allows us to:

- Mount all core components (MCU, sensors, camera, GPS, battery, etc.) cleanly on a single platform
- Avoid swapping components or re-flashing firmware depending on the use case
- Support both MVP testing and advanced features without needing a second build
- Increase flight time by using more efficient motors and larger props (6–7")
- Keep total cost reasonable and still get it flying in a short timeframe


## To Do:
- Choose material (e.g. carbon fiber vs plastic)
- Finalize exact frame size (e.g. 360mm) and shape ('X' vs '+' vs 'H')
- Decide on mounting strategy (stacked, rail, etc.)
- Estimate total weight and layout constraints

---

## Motor & Prop

## Design Dependencies

This decision depends on:
- **Total drone weight**: Including frame, electronics, payload, and battery
- **Frame prop clearance**: Maximum prop size allowed without collision
- **Target thrust-to-weight ratio**: Minimum 2:1 for safe hover and control
- **Battery voltage**: Must match motor rating and desired current draw
- **Flight time**: Must balance thrust output and energy consumption

(We will refine calculations as frame and component weights are finalized.)

## Power System (ESCs + Battery + PDB)

...

## Flight Controller & MCU

...

## Sensors & Telemetry

...

## Communication

...

## Testing Plans

...
