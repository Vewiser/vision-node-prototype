# 01 // Electronics and Circuit Design

## Design loop

**DEFINE → CALCULATE → SIMULATE → BUILD → MEASURE → TROUBLESHOOT → DOCUMENT**

For every circuit, record its purpose, supply, current limit, schematic, component values, expected test-point readings, tolerances, maximum ratings, measured results, safe failure, recovery, and final revision.

## Theory blocks

### Electrical foundations

- Voltage, current, resistance, power, energy, polarity, continuity, and ground references
- Ohm's law: `V = I × R`
- Power: `P = V × I`, `P = I²R`, and `P = V²/R`
- Series/parallel networks, open circuits, short circuits, current limiting, fuses, and heat

### Components and behavior

- Resistors, potentiometers, capacitors, inductors, and transformers
- Diodes, LEDs, rectifiers, BJTs, MOSFETs, relays, regulators, sensors, and connectors
- Kirchhoff's laws, RC time constants, filters, AC, phase, reactance, resonance, and Q
- Analog/digital signals, logic levels, pull resistors, debouncing, and level compatibility
- Return paths, decoupling, noise, shielding, EMI, tolerance, derating, and fault protection
- Datasheet symbols, pinouts, packages, ratings, and normal operating conditions

## Design tools

- Calculate on paper before simulation.
- Use KiCad or another reviewed tool for original schematics.
- Use SPICE for predictions—not proof of physical behavior.
- Use breadboards for low-frequency prototypes; move to perfboard or PCB only after validation.
- Keep original design files, sanitized measurements, and revisions in GitHub.

## Bench progression

| Lab | Build | Predict and prove |
| --- | --- | --- |
| E1 | LED status indicator | Resistor, current, power, voltage, polarity |
| E2 | Series/parallel network | Node voltages and branch currents |
| E3 | RC charge/discharge | Time constant and five-time-constant response |
| E4 | Low-pass filter | Cutoff and output across frequencies |
| E5 | Transistor switch | Drive, load current, off/on state, temperature |
| E6 | Protected 5 V load | Current budget and safe fault response |
| E7 | Sensor interface | Signal range, logic level, Linux data log |
| E8 | Original circuit | Full design budget and independent rebuild |

## Measurement discipline

Before probing, state what is being measured, the expected range, the reference point, whether the meter belongs in series or parallel, and whether the selected mode could short or overload anything.

Never measure resistance or continuity on an energized circuit. Never place a meter configured for current directly across a voltage source. Verify lead placement, mode, and range every time.

## AI mastery prompts

- “Quiz me on Ohm's law using five small circuits. Hide answers until I commit.”
- “Review my schematic for missing protection, unclear grounds, rating mistakes, and assumptions. Ask before suggesting.”
- “Compare my predicted and measured values. Help me form three testable explanations without choosing one.”
- “Give me one reversible fault to diagnose on this extra-low-voltage circuit. Do not reveal it until I finish.”

## Gate to RF

Independently calculate an LED resistor and power rating; trace series/parallel current paths; identify a short, open, reversed part, and missing ground; use a meter safely; read a datasheet; and explain one filtered, protected 5 V circuit.
