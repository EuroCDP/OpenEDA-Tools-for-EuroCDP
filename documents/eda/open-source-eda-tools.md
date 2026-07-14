# Open-Source EDA Tools

This section describes the open-source tools used in each of the flows. First, considerations about selecting and integrating open-source projects are discussed. Second, descriptions of the tools are given in tables. Third, feature lists and functionalities of the tools are compared in another set of tables.

## Open-Source-Related Considerations

Open-source tools vary in the way they are owned, managed, and developed. Some of the factors related to it are described below.

First and most obvious consideration is the project license. They range from very permissive (MIT, BSD) to licenses which protect open-source nature of the code including its derivatives (GPL). The license conditions may also propagate onto the output created with the toll, such as IPs or PDKs. Therefore, the license should be carefully studied before including a tool in a concrete workflow.

Open-source projects differ in the provided support level, documentation quality, pace of bug fixing and introduction of new features. This depends on the maturity of the project, as well as size and availability of the maintenance team. It is possible to evaluate these characteristics by checking the code repository metrics such as number of project stars, forks, maintainers, number of long-pending issues, and frequency of releases.

Finally, there is a significant difference between open-source projects that are "published source" versus "collaborative open source". In the first case, anyone can clone, modify, repackage, etc. the code, but the publishers do not actively encourage (or handle) feedback and feature requests. In collaborative open-source projects, the maintainers actively encourage feedback through, for example, a public issue tracker and GitHub pull requests (to accept code fixes from external parties). For some use cases, relying on "published source" tools could be considered a risk because these types of projects run a higher risk of becoming abandoned by the owners, or at the very least tend to lag behind to latest innovations and developments.

## Digital

As semiconductor technology advances, design challenges such as power optimization, efficiency, cost, and size have become increasingly significant. To overcome such challenges, specialized EDA tools are applied at each stage of the design flow. Over the past few decades, a few major EDA companies have dominated the market, but due to the high cost of licensing, open-source alternatives are increasingly gaining popularity. Various open-source EDA tools and frameworks are listed below that cover the complete digital design flow, from system-level architectural exploration to tape-out. The tools are ordered from higher levels of abstraction in the ASIC design flow, starting with system-level design and multi-feature frameworks and down to tape-out or more specialized tools with less features. Some tools have multiple functionalities that can be used in system level architectural design exploration to RTL verification, hence if the tools is already defined in earlier section such as at system level, then it's not further included and defined in later sections such as at RTL verification.

### Tool descriptions

Tool descriptions are summarized in Table 2.1. Tools that are closely related or share similar features are grouped within the same section. In addition to EDA tools, the table also includes relevant frameworks and supporting toolchains.

> **Table 2.1.** Digital Design Tool Descriptions

