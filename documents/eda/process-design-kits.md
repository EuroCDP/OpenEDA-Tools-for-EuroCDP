# Process design kits

The availability of tools, whether proprietary or open source, does not by itself constitute a design environment. Since the objective of the design process is the implementation of a functional hardware block, it is inherently tied to a specific technological platform selected for this purpose. The link between design tools and the fabrication process is provided by the **Process Design Kit (PDK)**, which consists of a set of libraries compatible with the design tools and exposes the underlying technology to the designer. A PDK is typically delivered together with process specifications, layout rule manuals, library-specific documentation, setup guidelines, and design examples.

Traditionally, PDKs are not publicly available and are distributed to customers under non-disclosure agreements (NDAs). In 2020, for the first time, an open-source PDK—the **Google–SkyWater PDK**—was released under the permissive **Apache 2.0** license. This PDK targets the **SKY130A/B** process of the SkyWater foundry and represents the first manufacturable PDK made available to the open-source community. Following the release of SKY130, **GlobalFoundries** opened access to process information by publishing the **GF180MCU A/B/C** PDKs one year later. In 2023, **IHP** followed with the publication of the **IHP Open PDK** for the **SG13G2** process. More recently, in late October 2025, the Chinese foundry **ICSprout** released partial information about its **55 nm CMOS** process. This section provides a brief overview and comparison of the manufacturable and non-manufacturable PDKs currently available within the open-source ecosystem.

**Table 3.1**. Open source PDKs.

✅ = Fully supported ⚙️ = Limited or indirect support ❌ = Not supported

<table>
<colgroup>
<col style="width: 36%" />
<col style="width: 15%" />
<col style="width: 16%" />
<col style="width: 15%" />
<col style="width: 15%" />
</colgroup>
<thead>
<tr class="header">
<th>Features</th>
<th colspan="4">Manufacturable open source PDK comparison</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><strong>SKY130</strong></td>
<td><strong>GF180</strong></td>
<td><strong>IHP-SG13GS</strong></td>
<td><strong>ICSprout55</strong></td>
</tr>
<tr class="even">
<td>CMOS compatible</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>CMOS minimal feature</td>
<td>150 nm</td>
<td>280 nm</td>
<td>130 nm</td>
<td>55 nm</td>
</tr>
<tr class="even">
<td>Standard cells</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="odd">
<td>IO cells</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
</tr>
<tr class="even">
<td>SRAM</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Analog primitives</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Triple well</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Maximum gate voltage</td>
<td>20</td>
<td>10</td>
<td>3.5</td>
<td>❌</td>
</tr>
<tr class="even">
<td>BJT devices</td>
<td>✅</td>
<td>✅</td>
<td>Lateral</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>HBT devices</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>LDMOS devices</td>
<td>❌</td>
<td>✅</td>
<td>⚙️</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Diodes</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Varactors</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Photodiode</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Diffusion resistors</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>Polysilicon resistors</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>TFR resistors</td>
<td>❌</td>
<td>❌</td>
<td>⚙️</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>MiM Capacitor</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr class="even">
<td>Resistive RAM</td>
<td>✅</td>
<td>❌</td>
<td>⚙️</td>
<td>❌</td>
</tr>
<tr class="odd">
<td>BEOL</td>
<td>1 local interconnect<br />
5 metal layers</td>
<td>5 thin<br />
1 thick<br />
metal layers</td>
<td>5 thin<br />
2 thick<br />
metal layers</td>
<td>5 thin<br />
2 thick<br />
metal layers</td>
</tr>
<tr class="even">
<td>Available via MPW services</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>⚙️</td>
</tr>
</tbody>
</table>

Apart from the manufacturable PDK’s there are some non-manufacturable (predictive) ones mainly used in education. At mature nodes, the OSU standard cell library and the NanGate45 library, both based on the FreePDK45 technology, provide realistic CMOS standard cells widely used for education, benchmarking, and tool development. The FreePDK45 has also a 3D IC version of the original FreePDK45. For advanced-node research there are two alternatives: (1) FreePDK15 PDK and (2) ASAP7 PDK, which offers a predictive, foundry-agnostic 7 nm FinFET technology with multiple standard-cell architectures, enabling exploration of modern scaling challenges such as restrictive design rules and track-based layouts. Together, these open PDKs form a representative stack for studying digital design methodologies across technology generations.

The manufacturable and open source PDKs, namely **SKY130, GF180, SG13G2, ICSprout55** are generally compatible with the open-source tools discussed in Section 2. Owing to the highly structured and automated nature of digital design, well-established standards exist for abstract PDK data. Accordingly, foundries typically provide digital libraries (often referred to as *views*) in standardized formats such as **CDL, LIB, LEF, SPICE, GDS, and Verilog**.

In contrast, within the **analog, AMS, and RF** domains, standardization is considerably less mature, and PDK data formats are often specific to individual design tools. Schematic diagrams and symbols are tool specific and not portable between the tools. Although SPICE language is well established, the way that the open-source simulators handle it is different, which produces inconsistencies between the libraries for different tools. Recent advances in **Verilog-A** modeling support within the open-source ecosystem have contributed to reducing inconsistencies among behavioral models. A similar trend applies to **Python-based parametric cells (PyCells)**, which provide a portable mechanism for describing layout generators across both open-source and proprietary tools, such as **PyCellStudio, KLayout, and XIC**.

Despite these improvements, a **significant portion of technology information is still represented in** **non-standard, tool-specific formats**. This lack of standardization is particularly evident in **physical verification data**, including **design rule checking (DRC)** and **layout versus schematic (LVS)** rule decks, where rules must be implemented and maintained using proprietary or tool-dependent rule languages. A comparable situation exists for **parasitic extraction** and **electromagnetic (EM) simulation**, in which the absence of a common representation results in multiple, tool-specific descriptions of identical technological data. The last observation produces a significant overhead of work related to the PDK information maintainability.
