# Advanced-Physical-Design-Using-Openlane-Skywater130
The following are summary of learnings from the workshop on "Advanced Physical Design Using Openlane Skywater130" orginized by VSD abd sponsored by Efabless from 3rd August-7th August 2022.

# Overview of Openlane
Openlane is a RTL2GDS digital design flow, using various open-source tools to perform various stages in the ASIC physical design process.
The foundry technology used is skywater130A, which is a 130nm technology. 
The skywater130 PDK is opensourced by Google-Skywater and the PDK intergation support for various opensource tools is provided by openpdk project.

Following table lists the various steps and corresponding tools in RTL to GDS flow.

  | Step | Tool Used | 
  | --- | --- |
  | Synthesis | Yosys and abc |
  | Floorplan | |
  | STA (Post Synthesis, Post CTS, Post Route)  | OpenSTA |
  | Placement | |
  | Clock Tree Synthesis(CTS) | TritonCTS |
  | Routing | TritonRoute | 
  | GDS | Magic |

*Note*:
- The entire openlane flow has few more steps, namely LEC, DFT Insertion, AntDiode Insertion and Physical Verification(DRC and LVS).
- But as part of the workshop these were not covered in labs.

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
- The design needs to be present in the 

## FAQ:
- What if I want to analyze/iteration an existing run in interactive mode?    
`prep -design <design-folder> -tag <run-folder>`   
This is useful to continue from last stage of an existing run.   

- What if I want to do fresh re-run in interactice mode?   
`prep -design <design-folder> -tag <run-folder> -overwrite`   