<table>
<colgroup>
<col style="width: 21%" />
<col style="width: 78%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2">Tools Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="2">System-Level EDA</td>
</tr>
<tr class="even">
<td colspan="2"><p>System Design &amp; Architecture Exploration: Simulator, Virtual Prototyping</p>
<p>Explore architecture choices, performance, and memory hierarchy before RTL is written.</p></td>
</tr>
<tr class="odd">
<td>FireSim</td>
<td>FPGA-accelerated full-system hardware simulation platform, enabling RTL validation and co-simulation with cycle-accurate models, from single-board setups to large-scale cloud FPGA deployments.</td>
</tr>
<tr class="even">
<td>Gem5</td>
<td>Full-system, modular, multi-ISA computer architecture simulator for design-space exploration. This platform is intended to explore computer system architecture, including both system-level designs and processor microarchitecture. It is primarily used to assess new hardware designs, test system software modifications, and evaluate optimizations applied at compile-time or run-time.</td>
</tr>
<tr class="odd">
<td>GVSoC</td>
<td>An open-source simulator targeting the PULP RISC-V architectures that can simulate complex full-platforms, including multicore, multi-memory levels (i.e., on- and off-chip), multi I/O peripherals, and accelerators, laying the bases of a real DSE for IoT embedded systems.</td>
</tr>
<tr class="even">
<td>QEMU</td>
<td>Machine &amp; user space emulator and virtualizer supporting multiple CPU architectures, capable of full system or user-mode emulation entirely in software.</td>
</tr>
<tr class="odd">
<td>Renode</td>
<td>Generic and open-source machine emulator that aims to simulate platforms consisting of processor cores and peripherals for multi-node embedded networks, enabling a scalable workflow for building reliable, tested, and secure IoT systems.</td>
</tr>
<tr class="even">
<td>Structural Simulation Toolkit (SST)</td>
<td>Explore highly concurrent systems where the ISA, microarchitecture, and memory interact with the programming model and communications system.</td>
</tr>
<tr class="odd">
<td>VPSim</td>
<td>Virtual Prototyping Simulator is a design environment that enables rapid design space exploration, virtual prototyping, and high-level validation, during the design phase of complex digital systems. Its simulation method separates processors and memory hierarchy for efficient design space exploration.</td>
</tr>
<tr class="even">
<td>MuchiSim</td>
<td>Simulator framework for analysis of PPA and cost of multi-node multi-chiplet tile-based manycore designs.</td>
</tr>
<tr class="odd">
<td>noxim</td>
<td>Network on Chip Simulator.</td>
</tr>
<tr class="even">
<td>Ramulator</td>
<td>Modular, and extensible cycle-accurate DRAM simulator.</td>
</tr>
<tr class="odd">
<td>SimEng</td>
<td>HPC Simulation Engine. Fast, easily modifiable, cycle-accurate processor simulator framework</td>
</tr>
<tr class="even">
<td>Spike</td>
<td>RISC-V ISA Simulator.</td>
</tr>
<tr class="odd">
<td>SystemC (TLM)</td>
<td>Transaction Level Modeling (TLM) is a standard interface for SystemC, a framework for virtual prototyping that enables modeling and simulation for architectural analysis, SW development, performance analysis, and HW verification.</td>
</tr>
<tr class="even">
<td colspan="2">Power Estimation</td>
</tr>
<tr class="odd">
<td>McPAT</td>
<td>Architectural integrated timing, area and power modeling framework for multicore and core processors.</td>
</tr>
<tr class="even">
<td colspan="2">IP / HDL Design, Generation and Integration</td>
</tr>
<tr class="odd">
<td>Switchboard</td>
<td>Communication and HW/SW Co-simulation framework for communication between diverse hardware models, including RTL simulations, FPGA-based RTL, and fast software models.</td>
</tr>
<tr class="even">
<td>FuseSoC + Edalize</td>
<td><p>FuseSoC: open-source package manager and build tool for reusable IP cores and SoCs.</p>
<p>Edalize: Backend abstraction library for EDA tools, used with FuseSoC to generate simulator/flow scripts.</p></td>
</tr>
<tr class="odd">
<td>Kactus2</td>
<td>An open-source IP-XACT-based design tool for embedded systems and SoCs. It provides a metadata-driven environment for sketching, packaging, integrating, and generating both hardware and software for system designs. It supports creating and managing IP libraries in the IEEE 1685/IP-XACT standard format, helps in assembling design hierarchies. The tool facilitates reuse of IPs, IP integration, and maintaining consistency in design metadata.</td>
</tr>
<tr class="even">
<td>MESSY</td>
<td>An open-source framework that integrates functional RISC-V simulation (achieved with GVSoC) with SystemC-AMS (used to model extra-functional aspects, in detail, power storage and distribution). Allows to perform a DSE that is dependent on the mutual impact between functional and extra-functional aspects like power consumption.</td>
</tr>
<tr class="odd">
<td colspan="2">Front-End: Logic Design (HDL) &amp; Verification</td>
</tr>
<tr class="even">
<td colspan="2">HDL and HLS Framework, Domain - specific IP Generator (HW-SW Co-design)</td>
</tr>
<tr class="odd">
<td>CIRCT</td>
<td>Circuit Intermediate Representations (IR) Compilers and Tools, an open-source HW compiler infrastructure and HW generation HLS tools built using MLIR.</td>
</tr>
<tr class="even">
<td>Dynamatic</td>
<td>HLS compiler that produces synchronous dynamically scheduled circuits from C/C++ code with dynamic scheduling. It generates synthesizable RTL with better and similar performance to commercial HLS tools in some specific areas. Its fully automated compilation flow is based on LLVM.</td>
</tr>
<tr class="odd">
<td>PandA-bambu</td>
<td>High-level synthesis (HLS) Framework that enables research on HW/SW co-design. It includes methodologies supporting research on HLS of hardware accelerators, parallelism extraction for embedded systems, hardware software partitioning, and mapping.</td>
</tr>
<tr class="even">
<td>PipelineC</td>
<td>Open-source C-like HDL with HLS-like automatic pipelining as a language construct/compiler feature. It can be partially compiled by gcc/llvm for basic functional verification, simulation and compiler produces synthesizable VHDL.</td>
</tr>
<tr class="odd">
<td>XLS</td>
<td>Accelerated HW synthesis HLS framework that produce synthesizable designs (Verilog/SV) that's aiming to be SDK enabling rapid development of hardware IP. It is still experimental. It supports both optionally pipelined functions with simple wire-based interfaces and concurrent processes.</td>
</tr>
<tr class="even">
<td>OpenASIP</td>
<td>Application Specific Integrated Processor (ASIP) toolset for designing and programming compiler-programmable accelerators. Initially based on Transport Triggered Architecture (TTA), it also supports RISC-V co-design. The toolset provides a retargetable flow from high-level programs to synthesizable RTL (VHDL/Verilog) and parallel binaries, with customization of register files, function units, operations, and interconnects. It supports simulation, architectural exploration, and RTL generation, enabling optimized, application-specific processors, and the cost metrics typically involve area, performance, and/or power consumption.</td>
</tr>
<tr class="odd">
<td>Amaranth (nMigen)</td>
<td>Toolchain for developing hardware based on synchronous digital logic using the Python along with SoC toolkit and more, with an objective to simplify hardware design complicity with reusable components. Amaranth toolchain consists of Amaranth HDL, standard library, simulator, build system. Verilog, SV and VHDL can be integrated into its flow or Amaranth code into Verilog based design flow.</td>
</tr>
<tr class="even">
<td>Chipyard</td>
<td>Open-source agile integrated SoC design framework that supports hardware development for RISC-V-based systems. It consists of collections of tools and libraries including processors, accelerators, memory subsystems, and peripherals, and provides tooling for simulation. Chipyard unifies hardware generation (using Chisel and FIRRTL), simulation (software and hardware-accelerated), and system-level experimentation, enabling designers to build complete SoCs with reusable IP components.</td>
</tr>
<tr class="odd">
<td>Chisel</td>
<td>Open-source Scala based new HDL is used to design advanced reusable, parameterizable digital electronics and circuits at RTL level for ASIC and FPGA systems. It can generate high speed C++ based cycle accurate software simulator or low-level synthesizable Verilog design for synthesis, place and route.</td>
</tr>
<tr class="even">
<td>Py2HWSW</td>
<td>Python framework for HW/SW co-design, project management, flow automation, and Verilog generation. It generates lint-friendly and portable Verilog code that can be ported seamlessly between FPGA and ASIC flows.</td>
</tr>
<tr class="odd">
<td>IMPRESS</td>
<td>IMPRESS (IMplementation of Partial REconfigurable SystemS) is an open-source reconfiguration tool for implementing multi-grain reconfigurable systems in Xilinx Series 7 FPGAs and Zynq-7000 SoC.</td>
</tr>
<tr class="even">
<td>bsg_fakeram</td>
<td>Generate black-boxed SRAMs</td>
</tr>
<tr class="odd">
<td>Lake</td>
<td>Framework that generates synthesizable memory modules from high level specification and widely available memory macros. It consists of generalized hardware modules aimed at memory controller designs.</td>
</tr>
<tr class="even">
<td>OpenRAM</td>
<td>Python-based SRAM generator for ASICs that creates layouts, netlists, timing and power models, placement and routing information, and all necessary views for integrating SRAM into ASIC designs.</td>
</tr>
<tr class="odd">
<td>RgGen</td>
<td>Register Generator. Automatically generate source code for control and status register (CSR) such as SystemVerilog RTL, UVM register model, C header file, wiki doc and human readable format register map specification. Supports standard bus protocols.</td>
</tr>
<tr class="even">
<td colspan="2">RTL Compilation / Simulation (Optionally Synthesis)</td>
</tr>
<tr class="odd">
<td>essent</td>
<td>(Essential Signal Simulation Enabled by Netlist Transformation) High-performance RTL(FIRRTL) simulator (cycle-accurate RTL simulators), incorporates various optimizations for improving performance which can be activated or deactivated with command line option.</td>
</tr>
<tr class="even">
<td>GHDL</td>
<td>VHDL analyzer (analyze and elaborate), compiler, simulator, and experimental synthesizer. Full support for 1987,1993, 2002 version of IEEE 1076 VHDL standard, and partial support for 2008 and 2019 revisions, and partial support of PSL (Property Specification Language). Can handle large design, comprehensive tool for designing, testing, simulation, verification and partially synthesizing the VHDL code. Supports Co-simulation typically with C/C++/SystemC supported via Verilog Procedural Interface (VPI) and VHDL Programming Interface (VHPI). Can be integrated seamlessly with other popular open-source EDA tools for streamlining simulation and synthesis workflows. Support OSVVM, UVVM and VUnit testing and verification framework.</td>
</tr>
<tr class="odd">
<td>Icarus Verilog</td>
<td>Verilog compiler and simulator, intended to compile all Verilog HDL as per IEEE 1364 standard but not there yet. Also supports SystemVerilog partially and some of its extensions.</td>
</tr>
<tr class="even">
<td>NVC</td>
<td>VHDL compiler and simulator. Supports 1993, 2000, 2002 revisions of VHDL and almost all of VHDL-2008 with exception of PSL and experimental support for Verilog and VHDL-2019 are being developed. Supports OSVVM, UVVM, VUnit and cocotb verification and testing frameworks, and subset of VHPI.</td>
</tr>
<tr class="odd">
<td>Surelog</td>
<td>SystemVerilog 2017 Pre-processor, Parser, elaborator, UHDM (Universal Hardware Data Model) compiler. Provides IEEE Design/TB C/C++ VPI and Python AST API. Aiming for a complete SystemVerilog 2017 frontend: a preprocessor, a parser, elaborator for both design and testbench, supporting all opensource cores. Can be used by Linter, Simulator, Synthesis tools and Formal tools. It can either be developed as plugins or frontend as an intermediate step for compilation flows.</td>
</tr>
<tr class="even">
<td>Synlig</td>
<td>SystemVerilog synthesis tool which uses Surelog as a SystemVerilog 2017 frontend (preprocessor, parser, elaborator) with Yosys as a synthesis framework. Also available as Yosys plugin.</td>
</tr>
<tr class="odd">
<td>Verilator</td>
<td>Verilog/SystemVerilog simulator, compiler and lint system. Its package converts Verilog and SV HDL design to C++/SystemC model after compilation which can be executed.th. Optionally insert assertion checks, and coverage analysis points. With recent developments, it can also parse UVM code and compile some UVM testbenches. Usually for compilation and faster optimization of code which is then wrapped into C++/SystemC or for high-speed simulation of design. Supports cocotb, C++/SystemC, UVM (Universal Verification Methodology) testbench and verification framework.</td>
</tr>
<tr class="even">
<td colspan="2">Waveform Viewer</td>
</tr>
<tr class="odd">
<td>fstdumper</td>
<td>Verilog VPI module to dump FST (Fast Signal Trace) databases. Aiming to provide unified VPI modules that work across most simulators with strong VPI support to dump simulation waveform in .fst format which can be viewed using GTKWave.</td>
</tr>
<tr class="even">
<td>GTKWave</td>
<td>Full featured GTK+ based waveform viewer for large system or designs that read FST, GHW, LXT, LXT2, VZT and standard Verilog VCD/EVCD files. Primarily used for debugging Verilog or VHDL simulation models, specially designed for post simulation analysis of dumpfiles rather than real time interaction during simulation. Allows visualization of both analog and digital signals.</td>
</tr>
<tr class="odd">
<td>simview</td>
<td>Text-based SystemVerilog design browser and waveform viewer. Run over SSH connection, intuitive control of UI. Generally, for debugging and analyzing SystemVerilog HW design and limited support for non-synthesizable testbench code. Features with full design parsing &amp; elaboration powered by slang, trace signal drivers/loads, support VCD &amp; FST (format written by Verilator) waveform, automatic or manual matching of wave file hierarchy to design hierarchy and send signals from source code to wave &amp; vice-versa.</td>
</tr>
<tr class="even">
<td>Sooty</td>
<td>Graphical command-line tool for visualizing vdc waveforms from hardware simulations, as an alternative to GTKWave. Lightweight, easy to use, leverage modern terminal features to provide clean graphical display with customizable display style.</td>
</tr>
<tr class="odd">
<td>Surfer</td>
<td>Extensible and snappy waveform viewer with web interface supporting VCD, FST and GHW as well as memory transaction format FTR.</td>
</tr>
<tr class="even">
<td colspan="2">Linter</td>
</tr>
<tr class="odd">
<td>PySlint</td>
<td>Python (pyslang) based SystemVerilog linter for testbenches, UVM, DPI, functional coverage, RTLI and SVA.</td>
</tr>
<tr class="even">
<td>SVA Lint</td>
<td>Linter for SystemVerilog Assertions (SVA). Minimalist linter designed to style and consistency rules for SystemVerilog code which is based on BYOL (Build Your Own Linter) that allows users to define custom linting rules for specific needs. It is flexible and extensible.</td>
</tr>
<tr class="odd">
<td>svlint</td>
<td>SystemVerilog linter compliant with IEEE1800-2017, based on sv-parser that can be integrated into text editor.</td>
</tr>
<tr class="even">
<td>TerosHDL</td>
<td>Toolbox for HDL(ASIC/FPGA) developers, offering VHDL and Verilog/SystemVerilog IDE support, including error and style linting, code formatting, code snippet &amp; grammar checking, templates generation, dependency, automatic documentation, state-machine visualization (design &amp; viewing), and hierarchy, dependency and schematic viewing. Also, supports tools such as GHDL, Verilator, Icarus Verilog, Yosys, VUnit, and cocotb. Example Support VSG as VHDL style linter, and Verible ad Verilog/SV style linters.</td>
</tr>
<tr class="odd">
<td>Verible</td>
<td>SystemVerilog developer tools, including parser, style-linter, formatter and language server. Easy to integrate with GitHub.</td>
</tr>
<tr class="even">
<td colspan="2">Formal Verification</td>
</tr>
<tr class="odd">
<td>ABC</td>
<td>A System for sequential logic synthesis and formal verification. It can also optimize, map and retime industrial gate-level designs with 100K gates.</td>
</tr>
<tr class="even">
<td>AutoCC</td>
<td>Frontend for SymbiYosys (SBY) to automatically discover covert channels in time-shared hardware.</td>
</tr>
<tr class="odd">
<td>AutoSVA</td>
<td>Tool that automatically generates formal property verification testbenches and SVA properties for unit-level RTL verification.</td>
</tr>
<tr class="even">
<td>cvc5</td>
<td>Formal verification tool, included in Yosys or SymbiYosys. It is an automatic theorem prover for Satisfiability Modulo Theories (SMT) problem and also provides Syntax-Guided Synthesis (SyGuS). It is 5<sup>th</sup> generation in Cooperating Validity Checker (CVC) family (CVC, CVC Lite, CVC3, CVC4).</td>
</tr>
<tr class="odd">
<td>eqy</td>
<td>Equivalence checking with Yosys, a tool for formal verifications to ensure functionality of design is not altered by synthesis tool.</td>
</tr>
<tr class="even">
<td>mcy</td>
<td>Mutation coverage with Yosys to improve test coverage, a coverage metric for testbenches. Filters false positives with formal equivalence checks, can be interfaced with other formal tools.</td>
</tr>
<tr class="odd">
<td>SBY</td>
<td>Front-end for Yosys-based formal hardware verification flows. It provides flows for bounded verification of safety properties (assertions), unbounded verification of safety properties, generation of testbench from cover statements, and verification of liveness of properties.</td>
</tr>
<tr class="even">
<td colspan="2">Verification &amp; Testing Framework</td>
</tr>
<tr class="odd">
<td>cocotb</td>
<td>Testbench environment for verifying VHDL and SystemVerilog RTL using Python. Fast, easy and reusable.</td>
</tr>
<tr class="even">
<td>OSVVM</td>
<td>Open-source VHDL verification methodology, VHDL verification framework, utility library, verification component library, and simulator independent scripting flow. It includes capability for Constrained Random, Functional Coverage, Scoreboards, FIFOs, Memory Models, error logging and reporting, and message filtering. Capable for Co-simulation and equivalent to SystemVerilog’s UVM for VHDL</td>
</tr>
<tr class="odd">
<td>PyUVM</td>
<td>Universal Verification Methodology implemented in Python instead of SystemVerilog. pyuvm uses cocotb to interact with simulators and schedule simulation events.</td>
</tr>
<tr class="even">
<td>UVVM</td>
<td>Universal VHDL Verification Methodology and Library for structured VHDL-based testbenches for reusability, maintainability and extensibility. Features include advance &amp; enhanced randomization, functional &amp; specification coverage, monitors, error injection, scoreboards, transactions, verbosity control, specification coverage, checkers, alert handling and logging.</td>
</tr>
<tr class="odd">
<td>SVUnit</td>
<td>Test framework for Verilog and SystemVerilog code for ASIC and FPGA developers. It is automated, fast, and lightweight.</td>
</tr>
<tr class="even">
<td>VUnit</td>
<td>Unit testing framework for VHDL and SystemVerilog. Usually for continuous and automated testing</td>
</tr>
<tr class="odd">
<td colspan="2">Design for Testability (DFT)</td>
</tr>
<tr class="even">
<td>ATALANTA</td>
<td>Automatic test pattern generator for stuck-at faults in combinational circuits</td>
</tr>
<tr class="odd">
<td>Fault</td>
<td>Automatic test pattern generation for netlists, scan chain stitching, and synthesis scripts. (Difetto (ALPHA))</td>
</tr>
<tr class="even">
<td>Fenice</td>
<td>Customizable fault-simulation and gate-level editing library for sequential circuits.</td>
</tr>
<tr class="odd">
<td>HOPE</td>
<td>Fault simulation and test pattern generation in digital circuits.</td>
</tr>
<tr class="even">
<td colspan="2">Physical Design &amp; Verification (Back-End)</td>
</tr>
<tr class="odd">
<td colspan="2">RTL2GDS / netlist GDS</td>
</tr>
<tr class="even">
<td>OpenROAD FlowScript</td>
<td>Autonomous, open-source tool chain for digital SoC layout generation, focusing on the RTL-to-GDSII phase of system-on-chip design. digital design. Aiming to bring down the barriers of cost, expertise and unpredictability. Addition to open PDK, it also supports proprietary platforms: GF55, GF12, Intel22, Intel16 and TSMC65. It consists of several tools from synthesis to signoff phase of physical implementation.</td>
</tr>
<tr class="odd">
<td>LibreLane</td>
<td>Extensible digital RTL2GDS flow, successor to OpenLane. It is ASIC infrastructure library based on various components including OpenROAD, Yosys, Magic, Netgen, CVC, KLayout and custom scripts for design exploration and optimization.</td>
</tr>
<tr class="even">
<td>Silicon Compiler</td>
<td>Modular build system for hardware. It design languages are C, Verilog, SV, VHDL, Chisel, Migen/Amaranth, Bluespec, MLIR. Various RTL to GDSII tools are supported and can be integrated to run the flow.</td>
</tr>
<tr class="odd">
<td>mflowgen</td>
<td>Flow management framework for digital ASIC design, automate and orchestrate tool flows from RTL to GDSII, integrating multiple EDA tools in a flexible, modular pipeline.</td>
</tr>
<tr class="even">
<td colspan="2">Synthesis</td>
</tr>
<tr class="odd">
<td>Yosys</td>
<td>OpenVerilog RTL synthesis suite, currently supports Verilog-2005, some subsets of VHDL and SV via plugins. Targets the SkyWater 130nm open source PDK for fully open source ASIC design, also perform formal verification. Integrated into many RTL”GDSII flow tools as synthesis tool.</td>
</tr>
<tr class="even">
<td>LSOracle</td>
<td>Framework developed on the top of EPFL logic synthesis libraries to unlock efficient logic manipulation by using different logic optimizers. Input:RTL (Verilog/flattened) or BLIF/gate-level netlist from Yosys</td>
</tr>
<tr class="odd">
<td>Naja eda</td>
<td>Structural Netlist API for EDA post synthesis flow development</td>
</tr>
<tr class="even">
<td colspan="2">Floorplan, Place &amp; Route</td>
</tr>
<tr class="odd">
<td>Coriolis</td>
<td>Free database, placement and routing tool for VLSI design. Its main components are the Hurricane database, the Etesian placer and the Katana router.</td>
</tr>
<tr class="even">
<td>LibrEDA</td>
<td>Placement algorithms, software framework for the physical design of silicon chips to simplify development of place and route tools.</td>
</tr>
<tr class="odd">
<td>Qrouter</td>
<td>Multi-level, over-the-cell maze router.</td>
</tr>
<tr class="even">
<td>Qflow</td>
<td>Digital synthesis flow using Verilog or VHDL for complete ASIC flow.</td>
</tr>
<tr class="odd">
<td>RePIAce</td>
<td>Global placement tool with features: analytical and nonlinear placement algorithm, support mixed size placement mode, support fast image drawing modes.</td>
</tr>
<tr class="even">
<td>DREAMPlace</td>
<td>Deep learning toolkit-enabled VLSI placement, run on both CPU and GPU. It integrates a GPU-accelerated detailed placer, ABCDPlace. Multi-threaded CPU and optional GPU acceleration support for detailed placement.. LEF/DEF support as input/output. Python binding and access to C++ placements database. Improved efficiency for wirelength and density operators from TCAD extension. Support moveable macro, support time optimization in global placement, integrate OpenTimer for static timing analysis.</td>
</tr>
<tr class="odd">
<td colspan="2">CTS</td>
</tr>
<tr class="even">
<td>TritonCTS 2.0</td>
<td>TritonCTS automatically generates a buffered clock tree, used in OpenROAD.</td>
</tr>
<tr class="odd">
<td colspan="2">Layout Editor, Physical verification: Netlist (Compare, verification)</td>
</tr>
<tr class="even">
<td>Glade</td>
<td>Glade is GTK+ Layout Design Editor, Gds, Lef And Def Editor – layout and schematic editor, DRC, extraction, LVS.</td>
</tr>
<tr class="odd">
<td>Klayout</td>
<td>Mask layout tool that GDSII viewer and editor, finla layout verification, support DRC, LVS. Used in many RTL2GDSII tool chains.</td>
</tr>
<tr class="even">
<td>Magic</td>
<td>IC layout tool, support extraction, DRC.</td>
</tr>
<tr class="odd">
<td>IRSIM</td>
<td>Switch-level simulation.</td>
</tr>
<tr class="even">
<td>Netgen</td>
<td>Netlist management system: LVS tool for comparing SPICE or Verilog netlists.</td>
</tr>
<tr class="odd">
<td>CVC</td>
<td>Circuit Validity Checker. Voltage aware ERC checker for CDL netlists.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td colspan="2">Power estimation &amp; Timing Analyzer</td>
</tr>
<tr class="even">
<td>OpenSTA</td>
<td>Gate level static timing verifier, analyzer.</td>
</tr>
<tr class="odd">
<td>OpenTimer</td>
<td>High-Performance Static Timing Analysis Tool for VLSI Systems</td>
</tr>
</tbody>
</table>

