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

# Interactive Openlane


