# Tool Recommendations 

This section gives recommendations on open-source tools to be used in digital, analog, mixed signal, RF and photonics design flows. The intention is to provide at least two options for each flow. However, as each of the flow consists of multiple stages each using different tools, there are not always multiple independent open-source tools available. The tool recommendations are first described textually and then summarized in tables. The recommendations should be considered as open suggestions as the tool landscape constantly evolves, and it is important to monitor the state of tool projects closely.

## Digital

System Level Design

Modern SoC designs typically consist of a programmable host core orchestrating the execution and programmable task- or domain-specific accelerators. In addition, the most energy-efficient acceleration of workloads can be achieved with fixed-function accelerators. Tools for designing these components are recommended in this subsection.

RISC-V based processors and toolsets have been adopted widely in recent years, so recommendations for them are provided. **Chipyard** is recommended for generating and implementing RISC-V based cores, as it offers six different cores as a base and allows customization. Additionally, the generated cores are tapeout-proven. The toolset utilizes generic RISC-V tools.

**OpenASIP** toolset is recommended for generating task- or domain-specific, compiler programmable accelerators. The toolset generates cores based on a statically scheduled wide-issue processor template whose resources and instruction set can be customized. The instruction set is automatically adapted to new operations. They are also supported by a retargetable compiler and instruction set simulator.

HLS tools are recommended for fixed-function accelerator design. **Bambu** and **Dynamatic** are recommended, as they are the most prominent open-source HLS tools. Although they are somewhat lacking in the amount of included IP libraries and extensive verification, they can produce RTL from C/C++ inputs as well as GCC/LLVM intermediate representation formats.

**QEMU**, **Gem5** and **Renode** are recommended for system simulation. **QEMU** is a widely adopted emulation tool with extensive support for different targets. **Gem5** is a well-established simulator with support for system-level as well as microarchitecture-level simulations. It ships with a variety of component simulation models. **Renode** aims to support platform simulations including peripherals and provide testing and verification automation functionalities. **Renode** is a functional simulator and does not provide a similar level of microarchitecture modeling as **gem5**. It allows co-simulation with Verilog/SystemVerilog files.

Logic Synthesis and Physical Design (Back-End)

**OpenROAD** and **LibreLane** are recommended for running logic synthesis and physical design as they are the only two fully open-source toolsets for this purpose. They are currently highly active projects aiming to automatically take RTL designs as input, run physical design, and produce GDSII output. In the case of **OpenROAD**, **Openroad-flow-scripts** is recommended to be used for automating the flow. Below are limitations of the tools:

- **OpenROAD**: For VHDL support, the existing GHDL plugin should be used. Note: The plugin has limited support for VHDL. At least package files are not supported.

- **OpenROAD**: Systemverilog is supported via Slang plugin. Package files are not supported. SystemVerilog-2023 is not supported.

- **OpenROAD**: Detailed routing consumes a large amount of memory and time with large designs.

- **OpenROAD** & **LibreLane**: No DFT insertion support. **Difetto** is a work-in-progress **LibreLane** plugin for DFT insertion.

**Table 5.1.** Digital Design Tool Recommendations: System Level EDA Tools.

| System Level EDA Tools  |          |                                                                                                                                                     |
|-------------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type       | **Tool** | **Justification**                                                                                                                                   |
| Simulator (Prototyping) | Gem5     | Widely adopted. Wide set of component models for simulation.                                                                                        |
|                         | QEMU     | A fast, open-source system emulator that operates at a higher abstraction level than gem5, favoring execution speed over microarchitectural detail. |
|                         | Renode   | Virtual SoC simulation. Supports co-simulation.                                                                                                     |

**Table 5.2.** Digital Design Tool Recommendations: IP Design and Integration.

| IP/HDL Design/Generation and Integration                          |                  |                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                                                 | **Tool**         | **Justification**                                                                                                                                                                                                                                  |
| RISC-V core design, customization, compilation and RTL generation | Chipyard         | Generates tapeout-proven RISC-V cores. Contains generic *riscv-tools* for compilation, instruction set simulation etc.                                                                                                                             |
| ASIP design, customization, compilation and RTL generation        | OpenASIP         | Generates tapeout-proven statically scheduled cores. Includes customizable instruction set and retargetable instruction set simulator and compiler, and RTL generation. Supports C and OpenCL. No similar open-source ASIP toolsets are available. |
| Fixed-function accelerator generation                             | Bambu, Dynamatic | The most prominent HLS tools. Lack of other options.                                                                                                                                                                                               |
| IP Integration                                                    | Kactus2          | Has been used in a taped-out design. No viable alternatives.                                                                                                                                                                                       |