### Feature comparison

Various available open-source EDA tools that are used in digital system design with their features are listed in the following tables. Digital system design includes many different design and verification stages and requires wide range of EDA tools and framework accordingly.

**Table 2.2.** System Level Tools Features Comparison.

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 11%" />
<col style="width: 10%" />
<col style="width: 8%" />
<col style="width: 11%" />
<col style="width: 18%" />
<col style="width: 10%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="8">System Level EDA Tools: System Design &amp; Architectural Exploration</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="9">Simulator, Emulator, Virtual Prototyping</td>
</tr>
<tr class="even">
<td></td>
<td><strong>FireSim</strong></td>
<td><strong>Gem5</strong></td>
<td><strong>GVSoC</strong></td>
<td><strong>QEMU</strong></td>
<td><strong>Renode</strong></td>
<td><strong>SST</strong></td>
<td><strong>SystemC (TLM)</strong></td>
<td><strong>VPSim</strong></td>
</tr>
<tr class="odd">
<td>ISA Support</td>
<td>⚙️<br />
RISC-V. Custom</td>
<td>ARM, x86, RISC-V,POWER SPARC, MIPS</td>
<td>RISC-V</td>
<td>ARM, x86, RISC-V, PPC, SPARC,, MIPS, OpenRISC and more</td>
<td>ARM, RISC-V, x86, POWER, SPARC, Xtensa, MSP430X</td>
<td>⚙️</td>
<td>⚙️</td>
<td>Arm, RISC-V</td>
</tr>
<tr class="even">
<td>Full-System &amp; Sub-System Simulation</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Cycle-Accurate</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>⚙️</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Extensible / Modular</td>
<td>✅Chisel based</td>
<td>✅</td>
<td>✅</td>
<td>⚙️</td>
<td><p>✅</p>
<p>Co-sim</p></td>
<td>✅co-sim</td>
<td>✅</td>
<td>✅with QEMU</td>
</tr>
<tr class="odd">
<td>Use Case</td>
<td>Hardware simulation, development, and IP generation, HW/SW co-design</td>
<td>CPU/memory architecture research</td>
<td>Multicore, multi memory level RISC-V based IoT processor &amp; System</td>
<td>OS bring-up, virtualization, fast regression</td>
<td>Firmware bring-up, embedded HW/SW co-dev</td>
<td>Multi-component heterogeneous system sim</td>
<td>System modeling, virtual<br />
prototyping, HW/SW<br />
Co-design, RTL<br />
Verification</td>
<td>Profiling, benchmarking HPC to multi SoC including heterogenous multicore architecture</td>
</tr>
<tr class="even">
<td>Sub-System Specific</td>
<td colspan="2"><strong>Muchisim</strong></td>
<td colspan="2"><strong>noxim</strong></td>
<td colspan="2"><strong>Ramulator</strong></td>
<td><strong>SimEng</strong></td>
<td><strong>Spike</strong></td>
</tr>
<tr class="odd">
<td>ISA Support</td>
<td colspan="2">⚙️</td>
<td colspan="2">❌</td>
<td colspan="2">❌</td>
<td>✅ Arm, x86, RISC-V, POWER</td>
<td>RISC-V only</td>
</tr>
<tr class="even">
<td>Subsystem Sim</td>
<td colspan="2">✅ Multi-Chip Multicore</td>
<td colspan="2">✅NoC</td>
<td colspan="2">✅ DRAM standards</td>
<td>✅ Pipelines, caches</td>
<td>⚙️</td>
</tr>
<tr class="odd">
<td>Use Case</td>
<td colspan="2">Multicore CPU, multi-chiplet architecture research</td>
<td colspan="2">NoC research &amp; interconnect exploration</td>
<td colspan="2">Memory controller/DRAM<br />
architecture research</td>
<td>Pipeline/microarchitecture studies</td>
<td>RISC-V ISA compliance &amp; functional verification</td>
</tr>
<tr class="even">
<td colspan="9">IP Reuse, Integration, Power Modeling &amp; Analysis</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>Switchboard</strong></td>
<td colspan="2"><strong>FuseSoC + Edalize</strong></td>
<td colspan="2"><strong>Kactus</strong></td>
<td><strong>McPAT</strong></td>
<td colspan="2"><strong>MESSY</strong></td>
</tr>
<tr class="even">
<td>Modeling /Simulation</td>
<td>✅ Connects subsystems: FPGA, RTL, SW models</td>
<td colspan="2">⚙️ (assist)</td>
<td colspan="2">❌</td>
<td>✅</td>
<td colspan="2">✅ Simulation (GVSoC),<br />
Power<br />
modeling (SystemC-AMS)</td>
</tr>
<tr class="odd">
<td>IP Packaging, reuse, Integration &amp; Doc gen</td>
<td>⚙️ Framework to integrate, communicate</td>
<td colspan="2">⚙️</td>
<td colspan="2">✅</td>
<td>❌</td>
<td colspan="2">⚙️</td>
</tr>
<tr class="even">
<td>Power Estimation</td>
<td>❌</td>
<td colspan="2">❌</td>
<td colspan="2">❌</td>
<td>✅</td>
<td colspan="2">✅</td>
</tr>
<tr class="odd">
<td>Area &amp; Timing Estimation</td>
<td>❌</td>
<td colspan="2">❌</td>
<td colspan="2">❌</td>
<td>✅</td>
<td colspan="2">️⚙️</td>
</tr>
<tr class="even">
<td>IP-XACT Support</td>
<td>❌</td>
<td colspan="2" rowspan="2"><p>⚙️</p>
<p>IP reuse, aid creation, build &amp; simulation SoC/ASIC solutions</p></td>
<td colspan="2" rowspan="2"><p>✅native</p>
<p>IP packaging, reuse and SoC assembly</p></td>
<td>❌</td>
<td colspan="2" rowspan="2"><p>⚙️</p>
<p>Functional sim,<br />
system/subsystem level<br />
power<br />
modeling</p></td>
</tr>
<tr class="odd">
<td>Use Case</td>
<td>HW/SW co-sim, connecting simulators/IPs</td>
<td>Power, Area &amp; Timing Analysis</td>
</tr>
<tr class="even">
<td colspan="9">HLS Framework, Domain–Specific IP Generators (HW/SW Co-design)</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><strong>CIRCT</strong></td>
<td><strong>Dynamatic</strong></td>
<td colspan="2"><strong>PandA-bambu</strong></td>
<td><strong>PipelineC</strong></td>
<td><strong>XLS</strong></td>
<td><strong>OpenASIP</strong></td>
</tr>
<tr class="even">
<td>IP /RTL Generator</td>
<td colspan="2">❌</td>
<td>❌</td>
<td colspan="2">✅ (HLS)</td>
<td>✅ (HLS)</td>
<td>⚙️</td>
<td>✅ Processor generator</td>
</tr>
<tr class="odd">
<td>Input</td>
<td colspan="2">MLIR/LLVM IR, FIRRTL, Calyx, Python, Chisel, OpenCL</td>
<td>C/C++ (LLVM)</td>
<td colspan="2">C/C++</td>
<td>Restricted C</td>
<td>DSLX, C++ IR</td>
<td>Architecture Definition File, C/C++, OpenCL</td>
</tr>
<tr class="even">
<td>Output</td>
<td colspan="2">RTL/IR</td>
<td>RTL (Verilog/VHDL)</td>
<td colspan="2">RTL (VHDL/Verilog)</td>
<td>Verilog/VHDL</td>
<td>RTL (Verilog/SV)</td>
<td>Custom processor RTL + compiler</td>
</tr>
<tr class="odd">
<td>Use Case</td>
<td colspan="2">Design accelerators, support HW design, transformation and generation, formal verification tooling, HLS</td>
<td>Dataflow accelerators</td>
<td colspan="2">RTL from C/C++, high-level verification, ASIC, parallel HW accelerator design, design flow space exploration</td>
<td>FPGA pipeline, streaming accelerators</td>
<td>Verified HLS, accelerate design</td>
<td>Custom domain-specific ISAs processors</td>
</tr>
</tbody>
</table>

> **Table 2.3.** Front-End EDA Tool’s Features Comparison

