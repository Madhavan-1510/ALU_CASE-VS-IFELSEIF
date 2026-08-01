# Comparative Study of 32-Bit ALU Implementations Using Case and If-Else Constructs

## Aim: 
Write a Verilog code for 32 32-bit ALU supporting four logical and four arithmetic operations, use case statement and if statement for ALU behavioral modeling. 

To verify the Functionality using Test Bench 

Synthesize and compare the results using if and case statements 

Identify Critical Path and constraints

## Tool Required: 
 Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim) 

 Synthesis: Genus 

## Design Information and Block Diagram: 
The ALU will take in two 32-bit values and a control line. An Arithmetic unit does the following tasks like addition, subtraction, multiplication and logical operations. As the input is given in 32-bit, we get a 32-bit output. The arithmetic will show only one output at a time, so a selector is necessary to select one of the operators. 

 <img width="668" height="344" alt="image" src="https://github.com/user-attachments/assets/b5f95c0d-1fd6-4c3c-9a35-11eb9c86cba3" />

#### Figure No 1: Block Diagram of 32 Bit ALU 

## Creating a Workspace:
Create a folder in your name (Note: Give the folder name without any spaces) and create a new sub-directory named Exp4 or alu_bl_model for the design. Then, open a terminal from the Sub-Directory.

## Creating Source Codes
In the Terminal window, type gedit <filename>.v (ex: gedit alu_case.v).

A Blank Document opens up into which the following source code can be typed.

(Note: File name should be with HDL Extension)

To verify the Functionality using the Test Bench

#### Source Code – Using Case Statement :
(Include program here)

Use the Save option or Ctrl+S to save the code, or click on the save option from the top-right corner and close the text file.

#### Creating a Test Bench:
Similarly, create your test bench using gedit <filename_tb>.v to open a new blank document (alu_case_tb.v).

#### Test Bench :
(Include test bench program here)

Use the Save option or Ctrl+S to save the code, or click on the save option from the top-right corner and close the text file.

#### Source Code - Using If Statement :
(Include program here)

#### Test Bench :
(Include program here)

Functional Simulation for each design

Invoke the cadence environment by typing the commands below

tcsh (Invokes C-Shell)

source /cadence/install/cshrc (mention the path of the tools)

(The path of cshrc could vary depending on the installation destination)

After this, you can see the window like below

To Launch the Simulation tool

•linux:/> nclaunch -new& // “-new” option is used for invoking NCVERILOG for the first time for any design

or

•linux:/> nclaunch& // On subsequent calls to NCVERILOG

It will invoke the nclaunch window for functional simulation. We can compile, elaborate and simulate it using Multiple Steps.

Setting Multi-step simulation

Select Multiple Step and then select “Create cds.lib File” as shown in the figure below

Click the .cds.lib file and save the file by clicking on the Save option

Fcds.lib file Creation

Save .lib file and select the correct option for cds.lib file format based on the HDL Language and Libraries used.

Select “Don’t include any libraries (verilog design)” from “New cds.lib file” and click on “OK” as in the figure below.

We are simulating a verilog design without using any libraries

Click “OK” in the “nclaunch: Open Design Directory” window, as shown in the figure below
<img width="422" height="267" alt="image" src="https://github.com/user-attachments/assets/70dcd6d9-0691-4fb4-8f01-28b833eaa670" />

#### Fig 2: Selection of Don’t include any libraries
An ‘NCLaunch window’ appears as shown in the figure below

Left side, you can see the HDL files. The right side of the window has Worklib and snapshots directories listed.

Worklib is the directory where all the compiled codes are stored, while Snapshot will have the output of elaboration, which in turn goes for simulation.

To perform the function simulation, the following three steps are involved: Compilation, Elaboration and Simulation.
<img width="771" height="840" alt="image" src="https://github.com/user-attachments/assets/68d267d5-e058-483a-86c4-9ab6596420d5" />

#### Fig 3: Nclaunch Window

#### Step 1: Compilation:
– Process to check the correct Verilog language syntax and usage

Inputs: Supplied are Verilog design and test bench codes

Outputs: Compiled database created in mapped library if successful, generates report else error reported in log file

#####  Steps for compilation:
	Create work/library directory (most of the latest simulation tools creates automatically)
 
	Map the work to library created (most of the latest simulation tools creates automatically)
 
 Run the compile command with compile options
 
i.e Cadence IES command for compile: ncverilog +access+rwc -compile filename.v

Left side select the file and in Tools: launch verilog compiler with current selection will get enable. Click it to compile the code

Worklib is the directory where all the compiled codes are stored while Snapshot will have output of elaboration which in turn goes for simulation
<img width="771" height="840" alt="image" src="https://github.com/user-attachments/assets/0f40d863-b915-42a1-84bc-e5296ca58120" />

#### Fig 4: Compiled database in WorkLib
After compilation, it will come under worklib. You can see on the right side window

select the test bench and compile it. It will come under Worklib. Under Worklib, you can see the module and test bench.

The cds.lib file is an ASCII text file. It defines which libraries are accessible and where they are located. It contains statements that map logical library names to their physical directory paths. For this Design, you will define a library called “worklib”

#### Step 2: Elaboration:
To check the port connections in a hierarchical design

Inputs: Top-level design/test bench Verilog codes