**Table 5.3.** Digital Design Tool Recommendations: RTL2GDSII Flow.

| RTL2GDSII Physical Implementation Flow (Logic Synthesis & Physical design) |                 |                                                                                                                                                       |
|----------------------------------------------------------------------------|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                                                          | **Tool**        | **Justification**                                                                                                                                     |
| Full Automation, Standalone                                                | OpenROAD & ORFS | Highly active projects aiming to automatically take RTL designs as input, run physical design, and produce GDSII output. Proven by multiple tapeouts. |
| Automation, Custom Integration                                             | LibreLane       | Highly active projects aiming to automatically take RTL designs as input, run physical design, and produce GDSII output. Proven by multiple tapeouts. |

**Table 5.4.** Digital Design Tool Recommendations: Synthesis, Simulation & Verification.

| Synthesis, Simulation & Verification Tools |                   |                                            |                                                                                                                     |
|--------------------------------------------|-------------------|--------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                          | **Tool**          | **Integrated/Installed with OR Framework** | **Justification**                                                                                                   |
| RTL Simulation: Verilog/SV                 | Icarus, Verilator |                                            | Both are widely adopted. Verilator seems to be under active development.                                            |
| RTL Simulation: VHDL                       | GHDL, nvc         |                                            | GHDL is a well-established simulator and nvc is an active project with support for several verification frameworks. |
| Waveform viewing                           | GTKWave, Surfer   |                                            | GTKWave is a well-established waveform viewer. Surfer aims to be highly configurable. Lack of other options.        |
| RTL Testbench Environment                  | CocoTB            |                                            | Not mandatory but enables the use of Python to write tests. Wide range of simulators supported.                     |
| Formal Verification                        | Eqy, sby          | Yosys                                      | Lack of other options.                                                                                              |
| Physical Verification: DRC, LVS            | Klayout           | OpenROAD/LibreLane                         | Default in OpenROAD. Lack of other options.                                                                         |
|                                            | Magic             | LibreLane                                  | Lack of other options.                                                                                              |
|                                            | Netgen            | LibreLane                                  | Lack of other options.                                                                                              |
| Physical Verification: ERC                 | CVC               |                                            | Lack of other options.                                                                                              |

## Analog/Mixed Signal/RF

In this chapter, the recommendations are primarily based on the **maturity of the tools** within their respective domains. Some of the tools have already been employed in real design projects using the **SKY130, GF180, and SG13G2 PDKs**, thereby demonstrating their practical capabilities. Nevertheless, additional tools are under active development; therefore, although the recommendations currently focus on two tools, the list should be regarded as **open and extensible**.

### Analog Design

**Table 5.5.** Analog Design Tool Recommendations: Schematic.

| Analog design: Schematic capture and editing                            |          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                                                       | **Tool** | **Justification**                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Integrated design tool environment for schematic capture and simulation | Xschem   | **Xschem** is a **Tcl-based**, well-established schematic editor with **multi-simulator support**. It provides symbol libraries for the **SKY130, GF180, and SG13G2 PDKs**. Within the open-source ecosystem, many analog designs developed using Xschem are actively maintained and continue to evolve. In addition, the tool closely resembles **Cadence Virtuoso** in both look and workflow, which facilitates the transition from proprietary to open-source design environments. |
| Integrated design tool environment for schematic capture and simulation | Qucs-S   | The tool is functionally similar to **Keysight ADS** and is primarily used for **RF circuit design with discrete components**. Recent updates have added support for **PDK-based elements**, improving its compatibility with analog integrated circuit design flows. Qucs-S can invoke different simulators, such as **ngspice** and **Xyce**; however, integration of additional simulators is not straightforward. The tool remains under active development.                       |

**Table 5.6.** Analog Design Tool Recommendations: Simulation.

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 11%" />
<col style="width: 64%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="3">Analog design: Simulation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Purpose/Tool Type</td>
<td><strong>Tool</strong></td>
<td><strong>Justification</strong></td>
</tr>
<tr class="even">
<td>Spice compatible<br />
circuit simulator</td>
<td>ngspice</td>
<td>An analysis of the table summarizing the features of open-source simulators indicates that <strong>ngspice</strong> is the most versatile option. Moreover, it is a well-established simulator within the open-source ecosystem and is widely used as the primary simulation engine. Ngspice supports also Verilog-A models via OSDI interface. The project is actively developed.</td>
</tr>
<tr class="odd">
<td>Analog circuit simulator based on Verilog-A</td>
<td>VACASK</td>
<td>The simulator is recommended because it <strong>natively supports Verilog-A models via the OSDI interface</strong>, which significantly improves simulation efficiency. Its <strong>modular architecture</strong>, with a clear separation between the simulation engine and device models, makes it particularly well suited to the open-source ecosystem, as models can be developed and maintained independently of the simulator core.</td>
</tr>
</tbody>
</table>

