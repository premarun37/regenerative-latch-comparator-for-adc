\# Regenerative Latch Comparator for Flash ADC



\## Overview



This project explores the design and simulation of multiple comparator architectures used in high-speed Analog-to-Digital Converters (ADCs). The study evaluates different comparator topologies and integrates the Strong-Arm Latch Comparator into a Flash ADC architecture.



The complete design flow includes:



\* Comparator architecture analysis

\* Circuit-level implementation

\* Simulation and performance verification

\* Flash ADC subsystem development

\* ADC output validation



\---



\## Objectives



\* Study various comparator architectures.

\* Compare static and dynamic comparator designs.

\* Analyze regenerative latch behavior.

\* Implement a Strong-Arm Latch Comparator.

\* Design a Flash ADC using the selected comparator.

\* Verify ADC operation through simulation.



\---



\# Comparator Architectures



\## 1. Resistive Divider Comparator



\### Block Diagram



!\[Block Diagram](Design/01-Comparators/01-Resistive-DIvider-Comparator/01-Block-Diagram/01\_Resistive\_divider\_comparator\_block\_diagram.jpg)



\### Schematic



!\[Schematic](Design/01-Comparators/01-Resistive-DIvider-Comparator/02-Schematics/01\_Resistive\_divider\_omparator\_circuit.jpg)



\### Simulation Result



!\[Simulation](Design/01-Comparators/01-Resistive-DIvider-Comparator/03-Simulation/01\_Resistive\_divider\_comparator\_simulation.jpg)



\### Working Principle



The resistive divider comparator generates a reference voltage using a resistor network. The input signal is compared against the reference voltage and the output switches according to the voltage difference.



\### Result



\* Successful threshold detection.

\* Simple architecture.

\* Higher static power consumption due to resistor network.



\---



\## 2. Charge Sharing Comparator



\### Block Diagram



!\[Block Diagram](Design/01-Comparators/02-Charge-Sharing-Comparator/01-Block-Diagram/02\_Charge\_sharing\_comparator\_block\_diagram.jpg)



\### Schematic



!\[Schematic](Design/01-Comparators/02-Charge-Sharing-Comparator/02-Schematics/02\_Charge\_sharing\_comparator\_circuit.jpg)



\### Simulation Result



!\[Simulation](Design/01-Comparators/02-Charge-Sharing-Comparator/03-Simulation/02\_Charge\_sharing\_comparator\_simulation.jpg)



\### Working Principle



The charge sharing comparator utilizes capacitor charge redistribution to determine the relationship between input and reference voltages.



\### Result



\* Reduced static power.

\* Faster operation than resistive implementations.

\* Sensitive to capacitor mismatch.



\---



\# Continue similarly for:



3\. Latch Dynamic Comparator



4\. Offset Compensated Comparator



5\. Strong Arm Latch Comparator



6\. Low Dynamic Comparator



7\. Three Stage Dynamic Comparator



8\. Two Stage Dynamic Comparator



9\. Single Tail Comparator



10\. Elzakker Comparator



11\. Modified Strong Arm Latch Comparator



12\. Voltage Sense Amplifier Comparator



13\. PMOS Preamplifier Comparator



14\. Dual Rail Double Tail Comparator



\---



\# Comparator Comparison Summary



| Comparator        | Speed     | Power    | Complexity |

| ----------------- | --------- | -------- | ---------- |

| Resistive Divider | Low       | High     | Low        |

| Charge Sharing    | Medium    | Low      | Medium     |

| Latch Dynamic     | High      | Low      | Medium     |

| Strong Arm Latch  | Very High | Very Low | Medium     |

| Double Tail       | Very High | Low      | High       |



\---



\# ADC Design Flow



The Flash ADC was designed using the Strong-Arm Latch Comparator due to its high speed and low power characteristics.



\## Step 1: Sample and Hold Circuit



\### Block Diagram



!\[Sample and Hold Block](Design/02-ADC/01-Sample-And-Hold/01-Block-Diagram/sample\_hold\_block.jpg)



\### Schematic



!\[Sample and Hold Schematic](Design/02-ADC/01-Sample-And-Hold/02-Schematics/sample\_hold\_schematic.jpg)



\### Simulation



!\[Sample and Hold Simulation](Design/02-ADC/01-Sample-And-Hold/03-Simulation/sample\_hold\_simulation.jpg)



\### Function



Samples the analog input and maintains a constant voltage during ADC conversion.



\---



\## Step 2: Strong Arm Comparator



\### Block Diagram



!\[Comparator Block](Design/02-ADC/03-Strong-Arm-Latch-Comparator/01-Block-Diagram/comparator\_block.jpg)



\### Schematic



!\[Comparator Schematic](Design/02-ADC/03-Strong-Arm-Latch-Comparator/02-Schematics/comparator\_schematic.jpg)



\### Simulation



!\[Comparator Simulation](Design/02-ADC/03-Strong-Arm-Latch-Comparator/03-Simulation/comparator\_simulation.jpg)



\### Function



Compares sampled voltage against reference ladder voltages.



\---



\## Step 3: Priority Encoder



\### Block Diagram



!\[Priority Encoder Block](Design/02-ADC/02-Priority-Encoder/01-Block-Diagram/priority\_encoder\_block.jpg)



\### Schematic



!\[Priority Encoder Schematic](Design/02-ADC/02-Priority-Encoder/02-Schematics/priority\_encoder\_schematic.jpg)



\### Simulation



!\[Priority Encoder Simulation](Design/02-ADC/02-Priority-Encoder/03-Simulation/priority\_encoder\_simulation.jpg)



\### Function



Converts thermometer code generated by comparators into binary output.



\---



\## Step 4: Flash ADC Integration



\### Block Diagram



!\[Flash ADC Block](Design/02-ADC/04-Flash-ADC/01-Block-Diagram/flash\_adc\_block.jpg)



\### Schematic



!\[Flash ADC Schematic](Design/02-ADC/04-Flash-ADC/02-Schematics/flash\_adc\_schematic.jpg)



\### Simulation



!\[Flash ADC Simulation](Design/02-ADC/04-Flash-ADC/03-Simulation/flash\_adc\_simulation.jpg)



\### Result



The Flash ADC successfully converts analog input signals into digital output codes with high-speed operation enabled by regenerative latch comparators.



\---



\# Tools Used



\* Cadence Virtuoso

\* CMOS Analog Design Techniques

\* Flash ADC Architecture



\---



\# Repository Structure



```text

Design/

├── Comparators

├── ADC

Report/

Result/

```



\---



\# Conclusion



Fourteen comparator architectures were designed and simulated to study their operating principles, speed, power consumption, and suitability for ADC applications. Based on the analysis, the Strong-Arm Latch Comparator was selected and integrated into a Flash ADC architecture. Simulation results validate successful comparator operation and ADC conversion functionality.