Outputs: Elaborate database updated in the mapped library if successful, generates a report, else error reported in the log file

#####  Steps for elaboration

– Run the elaboration command with elaborate options

1.It builds the module hierarchy

2. Binds modules to module instances
   
3.Computes parameter values

4. Checks for hierarchical name conflicts
   
5.It also establishes net connectivity and prepares all of this for simulation

After elaboration, the file will come under snapshot. Select the test bench and simulate it.
<img width="771" height="840" alt="image" src="https://github.com/user-attachments/assets/b20767f3-52b8-4cdd-a266-17bc57d57407" />

#### Fig 5: Elaboration Launch Option

#### Step 3: Simulation:
– Simulate with the given test vectors over a period of time to observe the output behaviour.

Inputs: Compiled and Elaborated top-level module name

Outputs: Simulation log file, waveforms for debugging

Simulations allow dumping design and test bench signals into a waveform

Steps for simulation – Run the simulation command with simulator options
<img width="915" height="665" alt="image" src="https://github.com/user-attachments/assets/05d0815b-cf8c-4327-9b78-7a4c626e947d" />

#### Fig 6: Design Browser window for simulation
CASE SIMULATION
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/5c2fba00-424f-458e-b66b-4cdb30ad16ed" />


IF ELSE IF SIMULATION
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/fd3d9d93-6742-467c-b04a-12535d78d8c6" />

#### Fig 7: Simulation Waveform Window

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)

##### Performing Synthesis

##### Synthesize Design

Run the synthesis Process one time for each code and make sure the output File names are changed accordingly

The Liberty files are present in the library path,

• The Available technology nodes are 180nm,90nm and 45nm.

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist. Or use source run.tcl command in the terminal window to view the netlist, and a log file will be created in the working folder.

#### Fig 8: Synthesis RTL Schematic using case and ifelseif construct
CASE 
<img width="1327" height="927" alt="image" src="https://github.com/user-attachments/assets/92895fbd-1688-48f9-a026-02d5dc915d79" />

IFELSEIF
<img width="1327" height="927" alt="image" src="https://github.com/user-attachments/assets/335a6967-117c-4200-9ea4-3d005b4c8925" />


#### Fig 9: Area report of case and ifelseif construct
CASE
<img width="1917" height="415" alt="image" src="https://github.com/user-attachments/assets/c687785d-11c9-42b1-bdf8-81d58c3961c2" />

IFELSEIF 
<img width="1917" height="518" alt="image" src="https://github.com/user-attachments/assets/4f25bda7-6557-4d62-823a-e2da9d85c1a7" />


#### Fig 10: Power Report of case and ifelseif construct
CASE
<img width="1917" height="507" alt="image" src="https://github.com/user-attachments/assets/cd80b2e0-e0ee-4167-ba00-62e9deded714" />

IFELSEIF
<img width="1916" height="487" alt="image" src="https://github.com/user-attachments/assets/d26c8fac-753c-4f71-b351-e2cd8adb1f75" />

#### Fig 11: Timing Report of case and ifelseif construct
CASE
<img width="1917" height="1043" alt="image" src="https://github.com/user-attachments/assets/7adb987e-e2b7-49e0-babd-bb7806b092d6" />

IFELSEIF
<img width="1917" height="1047" alt="image" src="https://github.com/user-attachments/assets/f434cb1f-76d5-4c98-b1d3-e04831ae0dcb" />


#### Fig 12: Tabulate Area,Power and Timing Report Comparision of ALU using case and ifelseif construct
| Metric | `alu_case` | `alu_ifelseif` | Difference |
|--------|-----------:|---------------:|-----------:|
| Cell Count | 1296 | 1296 | 0 |
| Cell Area | 10265.078 | 10265.078 | 0 |
| Net Area | 0.000 | 0.000 | 0 |
| Total Area | 10265.078 | 10265.078 | 0 |
| Leakage Power (W) | 3.72726e-05 | 3.72726e-05 | 0 |
| Internal Power (W) | 5.07450e-04 | 5.07450e-04 | 0 |
| Switching Power (W) | 2.18891e-04 | 2.18891e-04 | 0 |
| Total Power (W) | 7.63614e-04 | 7.63614e-04 | 0 |
| Critical Path Delay (ps) | 9717 | 9717 | 0 |
| Timing Path Status | Unconstrained | Unconstrained | Same |
| Startpoint | `b[2]` | `b[2]` | Same |
| Endpoint | `y[31]` | `y[31]` | Same |
## Result
The 32-bit ALU implemented using behavioural **case** statements and **if–elseif** constructs was successfully verified using Cadence Incisive (ncvlog/ncsim) for all test vectors. Both implementations produced identical functional outputs and were successfully synthesized using Cadence Genus, which generated the corresponding gate-level netlists along with area, timing, and power reports.

A comparative analysis of the synthesis reports showed **no measurable difference** between the two implementations. Both designs synthesized to the same hardware, resulting in an identical cell count, total cell area (10265.078), critical path delay (9717 ps), and total power consumption (7.63614 × 10⁻⁴ W). This indicates that although the RTL descriptions differ syntactically, the synthesis tool optimized both behavioural descriptions into an equivalent gate-level implementation. Consequently, neither the case-statement-based ALU nor the if–elseif-based ALU demonstrated any advantage in terms of area, timing, or power for the given design and synthesis constraints.