**Table 5.7.** Analog Design Tool Recommendations: Layout.

| Analog design: Layout Editor |          |                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type            | **Tool** | **Justification**                                                                                                                                                                                                                                                                                                                                                                            |
| Layout editor                | Klayout  | **KLayout** is a well-established layout editor with support for the **SKY130, GF180, and SG13G2** technologies. Its native integration of **Python and Ruby** makes the tool highly versatile and customizable. An additional advantage is support for the **PyCellStudio API**, which enables seamless migration of proprietary parametric cells. The project is under active development. |
| Layout editor                | MAGIC    | Although **Magic VLSI** is a legacy tool, it continues to be used within the open-source ecosystem. It supports the **SKY130, GF180, and SG13G2** technologies. Its highly versatile **Tcl interface** and command-line support enable straightforward integration into automated design flows. The project remains under active development.                                                |

Since PEX analysis is at the preliminary stage in the open-source domain, there are not many tools that support this feature.

**Table 5.8.** Analog Design Tool Recommendations: Parasitics Extraction.

| Analog design: PEX                                 |             |                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|----------------------------------------------------|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                                  | **Tool**    | **Justification**                                                                                                                                                                                                                                                                                                                                                                                                                         |
| A klayout compatible tool for parasitic extraction | Klayout-PEX | This tool acts as a **wrapper** around back-end tools that perform parasitic extraction. Its primary advantage is the integration with **KLayout**, along with support for **netlist reduction** options. Depending on the required **granularity of the PEX analysis**, it allows the user to select among different extraction tools and configurations to obtain either coarse or fine parasitic models. The tool is under development |
| Layout editor with PEX feature                     | MAGIC       | **Magic** includes a built-in **parasitic extraction engine** capable of extracting **series resistance** and **shunt capacitance** from the metal stack. It can be used as a **stand-alone tool** via its **Tcl interface**.                                                                                                                                                                                                             |

Since physical verification is an important step in the IC design flow, it is recommended to perform it extensively using different tools, increasing redundancy.

**Table 5.9.** Analog Design Tool Recommendations: Physical Verification.

| Analog design: Physical verification |               |                                                                                                                                                                                                                                                                                                                                                         |
|--------------------------------------|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                    | **Tool**      | **Justification**                                                                                                                                                                                                                                                                                                                                       |
| DRC/LVS                              | Klayout       | This is the **primary verification tool** used in the open-source domain for performing **design rule checking (DRC)** and **layout versus schematic (LVS)** validation, with rules implemented in **Ruby**. These capabilities have also been integrated into verification flows within **integrated design environments**, such as **RevolutionEDA**. |
| DRC/LVS                              | MAGIC+ netgen | **Magic**, together with **Netgen**, supports **layout versus schematic (LVS)** verification by extracting a netlist from the layout using Magic and subsequently comparing it with the reference netlist using Netgen.                                                                                                                                 |

### Mixed-Signal Design

As mentioned earlier, the **mixed-signal design flow** in the open-source ecosystem remains highly fragmented and requires further integration. Nevertheless, ongoing development efforts allow for the formulation of a set of **practical recommendations**, which are outlined below.

**Table 5.10.** Mixed-Signal Design Tool Recommendations: Schematic.

| AMS design: Schematic editing |          |                                                                                                                                                                                                                                                                                                                                                               |
|-------------------------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type             | **Tool** | **Justification**                                                                                                                                                                                                                                                                                                                                             |
| Schematic capture             | xschem   | **Xschem** provides partial support for **mixed-signal simulation** through integration with **ngspice/XSPICE** and **Verilator/Icarus Verilog**. It allows these tools to be invoked and the required libraries to be linked directly from the Xschem GUI, thereby improving usability for **AMS design** and abstracting low-level command-line operations. |

**Table 5.11.** Mixed-Signal Design Tool Recommendations: Simulation.

