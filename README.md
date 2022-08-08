# Advanced-Physical-Design-Using-Openlane-Skywater130
The following are summary of learnings from the workshop on "Advanced Physical Design Using Openlane Skywater130" orginized by VSD, sponsered by efabless from 3rd August-7th August 2022.

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
- The entire openlane flow has few more steps, namely LEC, AntDiode Insertion, DRC and LVS.
- But as part of the workshop these were not covered.

# Running Openlane 
Openlane is run in interactive mode in the workshop to execute and analyze each of the steps individually.
Example design from openlane of picorv32a was chosen.
The openlane docker distribution is used in the workshop.
To load openlane docker setup execute following:   
`make mount`

This will open the openlane shell.
Next, we need to set the openlane package version:    
`package require openlane 0.9`    








