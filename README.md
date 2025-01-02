# NASCOM_VSD_WORKSHOP
## DAY-1 (Inception of open source EDA , OpenLANE and sky130pdk):
  
 ## DAY-1-Theory
 ![Openlane_flow](https://github.com/user-attachments/assets/737be694-7ab0-4275-8a04-68a966354306)
 Courtsey:MD.Shalaen,e-fabless and VSD

  The current project uses opensource EDA tools for complete RTL-GDSII generation.Opensource EDA tools are tools which make ASIC design cheaper and collaborative. OpenLane is a package of opensource tools which are required at various stages of ASIC design. For example,Yosys is required for synthesys,OpenSTA is required for static-timing-analysis. Here SKY130 PDK has been used for this opensource SOC(System on Chip)development. In the synthesis stage, the verilog code of a riscv processor (namely picorv32a.v) is synthesised to produce sky-130 technology mapped std. cells.

## DAY-1-Lab
**Design Preparation**
![prep-design](https://github.com/user-attachments/assets/81d69433-ab4e-4cdc-9e92-9b49c1d0030f)


**Running Synthesis**
![Synthesis_succrssful](https://github.com/user-attachments/assets/8d269b5c-7851-4d2c-9488-5179a0a1de3e)


**Flop Ratio Calculation**
![Flop_ratio](https://github.com/user-attachments/assets/be6dbead-9af0-4651-a406-4e47494075f7)
   
   **Flop Ratio=(No. of D-ff/No. of total std. cells)=1613/14876=0.108429=10.84%**



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


  **Die Area Calculation**
![picorv32a_floorplan def](https://github.com/user-attachments/assets/9b9da829-3e56-4ceb-a17e-93ed2f831694)



   **Die width=((660685-0)/1000) =660.685 Microns;**
   
   **Die Height= ((671405-0)/1000) = 671.405 Microns;**
   
   **Die Area = 660.685*671.405=443587.2124 Microns**




**Invoking magic**
![Running magic](https://github.com/user-attachments/assets/ef7a72b2-882c-444f-b3d5-6e521d930a1f)

![magic1](https://github.com/user-attachments/assets/9a178563-39a0-4519-a34a-c8eca1e25f8c)


## DAY_3(Design Library Cells and ngspice Characterisation)

## DAY-3-Theory

**Standard CMOS Inverter**

   CMOS inverter consists of a PMOS connected to VDD and NMOS connected to VSS or ground.The drain terminals of the two MOS are connected together.CMOS inverters are used for its low power consumption, high noise margins, and ability to drive large currents.Ngspice has been used to simulate the behaviour of CMOS inverter,where the transition from low to high output voltage corresponds to the switching behavior of the inverter.


## DAY-3-Lab


**Invoking inverter layout**

 
  magic -T sky130A.tech sky130_inv.mag &


![vsdinvlayout](https://github.com/user-attachments/assets/e4819f8c-ae92-4df8-aa8b-3e0a6303607b)



**Creating Spice file for ngspice :**

To generate a SPICE file that can be used with Ngspice, follow these steps in the Tkcon window:

**1. extract all** ( Extracting netlist information)

**2. ext2spice** cthresh 0 rthresh 0 ( Generating spice netlist with defined threshold)

**3.ext2spice** ( Exporting spice netlist)

![Spice_netlist](https://github.com/user-attachments/assets/407d9c2d-e24a-40df-8b43-9601f8ccb159)


**Modifying spice netlist with pshort.lib, nshort.lib**

For modification following lines to be included in the spice file.

.include ./libs/pshort.lib


.include ./libs/nshort.lib


![inv_sp](https://github.com/user-attachments/assets/d6beb817-f5fd-49a1-ab93-edc90db0094d)



**Simulation with Ngspice**

ngspice  sky130_inv.spice   ( Command for launching Ngspice )

![sp_simulation](https://github.com/user-attachments/assets/d99eef4c-d95e-4612-84b4-57d0e354e229)

Shows error.The cause is unknown.








  