<table>
<colgroup>
<col style="width: 23%" />
<col style="width: 13%" />
<col style="width: 62%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="3">AMS design: Simulation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Purpose/Tool Type</td>
<td><strong>Tool</strong></td>
<td><strong>Justification</strong></td>
</tr>
<tr class="even">
<td>Spice compatible circuit simulator</td>
<td>Ngspice +<br />
XSPICE + verilator/iverilog</td>
<td><strong>Ngspice</strong>, together with the <strong>XSPICE code model library</strong>, supports <strong>mixed-signal design</strong> using an <strong>analog-on-top</strong> approach. It also enables simulation of digital blocks compiled from <strong>behavioral Verilog HDL</strong> descriptions.</td>
</tr>
<tr class="odd">
<td>VerilogAMS and Spice circuit simulator</td>
<td>Gnucap</td>
<td><strong>Gnucap</strong> is currently the only simulator that natively supports <strong>mixed-mode simulation</strong> by handling both <strong>Verilog-AMS models and SPICE</strong> within a single netlist. The project targets <strong>Verilog-AMS 2.4 LRM</strong> compatibility and already implements a large subset of the language features and device primitives.</td>
</tr>
</tbody>
</table>

**Table 5.12.** Mixed-Signal Design Tool Recommendations: Physical Implementation.

| AMS design: Physical Implementation |          |                                                                                                                                                                                                                                                                                                                               |
|-------------------------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                   | **Tool** | **Justification**                                                                                                                                                                                                                                                                                                             |
| Place and route tool                | OpenROAD | The **OpenROAD** tool supports the use of **macros**, enabling its application to the physical implementation of **mixed-signal circuits** using a **digital-on-top** approach. In this context, the analog subsystem can be abstracted as a macro and represented using standard data formats such as **LIB, LEF, and GDS**. |
| Layout editor                       | KLayout  | **KLayout** can be used in the mixed signal design at the physical implementation stage, while using **an analog-on-top** approach.                                                                                                                                                                                           |

**Table 5.13.** Mixed-Signal Design Tool Recommendations: Macro Abstraction.

| AMS: Macro abstraction |          |                                                                                                        |
|------------------------|----------|--------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type      | **Tool** | **Justification**                                                                                      |
| Characterization tool  | lc-time  | A **tool for analog circuit characterization** and for generating **Liberty (.lib) files**.            |
| Layout editor          | Magic    | **Magic** is capable of writing an abstract LEF file from a GDS which is useful for macro abstraction. |

### Radio Frequency Design

Similarly to the AMS flow, the **RF design flow** remains fragmented and lacks integration. The release of the **SG13G2 PDK** served as a significant stimulus, after which many tools improved their capabilities for **RF circuit design**.

**Table 5.14.** Radio Frequency Design Tool Recommendations: Schematic.

| RF design: Schematic capture                                            |          |                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                                                       | **Tool** | **Justification**                                                                                                                                                                                                                                                                                                            |
| Integrated design tool environment for schematic capture and simulation | Qucs-S   | Since **Qucs-S** closely resembles **Keysight ADS**, a dedicated RF design environment, it is recommended as a **primary schematic editor and design tool** for RF applications. It supports the **ngspice** and **Xyce** simulators, provides **SG13G2 PDK** elements, and enables **CDL netlisting** for LVS verification. |
| Integrated design tool environment for schematic capture and simulation | Xschem   | Since **Xschem** is well established within the **open-source IC design community**, it can also be used as a **schematic capture and design environment** for **mmWave circuits**.                                                                                                                                          |

**Table 5.15.** Radio Frequency Design Tool Recommendations: Simulator.

| RF design: Simulator             |          |                                                                                                                                                                                                  |
|----------------------------------|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type                | **Tool** | **Justification**                                                                                                                                                                                |
| Spice simulator with RF features | ngspice  | Currently, it offers the **richest set of features** required for **mmWave design**, including **S-parameter simulation with noise analysis** and **Touchstone file support**.                   |
| Modern Verilog-A simulator       | VACASK   | A **modern Verilog-A circuit simulator** targeting **analog and RF circuit design**. Although alternatives exist, this project features a **clear roadmap** and **strong development momentum**. |

**Table 5.16.** Radio Frequency Design Tool Recommendations: Layout.

| RF design: Layout Editor |            |                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|--------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type        | **Tool**   | **Justification**                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| mmWave layout tool       | KLayout    | **KLayout** is a well-established layout editor with support for the **SKY130, GF180, and SG13G2** technologies. Its native integration of **Python and Ruby** makes the tool highly versatile and customizable. An additional advantage is support for the **PyCellStudio API**, which enables seamless migration of proprietary parametric cells. The project is under active development                                                                 |
| mmWave layout tool       | GDSFactory | **GDSFactory** was originally developed to support **photonic circuit design**. It is **Python-based**, which enables high scriptability and provides a high degree of freedom in exploring the design space. Since the geometry of individual elements plays a critical role in **mmWave circuit design**, an automated, script-driven approach can significantly aid layout optimization. **GDSFactory** is well suited to support such design scenarios. |