<table>
<colgroup>
<col style="width: 17%" />
<col style="width: 12%" />
<col style="width: 9%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 12%" />
<col style="width: 11%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="7">Front-End EDA Tools (or Framework): Logic (HDL) Design, Verification &amp; Testing</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="8">HDL Framework, Toolchain, IP Generators</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"><strong>Amaranth (nMigen)</strong></td>
<td colspan="2"><strong>Chisel</strong></td>
<td><strong>Chipyard</strong></td>
<td colspan="2"><strong>Py2HWSW</strong></td>
</tr>
<tr class="odd">
<td>Host Language</td>
<td colspan="2">Python</td>
<td colspan="2">Scala</td>
<td>Chisel</td>
<td colspan="2">Python</td>
</tr>
<tr class="even">
<td>Generates Synthesizable Verilog</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">✅</td>
</tr>
<tr class="odd">
<td>Parametric/Reusable Design</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">✅</td>
</tr>
<tr class="even">
<td>Built-in / includes Simulation</td>
<td colspan="2">✅</td>
<td colspan="2">❌</td>
<td>✅</td>
<td colspan="2">✅</td>
</tr>
<tr class="odd">
<td>Ecosystem Integration</td>
<td colspan="2">✅</td>
<td colspan="2">❌</td>
<td>✅</td>
<td colspan="2">✅</td>
</tr>
<tr class="even">
<td>Large-Scale ASIC/SoC</td>
<td colspan="2">⚙️</td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">✅</td>
</tr>
<tr class="odd">
<td>Use Case</td>
<td colspan="2">Rapid prototyping, FPGA IP blocks, teaching, Not widely used in ASIC flow.</td>
<td colspan="2">ASIC/SoC research, parameterized CPU/accelerator design. RTL&amp; FPGA accelerated sim, automated VLSI flow</td>
<td>Ecosystem to design &amp; evaluate SoC/ HW</td>
<td colspan="2">HW/SW codesign, lint-friendly core gen for ASIC/FPGA, flow automation</td>
</tr>
<tr class="even">
<td colspan="8">Memory Generators</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><strong>Bsg_fakeram</strong></td>
<td colspan="2"><strong>Lake</strong></td>
<td><strong>OpenRAM</strong></td>
<td colspan="2"><strong>RgGen</strong></td>
</tr>
<tr class="even">
<td>Memory Generator</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">Register generation</td>
</tr>
<tr class="odd">
<td>Extensible</td>
<td colspan="2">⚙️</td>
<td colspan="2">⚙️</td>
<td>✅</td>
<td colspan="2">✅</td>
</tr>
<tr class="even">
<td>Input</td>
<td colspan="2">JSON (configuration file)</td>
<td colspan="2">Macros, high-level specification</td>
<td>Config + PDK</td>
<td colspan="2">YAML, JSON and more</td>
</tr>
<tr class="odd">
<td>Output</td>
<td colspan="2">RTL behavioral RAM models</td>
<td colspan="2">RTL/ macro buffers</td>
<td>SRAM GDSII, netlist, Verilog/SPICE models</td>
<td colspan="2">RTL, SW headers, UVM models</td>
</tr>
<tr class="even">
<td>Use Case</td>
<td colspan="2">Simulation/verification (Fake SRAM models), Prototyping</td>
<td colspan="2">Specialized memory/buffer IP</td>
<td>Generate ASIC SRAM macros</td>
<td colspan="2">Auto-generate register blocks</td>
</tr>
<tr class="odd">
<td colspan="8">Linters</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"><strong>PySlint</strong></td>
<td colspan="2"><strong>SVA Lint</strong></td>
<td><strong>svlint</strong></td>
<td><strong>TerosHDL</strong></td>
<td><strong>Verible</strong></td>
</tr>
<tr class="odd">
<td>Verilog Support</td>
<td colspan="2">✅</td>
<td colspan="2">❌</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>SystemVerilog Support</td>
<td colspan="2">✅</td>
<td colspan="2">SVA</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>VHDL Support</td>
<td colspan="2">❌</td>
<td colspan="2">❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>SVA (SystemVerilog Assertions) Linting</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td>⚙️</td>
<td>✅</td>
<td>⚙️</td>
</tr>
<tr class="odd">
<td>Style/ Formatting Checks</td>
<td colspan="2">✅</td>
<td colspan="2">⚙️</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Semantic Checks</td>
<td colspan="2">⚙️</td>
<td colspan="2">⚙️</td>
<td>⚙️</td>
<td>⚙️</td>
<td>⚙️</td>
</tr>
<tr class="odd">
<td>Custom Rule Support</td>
<td colspan="2">⚙️ Via python</td>
<td colspan="2">✅Assertion specific</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="even">
<td colspan="8">RTL Compiler/Simulator (Optionally Synthesis)</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>essent</strong></td>
<td><strong>GHDL</strong></td>
<td><strong>Icarus Verilog</strong></td>
<td><strong>NVC</strong></td>
<td><strong>Surelog</strong></td>
<td><strong>Synlig</strong></td>
<td><strong>Verilator</strong></td>
</tr>
<tr class="even">
<td>Verilog Support</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
<td>⚙️</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>SystemVerilog Support</td>
<td>❌</td>
<td>❌</td>
<td>⚙️</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
<td>Subset</td>
</tr>
<tr class="even">
<td>VHDL Support</td>
<td>❌</td>
<td>VHDL-87, -93,2002, partially 2008,2019</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Compiled Simulation (fast)</td>
<td>⚙️<br />
FIRRTL to C++</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Compilation</td>
<td>⚙️<br />
FIRRTL to C++</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Simulation</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Synthesis</td>
<td>❌</td>
<td>⚙️</td>
<td></td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Event-Driven Accuracy</td>
<td>Cycle-accurate</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>Cycle accurate</td>
</tr>
<tr class="even">
<td>Waveform format</td>
<td>FST, VCD</td>
<td>FST, GHW, VCD</td>
<td>FST, LXT, VCD</td>
<td>FST, VCD</td>
<td>❌</td>
<td>❌</td>
<td>FST, VCD</td>
</tr>
<tr class="odd">
<td>Testing &amp; Verification Framework Integration</td>
<td>❌</td>
<td>OSVVM, UVVM, VUnit, cocotb</td>
<td>Cocotb</td>
<td>OSVVM, UVVM, VUnit, cocotb</td>
<td>❌</td>
<td>❌</td>
<td>Cocotb,C++/SystemC Testbench (UVM in development)</td>
</tr>
<tr class="even">
<td>Primary Focus</td>
<td>Chisel/FIRRTL sim</td>
<td>VHDL sim/synth</td>
<td>Verilog compilation &amp; Sim</td>
<td>VHDL compilation &amp; sim</td>
<td>SV Frontend</td>
<td>SV-17 synthesis using Surelog, Yosys</td>
<td>Fast Verilog sim, lint, compile</td>
</tr>
<tr class="odd">
<td colspan="8">Waveform Viewer</td>
</tr>
<tr class="even">
<td></td>
<td><strong>fstdumper</strong></td>
<td colspan="2"><strong>GtkWave</strong></td>
<td><strong>simview</strong></td>
<td colspan="2"><strong>Sooty</strong></td>
<td><strong>Surfer</strong></td>
</tr>
<tr class="odd">
<td>VCD Support</td>
<td>❌</td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>FST Support</td>
<td>✅</td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">❌</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>LXT, LXT2, GHW, VZT Support</td>
<td>❌</td>
<td colspan="2">✅</td>
<td></td>
<td colspan="2">❌</td>
<td>⚙️</td>
</tr>
<tr class="even">
<td>GUI Waveform Viewer</td>
<td><p>❌</p>
<p>Via GTKWave</p></td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">✅</td>
<td><p>✅</p>
<p>Modern, web interface</p></td>
</tr>
<tr class="odd">
<td>Scripting/Automation</td>
<td>⚙️</td>
<td colspan="2">✅</td>
<td>✅</td>
<td colspan="2">✅</td>
<td>⚙️</td>
</tr>
<tr class="even">
<td>Primary Focus</td>
<td>Fast dumping of simulation waveform.</td>
<td colspan="2">General purpose. Debugging Verilog or VHDL simulatio.</td>
<td>Debug &amp; analyze SV HW design.</td>
<td colspan="2">Lightweight waveform visualization as an alternative viewer.</td>
<td>Lightweight, highly configurable.</td>
</tr>
<tr class="odd">
<td colspan="8">Formal Verification</td>
</tr>
<tr class="even">
<td></td>
<td><strong>ABC</strong></td>
<td><strong>mcy</strong></td>
<td><strong>cvc5</strong></td>
<td><strong>AutoSVA</strong></td>
<td><strong>AutoCC</strong></td>
<td><strong>SymbiYosys (sby)</strong></td>
<td><strong>eqy</strong></td>
</tr>
<tr class="odd">
<td>Mixed HDL</td>
<td>✅</td>
<td>⚙️</td>
<td>⚙️ SMT-LIB</td>
<td>⚙️</td>
<td>⚙️</td>
<td>✅</td>
<td>⚙️</td>
</tr>
<tr class="even">
<td>Formal Property Checking</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Automation (Property/Assertion Gen)</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>⚙️</td>
<td>✅</td>
<td>⚙️</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Equivalence Checking</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>⚙️</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Model Checking</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
<td>⚙️</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Integration with Open-source Tools</td>
<td>Yosys, LSOracle, eqy</td>
<td>Yosys</td>
<td>Yosys, SBY</td>
<td>SBY</td>
<td>SBY</td>
<td>Yosys, Boolector, cvc5</td>
<td>Yosys,SBY</td>
</tr>
<tr class="odd">
<td colspan="8">Verification Framework &amp; Testing</td>
</tr>
<tr class="even">
<td></td>
<td><strong>OSVVM</strong></td>
<td><strong>cocotb</strong></td>
<td><strong>PyUVM</strong></td>
<td><strong>OSVVM</strong></td>
<td><strong>UVVM</strong></td>
<td><strong>SVUnit</strong></td>
<td><strong>VUnit</strong></td>
</tr>
<tr class="odd">
<td>HDL Support</td>
<td>VHDL</td>
<td>Use Python for VHDL &amp; SV</td>
<td>Python</td>
<td>VHDL</td>
<td>VHDL</td>
<td>Verilog, SV</td>
<td>VHDL, SV</td>
</tr>
<tr class="even">
<td>Verification Style</td>
<td></td>
<td>Coroutine based</td>
<td>UVM-like (Python)</td>
<td>Library based</td>
<td>UVM like</td>
<td>Unit Testing</td>
<td>Unit Testing with Framework</td>
</tr>
<tr class="odd">
<td>Full Verification Methodology</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Testbench Automation</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Constrained Random or Randomization</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>⚙️via OSVVM</td>
</tr>
<tr class="even">
<td>Coverage</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Assertion</td>
<td>⚙️</td>
<td>⚙️</td>
<td>⚙️ via SV</td>
<td>VHDL assert</td>
<td>✅</td>
<td>⚙️</td>
<td>⚙️</td>
</tr>
<tr class="even">
<td>Scoreboard or Checker</td>
<td></td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>⚙️</td>
</tr>
<tr class="odd">
<td>Unit Testing</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td colspan="8">Design For Testing (DFT)</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>Atalanta</strong></td>
<td colspan="2"><strong>FAULT</strong><br />
<strong>(</strong>Difetto (ALPHA))</td>
<td><strong>Fenice</strong></td>
<td colspan="2"><strong>Hope</strong></td>
<td><strong>DFT in OpenROAD</strong></td>
</tr>
<tr class="even">
<td>Scan Insertion</td>
<td>❌</td>
<td colspan="2">✅</td>
<td>❌</td>
<td colspan="2">❌</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>ATPG</td>
<td>✅</td>
<td colspan="2">✅</td>
<td>❌</td>
<td colspan="2"><p>❌</p>
<p>Test pattern generation</p></td>
<td>❌</td>
</tr>
<tr class="even">
<td>Scan Chain Testing</td>
<td>❌</td>
<td colspan="2">✅</td>
<td>⚙️ library</td>
<td colspan="2">⚙️ fault simulation</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>MBIST</td>
<td>❌</td>
<td colspan="2">❌</td>
<td>❌</td>
<td colspan="2">⚙️ (BIST)</td>
<td>❌</td>
</tr>
<tr class="even">
<td>JTAG Macro</td>
<td>❌</td>
<td colspan="2">❌</td>
<td>❌</td>
<td colspan="2">❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Boundary Scan</td>
<td>❌</td>
<td colspan="2">❌</td>
<td>❌</td>
<td colspan="2">❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Scan-chain compression</td>
<td>❌</td>
<td colspan="2">❌</td>
<td>❌</td>
<td colspan="2">⚙️</td>
<td>❌</td>
</tr>
</tbody>
</table>

