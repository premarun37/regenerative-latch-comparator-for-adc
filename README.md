# Regenerative Latch Comparator for Flash ADC

## Overview
This project explores the design and simulation of multiple comparator architectures used in high-speed Analog-to-Digital Converters (ADCs). The study evaluates different comparator topologies and integrates the Strong-Arm Latch Comparator into a Flash ADC architecture.

The complete design flow includes:

- Comparator architecture analysis
- Circuit-level implementation
- Simulation and performance verification
- Flash ADC subsystem development
- ADC output validation

## Objectives

- Study various comparator architectures.
- Compare static and dynamic comparator designs.
- Analyze regenerative latch behavior.
- Implement a Strong-Arm Latch Comparator.
- Design a Flash ADC using the selected comparator.
- Verify ADC operation through simulation.

## Comparator Architectures

### 1. Resistive Divider Comparator

#### Block Diagram
![Block Diagram](Design/01-Comparators/01-Resistive-DIvider-Comparator/01-Block-Diagram/01_Resistive_divider_comparator_block_diagram.jpg)

#### Schematic
![Schematic](Design/01-Comparators/01-Resistive-DIvider-Comparator/02-Schematics/01_Resistive_divider_omparator_circuit.jpg)

#### Simulation Result
![Simulation](Design/01-Comparators/01-Resistive-DIvider-Comparator/03-Simulation/01_Resistive_divider_comparator_simulation.jpg)

#### Working Principle
The resistive divider comparator generates a reference voltage using a resistor network. The input signal is compared against the reference voltage and the output switches according to the voltage difference.

#### Result

- Successful threshold detection.
- Simple architecture.
- Higher static power consumption due to resistor network.

### 2. Charge Sharing Comparator

#### Block Diagram
![Block Diagram](Design/01-Comparators/02-Charge-Sharing-Comparator/01-Block-Diagram/02_Charge_sharing_comparator_block_diagram.jpg)

#### Schematic
![Schematic](Design/01-Comparators/02-Charge-Sharing-Comparator/02-Schematics/02_Charge_sharing_comparator_circuit.jpg)

#### Simulation Result
![Simulation](Design/01-Comparators/02-Charge-Sharing-Comparator/03-Simulation/02_Charge_sharing_comparator_simulation.jpg)

#### Working Principle
The charge sharing comparator utilizes capacitor charge redistribution to determine the relationship between input and reference voltages.

#### Result

- Reduced static power.
- Faster operation than resistive implementations.
- Sensitive to capacitor mismatch.

### 3. Latch Dynamic Comparator

Additional comparator architectures can be documented here using the same structure:

4. Offset Compensated Comparator
5. Strong Arm Latch Comparator
6. Low Dynamic Comparator
7. Three Stage Dynamic Comparator
8. Two Stage Dynamic Comparator
9. Single Tail Comparator
10. Elzakker Comparator
11. Modified Strong Arm Latch Comparator
12. Voltage Sense Amplifier Comparator
13. PMOS Preamplifier Comparator
14. Dual Rail Double Tail Comparator

## Comparator Comparison Summary