There are **limited options** available for **EM analysis of mmWave circuits**. Because EM simulations are **computationally intensive**, the choice of simulator depends on the **complexity of the analysis**, the **design size**, and the **available computational resources**.

**Table 5.17.** Radio Frequency Design Tool Recommendations: EM Simulation.

| RF design: EM simulations  |            |                                                                                                                                                                                                                                       |
|----------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type          | **Tool**   | **Justification**                                                                                                                                                                                                                     |
| Electromagnetic simulation | OpenEMS    | An **FDTD (finite-difference time-domain)** electromagnetic solver suitable for **circuit-level simulations**, offering a good balance between **accuracy and computational resource usage**.                                         |
| Electromagnetic simulation | AWS Palace | FEM (finite elements in frequency domain) since the FEM method is more resource hungry, it is recommended for small circuits. It has more flexibility at meshing stage which translates to better accuracy for the same problem size. |

## Integrated Photonics

This section contains a list of various tools selected as recommended components for open-source PIC design flow. The main goal in tool selection was to cover various simulation methods and functionality. The integration between the tools is currently quite poor, but we consider the selected tools to be most suitable to support such integration in future.

The tables below contain the tools which are grouped by the design step.

**Table 5.18.** Integrated Photonics Design Tool Recommendations: Device-Level Simulation.

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 11%" />
<col style="width: 64%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="3">Device-level simulation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Purpose/Tool Type</td>
<td><strong>Tool</strong></td>
<td><strong>Justification</strong></td>
</tr>
<tr class="even">
<td>FEM simulators</td>
<td><strong>FEMWELL<br />
Palace</strong></td>
<td>Applicability to photonic applications, and integrations with other software.</td>
</tr>
<tr class="odd">
<td>Other simulator types</td>
<td><strong>MPB<br />
Meep<br />
Meow<br />
Tiny3D</strong></td>
<td>Documentation quality, applicability to photonics domain, and integrations with other software.</td>
</tr>
</tbody>
</table>

**Table 5.19.** Integrated Photonics Design Tool Recommendations: Circuit Simulation.

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 11%" />
<col style="width: 64%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="3">Circuit simulation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Purpose/Tool Type</td>
<td><strong>Tool</strong></td>
<td><strong>Justification</strong></td>
</tr>
<tr class="even">
<td>S-parameter circuit simulator</td>
<td><strong>SAX<br />
Simphony</strong></td>
<td>Good integration with other software.</td>
</tr>
<tr class="odd">
<td>Schematic editor and simulator</td>
<td><strong>Qucs-S</strong></td>
<td>The tool resembles Keysight ADS environment and was shown to be useful in photonic applications, though with some custom tweaking.</td>
</tr>
<tr class="even">
<td>Comprehensive photonic circuit simulator</td>
<td><strong>Phisim</strong></td>
<td>Allows amplifier simulation</td>
</tr>
</tbody>
</table>

There are limited options for the *layout tools* which have a scripted approach, have multiple PDKs available for them, and allow device or component abstraction level (beyond drawing polygons). The listed tools are de-facto standard in the PIC design community.

**Table 5.20.** Integrated Photonics Design Tool Recommendations: Layout.

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 11%" />
<col style="width: 63%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="3">Layout</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Purpose/Tool Type</td>
<td><strong>Tool</strong></td>
<td><strong>Justification</strong></td>
</tr>
<tr class="even">
<td>Layout editor</td>
<td><strong>Nazca Design<br />
GDSFactory</strong></td>
<td>Comprehensive script-based (python) design tools. Allow creation of own component libraries. Have integrations with multiple 3<sup>rd</sup>-party tools.</td>
</tr>
<tr class="odd">
<td>Layout viewer</td>
<td><strong>KLayout</strong></td>
<td>De-facto standard viewer for PIC design. Contains PDK implementation for one of the open-source PDKs (SiEPIC).</td>
</tr>
</tbody>
</table>

There are limited open-source options available for physical verification. The existing tools, however, provide quite a comprehensive functionality for DRC and LVS.

**Table 5.21.** Integrated Photonics Design Tool Recommendations: Physical Verification.

| Physical verification |                |                                                                                                             |
|-----------------------|----------------|-------------------------------------------------------------------------------------------------------------|
| Purpose/Tool Type     | **Tool**       | **Justification**                                                                                           |
| DRC / LVS engine      | **KLayout**    | Powerful engine with own scripting language and viewing capability. Can be used in both GUI and batch mode. |
| DRC / LVS engine      | **GDSFactory** | Integrated with design environment. Allows Python scripting of DRC / LVS.                                   |