Some tools are used in both frontend and backend stages of digital design flows. Therefore, tools such as Yosys for synthesis and static timing analysis tools are described in the physical design section, as they are integrated to the RTL-to-GDSII design flow in some ASIC design flow. Many small or core tools and modules which are integrated inside some RTL-to-GDSII tools are not listed in the tables.

> **Table 2.4.** Comparison of Physical Design and Verification EDA Tool Features

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 9%" />
<col style="width: 9%" />
<col style="width: 13%" />
<col style="width: 10%" />
<col style="width: 11%" />
<col style="width: 9%" />
<col style="width: 15%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="7"><blockquote>
<p>Back-End EDA Tools: Physical Design &amp; Verification</p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="8">RTL2GDSII Flow (Autonomous, Custom, Modular)</td>
</tr>
<tr class="even">
<td>RTL2GDS / netlist GDS</td>
<td colspan="2"><strong>OpenROAD FlowScript (ORFS)</strong></td>
<td colspan="2"><strong>LibreLane</strong></td>
<td colspan="2"><strong>Silicon Compiler</strong></td>
<td><strong>mflowgen</strong></td>
</tr>
<tr class="odd">
<td>RTL → GDSII Flow</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td>Netlist to GDS</td>
</tr>
<tr class="even">
<td>OpenROAD Based</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td>Can call OpenROAD</td>
</tr>
<tr class="odd">
<td>Multi-tool Support</td>
<td colspan="2">❌</td>
<td colspan="2">❌</td>
<td colspan="2">✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Customizable Flow</td>
<td colspan="2">⚙️ Fixed</td>
<td colspan="2">⚙️</td>
<td colspan="2">✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Dependency / Reproducibility</td>
<td colspan="2">Script Based</td>
<td colspan="2">YAML/JSON Flow</td>
<td colspan="2">✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Cloud/CI Friendly</td>
<td colspan="2">Manual Script</td>
<td colspan="2">Can be scripted</td>
<td colspan="2">✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>AI/ML</td>
<td colspan="2">✅</td>
<td colspan="2">❌</td>
<td colspan="2"><blockquote>
<p>⚙️ Possible</p>
</blockquote></td>
<td>❌</td>
</tr>
<tr class="even">
<td>Primary Use Case</td>
<td colspan="2">Automated Flow</td>
<td colspan="2">Configurable ASIC Flow</td>
<td colspan="2">GDSII Framework</td>
<td>Flow construction + reproducibility infra</td>
</tr>
<tr class="odd">
<td colspan="8">Logic Synthesis</td>
</tr>
<tr class="even">
<td>Synthesis</td>
<td colspan="2"><strong>Yosys</strong></td>
<td colspan="2"><strong>LSOracle</strong></td>
<td colspan="3"><strong>Naja EDA</strong></td>
</tr>
<tr class="odd">
<td>Verilog Support</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td colspan="3">✅</td>
</tr>
<tr class="even">
<td>SystemVerilog Support</td>
<td colspan="2">⚙️</td>
<td colspan="2">✅</td>
<td colspan="3">⚙️</td>
</tr>
<tr class="odd">
<td>VHDL Support</td>
<td colspan="2">Via Plugin</td>
<td colspan="2">⚙️via Yosys</td>
<td colspan="3">❌</td>
</tr>
<tr class="even">
<td>Tech Mapping (Liberty)</td>
<td colspan="2">✅</td>
<td colspan="2">❌</td>
<td colspan="3">❌</td>
</tr>
<tr class="odd">
<td>Logic Optimization (AIG/MIG, etc.)</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td colspan="3">❌</td>
</tr>
<tr class="even">
<td>Formal Equivalence Checking</td>
<td colspan="2">⚙️ via SymbiYosys, ABC</td>
<td colspan="2">⚙️ relies on Yosys/ABC</td>
<td colspan="3">❌</td>
</tr>
<tr class="odd">
<td>Extensible / Plugins</td>
<td colspan="2">✅</td>
<td colspan="2">✅</td>
<td colspan="3">✅</td>
</tr>
<tr class="even">
<td colspan="8">Place and Route (P&amp;R)</td>
</tr>
<tr class="odd">
<td>Place &amp; Route</td>
<td colspan="2"><strong>Coriolis</strong></td>
<td><strong>DREAMPLace</strong></td>
<td><strong>LibrEDA</strong></td>
<td><strong>RePlAce</strong></td>
<td><strong>Qflow</strong></td>
<td><strong>Qrouter</strong></td>
</tr>
<tr class="even">
<td>Placement</td>
<td colspan="2">✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Routing</td>
<td colspan="2">✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Clock Tree Synthesis</td>
<td colspan="2">✅</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
<td>⚙️</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Timing Analysis Integration</td>
<td colspan="2">✅</td>
<td>⚙️</td>
<td>❌</td>
<td>⚙️</td>
<td>⚙️ Call STA externally</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Tech Mapping (LEF/DEF/Liberty)</td>
<td colspan="2">✅</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Scalability</td>
<td colspan="2">⚙️ Medium size</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
<td>❌</td>
<td>⚙️ Small, medium</td>
</tr>
<tr class="even">
<td colspan="8">Physical Verification (Layout), Timing Analyzer</td>
</tr>
<tr class="odd">
<td>Layout, STA, Netlist</td>
<td><strong>Klayout</strong></td>
<td><strong>Glade</strong></td>
<td><strong>Magic</strong></td>
<td><strong>OpenSTA</strong></td>
<td><strong>OpenTimer</strong></td>
<td><strong>Netgen</strong></td>
<td><strong>CVC</strong></td>
</tr>
<tr class="even">
<td>Layout Edit/View</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>DRC</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>LVS</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Parasitic Extraction</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Timing Analysis</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Power Estimation</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>⚙️ Switching activity input, limited</td>
<td>basic dynamic power est</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Netlist Comparison</td>
<td>✅</td>
<td>❌</td>
<td></td>
<td></td>
<td></td>
<td>✅</td>
<td>✅</td>
</tr>
</tbody>
</table>

**Overview of OpenROAD Flow Script (ORFS)**

OpenROAD is open-source platform for digital semiconductor design. Its native flow, OpenROAD Flow Scripts (ORFS), is a fully autonomous RTL-to-GDSII implementation framework built on OpenROAD and other open-source tools. It is described here in more detail, since it seems to be developing into a widely adopted flow framework and collection of tools for bringing digital designs from RTL to GDSII. ORFS is designed to enable no-human-in-the-loop (NHIL) digital design, targeting a rapid 24-hour turnaround from RTL to GDSII. It supports rapid architecture and design space exploration, enables early prediction of quality of results (QoR), and provides detailed physical design implementation. Basic Flow stages for a physical design implementation using OpenROAD with respective tools are listed in short in the following steps.

**Synthesis**

- Generate gate-level netlist (yosys).

- Perform cell mapping (abc).

- Perform pre-layout STA (OpenSTA).

**Floorplanning**

- Floorplan initialization – Define the chip area, utilization, core area, including of the macros, cell sites and tracks. IO pin and cell placement (ioPlacer, ICeWall).

- Macro placement (RAMs, embedded macros) (Hier-RTLMP, TritonMacroPlacer).

- Tap cell and well tie insertion.

- Generate power distribution network (PDNGEN).

**Global Placement**

- Standard cell placement.

- Automatic placement optimization and repair for max slew, max capacitance, and max fanout violations and long wires. (RePlAce)

**Detailed Placement**

- Perform detailed placement to legalize the globally placed components by aligning to grid, adhere to design rules .

- Incremental timing analysis for early estimates.(OpenSTA)

**Clock Tree Synthesis (CTS)**

- Insert buffers and resize for high fanout nets.

- Synthesize clock three structure (TritonCTS 2.0).

- Optimize setup/hold timing.

**Global Routing**

- Antenna repair.

- Perform global routing to generate routing guide files for detailed router (FastRoute).

**Detailed Routing**

- Perform detail route (TritonRoute).

- Legalize routes, DRC-correct routing to meet timing, power constraints.

**Chip Finishing**

- Perform SPEF extraction, parasitic extraction using OpenRCX.

- IR drop analysis (PDNSim)

- Final timing verification

- Final physical verification

- Dummy metal fill for manufacturability

- Use Klayout or Magic using generated GDS for DRC signoff.

The OpenROAD build system combines multiple tools into a single executable by compiling each tool as a library and linking them together. It relies on OpenDB for database system and additional open-source tools beyond those listed above.

## Analog/Mixed Signal/RF

This subsection introduces open-source tools used in analog, mixed signal, and RF design flows. Since the design flows share similar steps, the tools are grouped by design step with some modifications where needed.

### Tool descriptions