| Comparator | Author(s) | Power (W) | Offset (V) | Delay (s) |
|------------|-----------|-----------|------------|-----------|
| Resistive Divider Comparator | Lauri Sumanen et al. | 13.98Âµ | 192.4m | 39.66n |
| Charge Charging Comparator | D. Meganathan et al. | 6.92Âµ | 193.5m | 120.8p |
| Latch Dynamic Comparator | C.-P. Huang et al. | 32.46Âµ | 206m | 30.08n |
| Offset Compensated Comparator | Fei Yuvan | 31.29Âµ | 105m | 16.63n |
| StrongARM Latch Comparator | L. Filippini, B. Taskin | 12.56Âµ | 189.2m | 77.72p |
| Low Power Dynamic Comparator | Subhash Chevella et al. | 22.34Âµ | 185.8m | 30.2n |
| Three Stage Comparator | Z. Li et al. | 32.215Âµ | 212m | 94.08p |
| Two Stage Comparator | Y. Wang et al. | 51.675Âµ | 204m | 30.08n |
| Elzakker Comparator | Z. Li et al. | 13.546Âµ | 209.6m | 30.11n |
| Modified StrongARM Comparator | Maria R. Siukaeva et al. | 8.6929Âµ | 206.7m | 51.87p |
| Voltage Sense Amplifier Comparator | Dinanath N. Donadkar et al. | 14.9016Âµ | 207.2m | 30.1n |
| PMOS Preamplifier Comparator | Maria R. Siukaeva et al. | 15.57Âµ | 205.9m | 4.137n |
| Dual Rail Double Tail Comparator | Dinanath N. Donadkar et al. | 31.6Âµ | 123.9m | 139.3p |

## ADC Design Flow

The Flash ADC was designed using the Strong-Arm Latch Comparator due to its high speed and low power characteristics.

### Step 1: Sample and Hold Circuit

#### Block Diagram
![Sample and Hold Block](Design/02-ADC/01-Sample-And-Hold/01-Block-Diagram/sample_hold_block.jpg)

#### Schematic
![Sample and Hold Schematic](Design/02-ADC/01-Sample-And-Hold/02-Schematics/sample_hold_schematic.jpg)

#### Simulation
![Sample and Hold Simulation](Design/02-ADC/01-Sample-And-Hold/03-Simulation/sample_hold_simulation.jpg)

#### Function
Samples the analog input and maintains a constant voltage during ADC conversion.

### Step 2: Strong Arm Comparator

#### Block Diagram
![Comparator Block](Design/02-ADC/03-Strong-Arm-Latch-Comparator/01-Block-Diagram/comparator_block.jpg)

#### Schematic
![Comparator Schematic](Design/02-ADC/03-Strong-Arm-Latch-Comparator/02-Schematics/comparator_schematic.jpg)

#### Simulation
![Comparator Simulation](Design/02-ADC/03-Strong-Arm-Latch-Comparator/03-Simulation/comparator_simulation.jpg)

#### Function
Compares sampled voltage against reference ladder voltages.

### Step 3: Priority Encoder

#### Block Diagram
![Priority Encoder Block](Design/02-ADC/02-Priority-Encoder/01-Block-Diagram/priority_encoder_block.jpg)

#### Schematic
![Priority Encoder Schematic](Design/02-ADC/02-Priority-Encoder/02-Schematics/priority_encoder_schematic.jpg)

#### Simulation
![Priority Encoder Simulation](Design/02-ADC/02-Priority-Encoder/03-Simulation/priority_encoder_simulation.jpg)

#### Function
Converts thermometer code generated by comparators into binary output.

### Step 4: Flash ADC Integration

#### Block Diagram
![Flash ADC Block](Design/02-ADC/04-Flash-ADC/01-Block-Diagram/flash_adc_block.jpg)

#### Schematic
![Flash ADC Schematic](Design/02-ADC/04-Flash-ADC/02-Schematics/flash_adc_schematic.jpg)

#### Simulation
![Flash ADC Simulation](Design/02-ADC/04-Flash-ADC/03-Simulation/flash_adc_simulation.jpg)

#### Result
The Flash ADC successfully converts analog input signals into digital output codes with high-speed operation enabled by regenerative latch comparators.

## Tools Used

- Cadence Virtuoso
- CMOS Analog Design Techniques
- Flash ADC Architecture

## Repository Structure

```text
Design/
|-- Comparators
|-- ADC
Report/
Result/
```

## Conclusion
Fourteen comparator architectures were designed and simulated to study their operating principles, speed, power consumption, and suitability for ADC applications. Based on the analysis, the Strong-Arm Latch Comparator was selected and integrated into a Flash ADC architecture. Simulation results validate successful comparator operation and ADC conversion functionality.
