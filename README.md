# Advanced-Physical-Design-Using-Openlane-Skywater130
The following are summary of learnings from the workshop on "Advanced Physical Design Using Openlane Skywater130" orginized by VSD abd sponsored by Efabless from 3rd August-7th August 2022. The objective of the workshop was to get hands-on experience with Physical Design using the Openlane flow on an example design. It covered various configuration options available for every stage of the process, steps to analyze the logs & results and further introduced basic ECO flows when there are timing violations. Furthermore, it went through the flow of creating, characterizing and using custom inverter std cell into the openlane process. The workshop vsd-iat web portal provided videos on the theory followed by video walkthrough on labs and an optional assignment/exploration part.

# Overview of Openlane
Openlane is a RTL2GDS  flow, using multiple open-source tools to perform the stages in the ASIC physical design process.
Openlane is used with skywater130nm PDK from Google-Skywater. 
Sywater130 PDK is open-sourced by Google-Skywater and its intergation support for the opensource tools is provided by the `openpdk` project.

Following table lists the various steps and corresponding tools in RTL to GDS flow.

  | Step | Tool Used | Run Command |
  | --- | --- | --- |
  | Synthesis | Yosys and abc | `run_synthesis` |
  | Floorplan | init_fp, io_placer, pdn | `run_floorplan` |
  | STA (Post Synthesis, Post CTS, Post Route)  | OpenSTA | `sta` |
  | Placement | RePlace(Global Placement) and OpenDP(Detailed Placement) | `run_placement` |
  | Clock Tree Synthesis(CTS) | TritonCTS | `run_cts`|
  | Routing | FastRoute(Global Route) and TritonRoute(Detailed Route) | `run_routing` |
  | GDS | Magic | *From Magic Gui* -> Save GDS |

*Note*:
- The complete Openlane flow has few more steps, namely LEC, DFT Insertion, AntDiode Insertion and Physical Verification(DRC and LVS).
- But these were not covered as part of workshop labs.

# Running Openlane 
Openlane is run in interactive mode in the workshop to execute and analyze each of the steps individually.       
Example design from openlane of picorv32a was chosen, which is a RISC-V processor design.    
The openlane docker distribution is used in the workshop.   

To load openlane docker setup execute following:     
`make mount`

Start OpenLane interactively:    
`./flow.tcl -interactive`

On the OpenLane shell, do design preparation:       
`package require openlane 0.9`    
`prep -design picorv32a`

*Note*:
- The design needs to be present in the <designs> folder
- This step mainly generates the merged.lef in the run area, which is obtained by merging the technology lef file and the stdcell lef file

## FAQ:
- What if I want to analyze/iteration an existing run in interactive mode?    
`prep -design <design-folder> -tag <run-folder>`   
This is useful to continue from last stage of an existing run.   

- What if I want to do fresh re-run in interactice mode?   
`prep -design <design-folder> -tag <run-folder> -overwrite`

# Running Synthesis

## Running Synthesis with Custom Stdcell Cell