**Table 2.5.** Analog/Mixed Signal/Design Tool Descriptions

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2">Tools Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="2"><blockquote>
<p>Schematic capture EDA tools</p>
</blockquote></td>
</tr>
<tr class="even">
<td>Xschem</td>
<td>A Schematic capture tool well established in the open-source silicon domain</td>
</tr>
<tr class="odd">
<td>Qucs-S</td>
<td>A schematic capture tool for RF design widely used by RF designers at discrete level</td>
</tr>
<tr class="even">
<td>XCircuit</td>
<td>A circuit drawing and schematic capture tool</td>
</tr>
<tr class="odd">
<td>Qucs</td>
<td>Predecessor of Qucs-S</td>
</tr>
<tr class="even">
<td>XIC</td>
<td>A set of tools for IC design, which was used in production and later released to open-source domain.</td>
</tr>
<tr class="odd">
<td>RevolutionEDA</td>
<td>A new schematic and symbol editor targeting custom integrated circuit design with integrated simulation and plotting capabilities. The software is under Common Clause v 1.0 license which means access to the source code, but some restrictions on further code redistribution</td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td colspan="2">Circuit simulation</td>
</tr>
<tr class="even">
<td>NGSPICE</td>
<td>A SPICE simulator for analog, mixed-signal circuits and OSDI interface support</td>
</tr>
<tr class="odd">
<td>Xyce</td>
<td>A SPICE compatible simulator from Sandia National Laboratories for large AMS designs</td>
</tr>
<tr class="even">
<td>VACASK</td>
<td>A modular simulator supporting Verilog -A models and targeting RF design flow. The tool supports OSDI interface.</td>
</tr>
<tr class="odd">
<td>Gnucap</td>
<td>A mixed-signal simulator with modular, plugin-based architecture targeting VerilogAMS support</td>
</tr>
<tr class="even">
<td>WRSpice</td>
<td>A SPICE compatible simulator from WRCad</td>
</tr>
<tr class="odd">
<td colspan="2">Verilog-A model generators</td>
</tr>
<tr class="even">
<td>OpenVAF</td>
<td>A Verilog-A compiler for ngspice and VACASK</td>
</tr>
<tr class="odd">
<td>ADMS</td>
<td>A Verilog-A model compiler for Xyce and WRspice</td>
</tr>
<tr class="even">
<td>Gnucap ModelGen</td>
<td>A VerilogAMS model compiler for Gnucap</td>
</tr>
<tr class="odd">
<td colspan="2">Electromagnetic field analysis and simulation</td>
</tr>
<tr class="even">
<td>OpenEMS</td>
<td>An electromagnetic simulator supporting RF and mmWave co-design. Method: FDTD. Limited user interface, model is usually built using Matlab or Python scripts. Some 3<sup>rd</sup> party plugins to create model scripts from open-source CAD tools. IHP workflow to create and run this model script from GDSII file</td>
</tr>
<tr class="odd">
<td>AWS Palace</td>
<td>An electromagnetic simulator for RF/mm-wave supporting single computer to large-scale EM analysis and cloud workflows. Method: FEM. Comprehensive support for many features and solver options known from commercial RF FEM tools. Solver engine only, no user interface, model and mesh must be built with other tools. IHP workflow to create these simulator input files from GDSII file.</td>
</tr>
<tr class="even">
<td>ElmerFEM</td>
<td>A multi physics software, some support for RF EM modelling. Method: FEM. Solver engine only, no user interface, model and mesh must be built with other tools. Not obvious how to apply to RF models. Limitations for RF solver, e.g. direct solver only (limited model size), no adaptive mesh refinement. IHP workflow is planned (work in progress).</td>
</tr>
<tr class="odd">
<td>RF-SciKit</td>
<td>A BSD-licensed package for RF/Microwave engineering. It provides a modern, object-oriented library which is both flexible and scalable.</td>
</tr>
<tr class="even">
<td colspan="2">Layout Editing</td>
</tr>
<tr class="odd">
<td>Klayout</td>
<td>Layout editor with integrated DRC and LVS capabilities</td>
</tr>
<tr class="even">
<td>Magic</td>
<td>TCL/TK based highly scriptable layout editor with DRC capabilities and netlist extraction features</td>
</tr>
<tr class="odd">
<td>XIC</td>
<td>Layout editor from WRCad tool set</td>
</tr>
<tr class="even">
<td>GDSFactory</td>
<td>Python based highly scriptable layout automation tool</td>
</tr>
<tr class="odd">
<td>RevolutionEDA</td>
<td>Python based integrated design environment</td>
</tr>
<tr class="even">
<td colspan="2">DRC engines</td>
</tr>
<tr class="odd">
<td>Klayout</td>
<td>Built in features to implement DRC rules. It includes DRC markup browser</td>
</tr>
<tr class="even">
<td>Magic</td>
<td>It includes a DRC engine. It can be run in a live mode (while editing the layout)</td>
</tr>
<tr class="odd">
<td>XIC</td>
<td>DRC engine included in XIC tool set</td>
</tr>
<tr class="even">
<td>GDSFactory</td>
<td>Python based DRC engine</td>
</tr>
<tr class="odd">
<td colspan="2">LVS engines</td>
</tr>
<tr class="even">
<td>Klayout</td>
<td>Built in features to implement LVS rules. It includes LVS markup browser</td>
</tr>
<tr class="odd">
<td>netgen</td>
<td>A netlist comparison tool. It supports SPICE and CDL formats.</td>
</tr>
<tr class="even">
<td>XIC</td>
<td>LVS engine included in XIC tool set</td>
</tr>
<tr class="odd">
<td>GDSFactory</td>
<td>Python based LVS engine</td>
</tr>
<tr class="even">
<td colspan="2">Integrated solutions</td>
</tr>
<tr class="odd">
<td>ORDeC</td>
<td>(Open Rapid Design Composer) is an open-source <strong>custom IC design platform</strong>. Its goal is to provide an accessible and streamlined interface to design and analyze analog, mixed-signal and custom digital integrated circuits from schematic to layout.</td>
</tr>
<tr class="even">
<td colspan="2">Parasitic Extraction</td>
</tr>
<tr class="odd">
<td>Klayout - PEX</td>
<td>Klayout based wrapper for parasitic extraction from a layout</td>
</tr>
<tr class="even">
<td>Magic</td>
<td>Layout tool with the capability of generating a netlist with parasitic from a custom layout.</td>
</tr>
<tr class="odd">
<td>OpenEMS</td>
<td>EM field solver capable to determine S-parameters of an element, which then can be identified as parasitic element</td>
</tr>
<tr class="even">
<td>FastCap</td>
<td>A multipole-accelerated capacitance extraction program</td>
</tr>
<tr class="odd">
<td>FastCap2</td>
<td>3D capacitance solver</td>
</tr>
<tr class="even">
<td>FastHenry</td>
<td>A multipole-accelerated inductance analysis program.</td>
</tr>
<tr class="odd">
<td colspan="2">Circuit Documentation</td>
</tr>
<tr class="even">
<td>CACE</td>
<td>A tool for automatic generation of documentation based on automated testbenches.</td>
</tr>
<tr class="odd">
<td colspan="2">Waveform Viewers</td>
</tr>
<tr class="even">
<td>GTKWave</td>
<td>Analog and digital signals waveform viewer</td>
</tr>
<tr class="odd">
<td>GAW</td>
<td>GTK analog wave viewer</td>
</tr>
<tr class="even">
<td>Surfer</td>
<td>An Extensible and Snappy Waveform Viewer</td>
</tr>
<tr class="odd">
<td>ngspice</td>
<td>A native plotting backend for ngspice</td>
</tr>
<tr class="even">
<td>Xschem</td>
<td>A Xschem built-in plotting objects</td>
</tr>
<tr class="odd">
<td>Qucs-S</td>
<td>Qucs-S built in plotting objects</td>
</tr>
<tr class="even">
<td>gnuplot</td>
<td>A generic and versatile plotting tool</td>
</tr>
<tr class="odd">
<td>XIC</td>
<td>XIC plotting backend from WRCad tool set</td>
</tr>
</tbody>
</table>

### Feature comparison

**Table 2.6.** Analog/Mixed Signal/Tool Feature Comparisons: Schematic editing

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

| Features                                                                      | Analog design EDA Tools: Schematic editing |            |         |          |            |
|-------------------------------------------------------------------------------|--------------------------------------------|------------|---------|----------|------------|
|                                                                               | **Xschem**                                 | **Qucs-S** | **XIC** | **Qucs** | **RevEDA** |
| Custom symbol definition                                                      | ✅                                         | ✅         | ✅      | ✅       | ✅         |
| Spice netlisting                                                              | ✅                                         | ✅         | ✅      | ✅       | ✅         |
| Verilog netlisting                                                            | ✅                                         | ⚙️         | ❌      | ⚙️       | ❌         |
| Spectre netlisting                                                            | ✅                                         | ⚙️         | ❌      | ❌       | ❌         |
| Callbacks for instance parameters calculation                                 | ✅                                         | ✅         | ❌      | ❌       | ❌         |
| Multiple simulator support                                                    | ✅                                         | ✅         | ❌      | ✅       | ❌         |
| Cell view selection and configuration (schematic, extracted, EM, model, etc.) | ❌                                         | ✅         | ✅      | ✅       | ✅         |
| Hierarchical schematics                                                       | ✅                                         | ✅         | ✅      | ✅       | ✅         |
| Version control support                                                       | ❌                                         | ❌         | ❌      | ❌       | ❌         |
| Multiuser support (editable, read-only)                                       | ❌                                         | ❌         | ❌      | ❌       | ✅         |

**Table 2.7.** Analog/Mixed Signal/Tool Feature Comparisons: Simulators

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

<table>
<colgroup>
<col style="width: 26%" />
<col style="width: 14%" />
<col style="width: 15%" />
<col style="width: 16%" />
<col style="width: 14%" />
<col style="width: 13%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="4">Analog design EDA Tools: Simulators</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>NGSpice</strong></td>
<td><strong>Xyce</strong></td>
<td><strong>VACASK</strong></td>
<td><strong>Gnucap</strong></td>
<td><strong>WRSpice</strong></td>
</tr>
<tr class="even">
<td>OP – operational point</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>DC – dc dweep analysis</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>TRAN – transient analysis</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>AC – small signal analysis</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Parameter Sweep</td>
<td>indirect</td>
<td>✅</td>
<td>✅</td>
<td>indirect</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>SP – scattering parameter analysis</td>
<td>✅</td>
<td>Via Linear analysis</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>NOISE – small noise analysis</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>SENS – sensitivity analysis</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Harmonic Balance – nonlinear AC analysis</td>
<td>⚙</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>TR transfer function</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="even">
<td>AMS simulation</td>
<td>Via XSPICE</td>
<td>Via custom code</td>
<td>❌</td>
<td>Native<br />
VerilogAMS</td>
<td>Native<br />
Verilog</td>
</tr>
<tr class="odd">
<td>PZ – Pole Zero analysis</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="even">
<td>DISTO – Distortion analysis</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>PSS – Periodic Steady State</td>
<td>⚙</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>PAC – Periodic AC analysis</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Touchstone format support</td>
<td>Write</td>
<td>Write</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>OSDI support</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Measurements support</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Fourier analysis</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Temperature analysis</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Output formats</td>
<td>RAW and text</td>
<td>RAW and text</td>
<td>RAW and text</td>
<td>text</td>
<td>RAW and text</td>
</tr>
<tr class="odd">
<td>Phase noise</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Transient noise</td>
<td>Scripted</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Statistical analysis</td>
<td>Scripted</td>
<td>Native command</td>
<td>Scripted</td>
<td>Scripted</td>
<td><p>Native</p>
<p>command</p></td>
</tr>
<tr class="even">
<td>Corner / multi-corner simulation</td>
<td>Single corner at once</td>
<td>Single corner at once</td>
<td>Single corner at once</td>
<td>Single corner at once</td>
<td>Single corner at once</td>
</tr>
<tr class="odd">
<td>Model support (Verilog, Verilog-AMS, etc.)</td>
<td>Via OSDI</td>
<td>Via ADMS</td>
<td>Via OSDI</td>
<td>Via Gnucap-Model Generator</td>
<td>Via ADMS</td>
</tr>
</tbody>
</table>

**Table 2.8.** Analog/Mixed Signal/Tool Feature Comparisons: Layout Editors

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

| Features                                     | Analog design EDA Tools: Layout Editors |                    |         |                |                      |
|----------------------------------------------|-----------------------------------------|--------------------|---------|----------------|----------------------|
|                                              | **Klayout**                             | **Magic**          | **XIC** | **GDSFactory** | **RevEDA**           |
| Parametric cell support with PyCellStudio    | ✅                                      | ❌                 | ✅      | ❌             | ❌                   |
| Parametric cell support with TCL             | ❌                                      | ✅                 | ❌      | ❌             | ❌                   |
| Parametric cell support with Python          | ✅                                      | ❌                 | ❌      | ✅             | ✅                   |
| DRC engine                                   | ✅                                      | ✅                 | ✅      | ✅             | Wraps around klayout |
| LVS engine                                   | ✅                                      | Netlist extraction | ✅      | ✅             | Wraps around klayout |
| PEX engine                                   | ✅                                      | ✅                 | ✅      | ❌             | ❌                   |
| Hierarchical layout support                  | ✅                                      | ✅                 | ✅      | ✅             | ✅                   |
| Multiuser support (editable, read-only)      | ❌                                      | ❌                 | ❌      | ❌             | ✅                   |
| Back annotation between schematic and layout | ❌                                      | ❌                 | ❌      | ❌             | ❌                   |

**Table 2.9.** Analog/Mixed Signal/Tool Feature Comparisons: Mixed Signal

<table>
<colgroup>
<col style="width: 49%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th>Analog design EDA Tools: Mixed signal design</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>Support level</strong></td>
</tr>
<tr class="even">
<td>Supported AMS hardware description languages (HDLs)</td>
<td>Gnucap supports Verilog-AMS,<br />
ngspice supports XSpice code models</td>
</tr>
<tr class="odd">
<td>AMS HDL integrated development environment (IDE) editor</td>
<td>❌</td>
</tr>
<tr class="even">
<td>AMS HDL compilation as a shared library</td>
<td>Supported by gnucap-model-generator<br />
Verilog-AMS LRM 2.4.0</td>
</tr>
<tr class="odd">
<td>Automatic Analog-Digital netlist partitioning</td>
<td>No, however gnucap supports manual partitiong</td>
</tr>
<tr class="even">
<td>Event-based and electrical co-simulation</td>
<td>Gnucap supports this feature, also ngspice can run analog on top simulation, which contains digital blocks (compiled from Verilog)</td>
</tr>
<tr class="odd">
<td>Analog-Digital waveform viewer</td>
<td>GTKWave, Surfer, lack of interfaces for analog waveforms</td>
</tr>
<tr class="even">
<td>AMS IP modeling for digital-on-top integration</td>
<td>LEF views can be generated using Magic VLSI,<br />
There are several tools: lc-time, libretto, CharLib, which can characterize timing for analog cells and generate Liberty files.</td>
</tr>
</tbody>
</table>

