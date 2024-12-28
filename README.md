# NASCOM_VSD_WORKSHOP
## DAY-1 (Inception of open source EDA , OpenLANE and sky130pdk):
  
 ## DAY-1-Theory
 ![Openlane_flow](https://github.com/user-attachments/assets/737be694-7ab0-4275-8a04-68a966354306)
 Courtsey:MD.Shalaen,e-fabless and VSD

  The current project uses opensource EDA tools for complete RTL-GDSII generation.Opensource EDA tools are tools which make ASIC design cheaper and collaborative. OpenLane is a package of opensource tools which are required at various stages of ASIC design. For example,Yosys is required for synthesys,OpenSTA is required for static-timing-analysis. Here SKY130 PDK has been used for this opensource SOC(System on Chip)development. In the synthesis stage, the verilog code of a riscv processor (namely picorv32a.v) is synthesised to produce sky-130 technology mapped std. cells.

## DAY-1-Lab 
![Synthesis_succrssful](https://github.com/user-attachments/assets/8d269b5c-7851-4d2c-9488-5179a0a1de3e)
![prep-design](https://github.com/user-attachments/assets/81d69433-ab4e-4cdc-9e92-9b49c1d0030f)
![Flop_ratio](https://github.com/user-attachments/assets/be6dbead-9af0-4651-a406-4e47494075f7)



## DAY-2 (Floorplanning , Placement and Library cells):

  ## DAY-2-Theory:
     
     
  After synthesis is done,the next stge is floorplanning. In this stage, the core area and die area are decied using proper utilisation factor.

                        
                        Utilisation factor=(Area occupied by gate-level netlist/Total area of core)
  
  **Preplaced Cell**: Prior to the placement of the standard cell,some prdefined macros and cells are placed in order to perform some additioanal optimisation on design.

  **Decoupling Capacitors:** Decap cells are used to manage voltage fluctuations.

  **Power Planning:** A grid of VDD and VSS are used to ensure proper power delivary.

  **Pin placement:** I/p and O/P pims are properly placed for efficient routing.

## DAY-2 Lab: 
**Running floorplan**
![run_floorplan](https://github.com/user-attachments/assets/7ba4a452-76bb-4a0e-b91a-a242344ae3c8)

![picorv32a_floorplan def](https://github.com/user-attachments/assets/9b9da829-3e56-4ceb-a17e-93ed2f831694)

**Invoking magic**

![Running magic](https://github.com/user-attachments/assets/ef7a72b2-882c-444f-b3d5-6e521d930a1f)

![magic1](https://github.com/user-attachments/assets/9a178563-39a0-4519-a34a-c8eca1e25f8c)




  