**Table 2.10.** Analog/Mixed Signal/Tool Feature Comparisons: EM Simulators

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 27%" />
<col style="width: 24%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Features</strong></th>
<th colspan="3"><strong>Analog design EDA Tools: EM Simulators</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>OpenEMS</strong></td>
<td><strong>AWS Palace</strong></td>
<td><strong>ElmerFEM</strong></td>
</tr>
<tr class="even">
<td colspan="4"><strong>EM Solver</strong></td>
</tr>
<tr class="odd">
<td><strong>Solver Type (FDTD, FEM, MoM)</strong></td>
<td>FDTD</td>
<td>FEM</td>
<td>FEM</td>
</tr>
<tr class="even">
<td><strong>Frequency Range Supported</strong></td>
<td>DC to THz</td>
<td><p>No upper limit,<br />
low frequency limit for RF solver depends on mesh size, typ. 10 MHz,<br />
DC by extrapolation.</p>
<p>Static solvers available but not included in IHP workflow.</p></td>
<td>No upper limit,<br />
low frequency limit depends on mesh size,<br />
to be determined,<br />
DC by extrapolation</td>
</tr>
<tr class="odd">
<td><strong>Selectable accuracy solver precision (fast, high accuracy)</strong></td>
<td>Not really<br />
(only energy<br />
convergence limit)</td>
<td>Yes,<br />
choose order of FEM basis function</td>
<td>Yes,<br />
choose order of FEM basis function</td>
</tr>
<tr class="even">
<td><strong>Use case orientation (IC-level, package level, antenna)</strong></td>
<td>RF at IC level and package level and antennas. Often slower than Palace FEM, but requires less RAM for large models than FEM -&gt; possibly better for some chip-on-package work. Mesh less efficient for diagonal polygons, best for Manhattan shapes.</td>
<td><p>RF at IC level and package level,</p>
<p>antenna far field is new feature and needs to be tested.</p>
<p>Using FEM, mesh is more efficient than FDTD for models with dimensions ranging from large to very small.</p>
<p>However, FEM often requires more RAM than FDTD, antenna models might run into memory limit.</p>
<p>Large models possible using MPI on data center scale.</p>
<p>Future speed-up possible if mesh algorithm in IHP workflow (gmsh) can be improved.</p></td>
<td><p>Multiphysics<br />
otherwise see Palace.</p>
<p>Complexity is limited because at present, only direct matrix solver is available for the RF solver.</p>
<p>Work on RF solver is rather new, work in progress.</p>
<p>Future speed-up possible if mesh algorithm in IHP workflow (gmsh) can be improved.</p></td>
</tr>
<tr class="odd">
<td><strong>Multi-threading</strong></td>
<td>Yes, but does not scale well for more than 4 threads</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr class="even">
<td><strong>Load sharing / Data center</strong></td>
<td>No</td>
<td>MPI</td>
<td>MPI</td>
</tr>
<tr class="odd">
<td><strong>Recommended RAM size</strong></td>
<td>16 GB</td>
<td>64 -128 GB</td>
<td>64 -128 GB</td>
</tr>
<tr class="even">
<td colspan="4"><strong>Geometry and Materials</strong></td>
</tr>
<tr class="odd">
<td><strong>Support for planar and 3D structures</strong></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr class="even">
<td><strong>Fully customizable layer stack (metal thickness and conductivity, vias, substrate)</strong></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes, but at present metal resistance goes to zero towards DC.<br />
TO DO: implement wideband metal loss model.</td>
</tr>
<tr class="odd">
<td colspan="4"><strong>Meshing</strong></td>
</tr>
<tr class="even">
<td><strong>Automatic meshing</strong></td>
<td>Yes, by IHP workflow script (custom code)</td>
<td>Yes, by IHP workflow script (gmsh + custom code)</td>
<td>Yes, by IHP workflow script (gmsh + custom code)</td>
</tr>
<tr class="odd">
<td><strong>Adaptive meshing (shape and current density based)</strong></td>
<td>Not used in FDTD</td>
<td>Yes, adaptive mesh refinement option during solve</td>
<td>No adaptive mesh refinement during solve</td>
</tr>
<tr class="even">
<td colspan="4"><strong>Simulation Features</strong></td>
</tr>
<tr class="odd">
<td><strong>DC and low frequencies</strong></td>
<td>Solution goes down to DC, but results towards DC might have some ripple, depending on energy convergence limit.</td>
<td><p>Static solver available but not implemented in IHP workflow script.</p>
<p>IHP workflow script uses extrapolation to DC from low frequency data<br />
(10 + 20 MHz).</p>
<p>This DC data is more accurate and robust than openEMS FDTD data.</p></td>
<td>IHP workflow script uses extrapolation to DC from low frequency data<br />
(10 + 20 MHz)</td>
</tr>
<tr class="even">
<td><strong>Adaptive frequency sampling</strong></td>
<td>FDTD always gives smooth wideband sweep from FFT</td>
<td>Yes, robust and fast</td>
<td>Very limited</td>
</tr>
<tr class="odd">
<td><strong>Multi/differential-ports and multi-signal analysis</strong></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr class="even">
<td><strong>S-parameter extraction</strong></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr class="odd">
<td><strong>Field visualization (E/H fields)</strong></td>
<td>Optional (Paraview)</td>
<td>Optional (Paraview)</td>
<td>Optional (Paraview)</td>
</tr>
<tr class="even">
<td><strong>Current density visualization</strong></td>
<td>Optional (Paraview)</td>
<td>Optional (Paraview),<br />
somewhat difficult to use and see</td>
<td>?</td>
</tr>
<tr class="odd">
<td colspan="4"><strong>Usability</strong></td>
</tr>
<tr class="even">
<td><strong>GUI available</strong></td>
<td><p>openEMS is essentially a solver with API, but provides a model viewer application with limited editing capabilities.</p>
<p>GUI for IHP workflow under development for simple/typical use cases (standard port, no multi-technology config)</p>
<p>3<sup>rd</sup> party interface for FreeCAD solid modeler available (no GDSII, not automatic meshing)</p></td>
<td><p>Palace is a pure number cruncher.<br />
IHP workflow shows model &amp; mesh in gmsh GUI.</p>
<p>GUI for IHP workflow under development for simple/typical use cases (standard port, no multi-technology config)</p></td>
<td><p>Elmer is essentially a number cruncher.</p>
<p>ElmerGUI tool is not compatible with text-based Elmer configuration used by IHP workflow. IHP workflow shows model &amp; mesh in gmsh GUI.</p>
<p>GUI for IHP workflow under development for simple/typical use cases (standard port, no multi-technology config)</p></td>
</tr>
<tr class="odd">
<td><strong>Scripting for automation</strong></td>
<td>IHP workflow uses openEMS Python API,<br />
openEMS also supports Matlab/Octave API.</td>
<td>IHP workflow uses Python with gmsh to create model, then calls FEM solver</td>
<td>IHP workflow uses Python with gmsh to create model, then calls FEM solver</td>
</tr>
<tr class="even">
<td><strong>Waveform viewer</strong></td>
<td>3rd party by script</td>
<td>3rd party by script</td>
<td>3rd party by script</td>
</tr>
<tr class="odd">
<td><strong>Input format</strong></td>
<td><p>openEMS API to create models in Python or Matlab/Octave syntax</p>
<p>With IHP workflow: GDSII layout and XML stackup</p></td>
<td><p>Palace requires FEM mesh (typically from gmsh) and solver config file.</p>
<p>With IHP workflow: GDSII layout and XML stackup</p></td>
<td><p>Elmer requires FEM mesh (typically from gmsh) and solver config file.</p>
<p>With IHP workflow: GDSII layout and XML stackup</p></td>
</tr>
<tr class="even">
<td><strong>Output format</strong></td>
<td><p>Time domain voltage &amp; current,</p>
<p>S-parameters,</p>
<p>optional Paraview visualization files</p></td>
<td><p>S-parameters,</p>
<p>optional Paraview visualization files</p></td>
<td><p>S-parameters,</p>
<p>optional Paraview visualization files</p></td>
</tr>
</tbody>
</table>

## Integrated photonics

This subsection introduces open-source tools used in PIC design flow. Many of these tools were originally developed for Analog or RF design, and are used in photonics as if (at different frequency), or with additional dedicated models. Some of the steps may use general-purpose tools like python and Octave which we do not mention here. However, dedicated packages and libraries are included. In some of the steps there are no open-source tools available, which is discussed later in the gap analysis section.

Besides functionality features, it is important to understand and consider factors related to the open-source nature of the software. These factors are outlined in the last part of this section.

### Tool descriptions

The “Device-level simulation” category groups multiple tools for electro-magnetic simulations: mode solvers, FEM-, FD-, EME, FMM, etc. based tools, etc. Some of them also allow multi-physics simulations, which is useful for packaging or thermal simulations. Several tools are general EM-simulation tools, while others are dedicated to optical domain.

**Table 2.11.** Integrated Photonics Tool Descriptions

<table>
<colgroup>
<col style="width: 21%" />
<col style="width: 78%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2">Tools Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="2">Device-level simulation</td>
</tr>
<tr class="even">
<td colspan="2"><blockquote>
<p>FEM-based simulators</p>
</blockquote></td>
</tr>
<tr class="odd">
<td>FEMWELL</td>
<td>FEMWELL is a physics simulation tool that utilises the Finite Element Method (FEM).</td>
</tr>
<tr class="even">
<td>Elmer FEM</td>
<td>Elmer is a tool that can solve a large number of partial differential equations making it an ideal tool for multiphysical problems.</td>
</tr>
<tr class="odd">
<td>Palace</td>
<td>Parallel finite element code for full-wave 3D electromagnetic simulations in the frequency or time domain, using the MFEM finite element discretization library and libCEED library for efficient exascale discretizations.</td>
</tr>
<tr class="even">
<td>Netgen/NGSolve</td>
<td>Multi-purpose finite element library.</td>
</tr>
<tr class="odd">
<td>JAX-FEM</td>
<td>JAX-FEM is Automatic Differentiation (AD) + Finite Element Method (FEM),</td>
</tr>
<tr class="even">
<td colspan="2"><blockquote>
<p>Other simulators</p>
</blockquote></td>
</tr>
<tr class="odd">
<td>MPB</td>
<td>MPB is a free and open-source software package for computing the band structures, or dispersion relations, and electromagnetic modes of periodic dielectric structures, on both serial and parallel computers.</td>
</tr>
<tr class="even">
<td>EMpy</td>
<td>ElectroMagnetic Python is a suite of algorithms widely known and used in electromagnetic problems and optics: the transfer matrix algorithm, the rigorous coupled wave analysis algorithm and more.</td>
</tr>
<tr class="odd">
<td>FDTDX</td>
<td>FDTDX is an efficient open-source Python package for the simulation and design of three-dimensional photonic nanostructures using the Finite-Difference Time-Domain (FDTD) method.</td>
</tr>
<tr class="even">
<td>meep</td>
<td>Meep is a free and open-source software package for electromagnetics simulation via the finite-difference time-domain (FDTD) method spanning a broad range of applications.</td>
</tr>
<tr class="odd">
<td>meow</td>
<td>A simple electromagnetic EigenMode Expansion (EME) tool for Python.</td>
</tr>
<tr class="even">
<td>Tiny3D</td>
<td>Tidy3D is a software package for solving extremely large electrodynamics problems using the finite-difference time-domain (FDTD) method. It requires subscription to the server, but some of the components (e.g. Mode-solver) are open.</td>
</tr>
<tr class="odd">
<td>EMEPy</td>
<td>An open-source tool for simulating EM fields in Python using the Eigenmode Expansion Method (EME).</td>
</tr>
<tr class="even">
<td>FMMAX</td>
<td>FMMAX is an implementation of the Fourier Modal Method (FMM).</td>
</tr>
<tr class="odd">
<td colspan="2">Circuit-level design</td>
</tr>
<tr class="even">
<td colspan="2">Circuit simulation</td>
</tr>
<tr class="odd">
<td>SAX</td>
<td>S-Matrices with Autograd and XLA - a scatter parameter circuit simulator and optimizer for the frequency domain based on JAX.</td>
</tr>
<tr class="even">
<td>Simphony</td>
<td>A simulator for photonic circuits, is a fundamental package for designing and simulating photonic integrated circuits with Python.</td>
</tr>
<tr class="odd">
<td>scikit-rf</td>
<td>A python package for RF/Microwave engineering</td>
</tr>
<tr class="even">
<td>Lcapy</td>
<td>A Python package for linear circuit analysis. It uses SymPy for symbolic mathematics.</td>
</tr>
<tr class="odd">
<td>PySpice</td>
<td>PySpice is a Python module which interface Python to the Ngspice and Xyce circuit simulators</td>
</tr>
<tr class="even">
<td>VACASK</td>
<td>VACASK (Verilog-A Circuit Analysis Kernel) is an analog circuit simulator. VACASK uses the OpenVAF-reloaded Verilog-A compiler for building the device models as shared libraries.</td>
</tr>
<tr class="odd">
<td>Qucs-S</td>
<td>Qucs-S is a circuit simulation program based on Qucs circuit simulator. The purpose of the Qucs-S project is to use free circuit simulation kernels (Ngspice, Qucsator, Xyce) with the unified GUI based on Qt6 toolkit.</td>
</tr>
<tr class="even">
<td>Phisim</td>
<td>Simulation software package for semiconductor integrated optical circuits. The simulation is a travelling wave finite time difference simulation of an InP based optical integrated circuit.</td>
</tr>
<tr class="odd">
<td colspan="2">Layout tools</td>
</tr>
<tr class="even">
<td>Nazca Design</td>
<td>Python based highly scriptable layout automation tool</td>
</tr>
<tr class="odd">
<td>GDSFactory</td>
<td>Python based highly scriptable layout automation tool</td>
</tr>
<tr class="even">
<td>KLayout</td>
<td>Layout editor with integrated DRC and LVS capabilities</td>
</tr>
<tr class="odd">
<td>gdstk</td>
<td>Gdstk (GDSII Tool Kit) is a C++ library for creation and manipulation of GDSII and OASIS files.</td>
</tr>
<tr class="even">
<td colspan="2">Physical layout verification</td>
</tr>
<tr class="odd">
<td colspan="2">DRC, LVS tools</td>
</tr>
<tr class="even">
<td>KLayout</td>
<td>Built in features to implement DRC / LVS rules. It includes DRC and LVS markup browser</td>
</tr>
<tr class="odd">
<td>GDSFactory</td>
<td>Python based DRC and LVS engine</td>
</tr>
</tbody>
</table>

### Feature comparison

The tables in this section provide functionality comparisons for tools in different categories.

**Table 2.12.** Integrated Photonics Tool Feature Comparison: Device-level simulation ½

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

<table style="width:100%;">
<colgroup>
<col style="width: 30%" />
<col style="width: 13%" />
<col style="width: 12%" />
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="5">Device-level simulation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td colspan="5"><strong>FEM-based</strong><br />
See also comparison table in section 2.2.</td>
</tr>
<tr class="even">
<td></td>
<td><strong>FEMWELL</strong></td>
<td><strong>Elmer FEM</strong></td>
<td><strong>Palace</strong></td>
<td><strong>Netgen/NGSolve</strong></td>
<td><strong>JAX-FEM</strong></td>
</tr>
<tr class="odd">
<td>Main purpose</td>
<td>Photonics-focused FEM toolkit</td>
<td>General multiphysics FEM solver</td>
<td>Large-scale electromagnetic simulation</td>
<td>Flexible research FEM framework</td>
<td>Differentiable FEM &amp; optimization</td>
</tr>
<tr class="even">
<td>Typical use cases</td>
<td>Waveguide modes, photonic components</td>
<td>Multiphysics engineering</td>
<td>RF/photonic cavities, resonators</td>
<td>Research FEM, custom PDEs</td>
<td>ML-coupled FEM, optimization</td>
</tr>
<tr class="odd">
<td>Primary domain</td>
<td>EM (wave optics), thermal, electrostatics</td>
<td>EM, thermal, mechanics, fluids</td>
<td>EM (Maxwell)</td>
<td>General PDEs (incl. EM)</td>
<td>Mechanics, thermal, inverse problems</td>
</tr>
<tr class="even">
<td>Full-wave 3D EM</td>
<td>⚙️</td>
<td>✅</td>
<td>✅</td>
<td>⚙️</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Time-domain support</td>
<td>⚙️</td>
<td>⚙️</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Frequency-domain support</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Eigenmode solvers</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Waveguide boundary conditions</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>Multiphysics coupling</td>
<td>⚙️</td>
<td>✅</td>
<td>⚙️</td>
<td>✅</td>
<td>⚙️</td>
</tr>
<tr class="even">
<td>Integrations</td>
<td>GDSFactory</td>
<td>GDSFactory</td>
<td>GDSFactory</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>License</td>
<td>GPL-3.0</td>
<td>GPL-2.0</td>
<td>Apache-2.0</td>
<td>LGPL-2.1</td>
<td>GPL-3.0</td>
</tr>
</tbody>
</table>

**Table 2.13.** Integrated Photonics Tool Feature Comparison: Device-level simulation 2/2

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 11%" />
<col style="width: 10%" />
<col style="width: 8%" />
<col style="width: 14%" />
<col style="width: 11%" />
<col style="width: 10%" />
<col style="width: 8%" />
<col style="width: 8%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="8">Device -level simulation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td colspan="8"><strong>Other</strong><br />
See also comparison table in section 2.2.</td>
</tr>
<tr class="even">
<td></td>
<td><strong>MPB</strong></td>
<td><strong>EMpy</strong></td>
<td><strong>FDTDX</strong></td>
<td><strong>Meep</strong></td>
<td><strong>meow</strong></td>
<td><strong>Tiny3D</strong></td>
<td><strong>EMEPy</strong></td>
<td><strong>FMMAX</strong></td>
</tr>
<tr class="odd">
<td>Simulation method</td>
<td>Planewave eigenmode solver</td>
<td><p>Transfer matrix method,</p>
<p>RCWA</p></td>
<td>FDTD</td>
<td>Multiple, incl. DTFT, mode decompositions, etc.</td>
<td>EME</td>
<td></td>
<td>EME</td>
<td>RCWA</td>
</tr>
<tr class="even">
<td>Domain</td>
<td>Frequency</td>
<td>Frequency</td>
<td>Time</td>
<td>Time</td>
<td>Frequency</td>
<td>Frequency</td>
<td>Frequency</td>
<td>Frequency</td>
</tr>
<tr class="odd">
<td>Output data format</td>
<td>HDF5</td>
<td></td>
<td></td>
<td>HDF5</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Documentation</td>
<td>Good</td>
<td>Limited</td>
<td>Good</td>
<td>Good</td>
<td>Good</td>
<td></td>
<td>Limited</td>
<td>Limited</td>
</tr>
<tr class="odd">
<td>Acceleration</td>
<td>Multi-core</td>
<td></td>
<td>JAX-based</td>
<td>Multi-core</td>
<td></td>
<td></td>
<td></td>
<td>JAX-based</td>
</tr>
<tr class="even">
<td>Integrations</td>
<td>GDSFactory</td>
<td></td>
<td></td>
<td>GDSFactory</td>
<td>GDSFactory, SAX, Tiny3D</td>
<td>GDSFactory</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>License</td>
<td>GPL-2.0</td>
<td>MIT</td>
<td>MIT</td>
<td>GPL-2.0</td>
<td>Apache-2.0</td>
<td>See “Other”</td>
<td>MIT</td>
<td>MIT</td>
</tr>
<tr class="even">
<td>Other</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>Part of a paid software suite</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

**Table 2.14.** Integrated Photonics Tool Feature Comparison: Circuit simulation

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 10%" />
<col style="width: 11%" />
<col style="width: 7%" />
<col style="width: 7%" />
<col style="width: 9%" />
<col style="width: 8%" />
<col style="width: 22%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="8"><p>Circuit simulation</p>
<p>See also comparison table in section 2.2.</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>SAX</strong></td>
<td><strong>Simphony</strong></td>
<td><strong>scikit-rf</strong></td>
<td><strong>Lcapy</strong></td>
<td><strong>PySpice</strong></td>
<td><strong>VACASK</strong></td>
<td><strong>Qucs-S</strong></td>
<td><strong>Phisim</strong></td>
</tr>
<tr class="even">
<td>Simulation methods</td>
<td>S-parameters</td>
<td>S-parameters</td>
<td>S-parameters</td>
<td></td>
<td>SPICE</td>
<td>SPICE</td>
<td>SPICE</td>
<td>TW-FTD</td>
</tr>
<tr class="odd">
<td>Application domain</td>
<td>Photonic / RF</td>
<td>Photonic / RF</td>
<td>RF</td>
<td></td>
<td>Electronic circuits</td>
<td>Analog circuits</td>
<td>RF / analog circuits</td>
<td>Photonics, incl. amplifiers</td>
</tr>
<tr class="even">
<td>Symbolic</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Data formats</td>
<td>Netlist / API</td>
<td>Python API</td>
<td>Touchstone, Z/Y/ABCD, N-port definitions</td>
<td>Netlist</td>
<td>Spice netlist</td>
<td>Verilog-A</td>
<td></td>
<td>Custom, python API</td>
</tr>
<tr class="even">
<td>Integrations</td>
<td>GDSFactory</td>
<td>SiEPIC and SiPANN</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>License</td>
<td>Apache-2.0</td>
<td>MIT</td>
<td>BSD-3-Clause</td>
<td>LGPL-2.1</td>
<td>GPL-3.0</td>
<td>GPL-3.0</td>
<td>GPL-2.0</td>
<td>GPL-3.0</td>
</tr>
<tr class="even">
<td>Other</td>
<td></td>
<td></td>
<td>General-purpose library</td>
<td></td>
<td></td>
<td></td>
<td>Simulation with backends</td>
<td></td>
</tr>
</tbody>
</table>

**Table 2.15.** Integrated Photonics Tool Feature Comparison: Layout tools

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

<table style="width:100%;">
<colgroup>
<col style="width: 38%" />
<col style="width: 13%" />
<col style="width: 15%" />
<col style="width: 17%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="4">Layout tools</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>Nazca Design</strong></td>
<td><strong>GDSFactory</strong></td>
<td><strong>KLayout</strong></td>
<td><strong>gdstk</strong></td>
</tr>
<tr class="even">
<td>Parametric cell support with PyCellStudio</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Parametric cell support with Python</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>DRC engine</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>LVS engine</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>PEX engine</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Hierarchical layout support</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>Multiuser support (editable, read-only)</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Back annotation between schematic and layout</td>
<td>❌</td>
<td><p>❌</p>
<p>(paid version)</p></td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>License</td>
<td>GPL-3.0</td>
<td>MIT</td>
<td>GPL-2.0</td>
<td>BSL-1.0</td>
</tr>
</tbody>
</table>

**Table 2.16.** Integrated Photonics Tool Feature Comparison: Physical Verification

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

| Features           | Physical verification |                   |
|--------------------|-----------------------|-------------------|
|                    | **KLayout**           | **GDSFactory**    |
| DRC                | ✅                    | ✅                |
| LVS                | ✅                    | ✅                |
| Scripting language | Custom                | Python            |
| GUI mode           | ✅                    | ❌ (paid version) |
| Batch mode         | ✅                    | ✅                |
| Markup browser     | ✅                    | ❌ (paid version) |
