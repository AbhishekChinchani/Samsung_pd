## Day-0-Installation

	
 <details>
 <summary>icc2_shell </summary>
ICC2 compiler is a complete netlist-to-GDSII implementation system that includes early design exploration and prototyping, detailed design planning, block implementation, chip assembly, and sign-off-driven design closure. It is invoked using the command icc2_shell     

Below is the screenshot showing the successful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e0e2b03e90d202a407834f16c21cc39f0c6500c/Samsung_PD_%23day0/icc2.png">
</details>
 <details>
 <summary>dc_shell</summary>
Design Compiler is the command line interface of Synopsys synthesis tool. It includes innovative topographical technology that enables a predictable flow resulting in faster time to results.It is invoked using the command dc_shell    

Below is the screenshot showing the successful launch:

<img width="1085" alt="dc_shell" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b8c436bb42d7573a753b7de1dd16dab7a0637486/Samsung_PD_%23day0/dc_shell.png">
</details>

<details>
 <summary>pt_shell</summary>
PrimeTime is a Static Timing Analysis (STA) tool from Synopsys. This is a simple description to use PrimeTime for the VLSI class project. It is invoked using the command pt_shell   

Below is the screenshot showing the successful launch:

<img width="1085" alt="pt_shell" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b8c436bb42d7573a753b7de1dd16dab7a0637486/Samsung_PD_%23day0/pt_shell.png">
</details>

<details>
 <summary>lc_shell</summary>
Library Compiler (LC) parses this textual information for completeness and correctness, before converting it to a format, used globally by all Synopsys applications. It is invoked using the command lc_shell.   

Below is the screenshot showing the successful launch:

<img width="1085" alt="lc_shell" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b8c436bb42d7573a753b7de1dd16dab7a0637486/Samsung_PD_%23day0/lc_shell.png">
</details>

<details>
 <summary>gtkwave</summary>
GTKWave is the best free wave viewer and is the recommended viewer by the Icarus Verilog simulation tool. The GTKWave software is used as a simulation tool to verify the Verilog design code through a test bench. It is invoked using the command gtkwave.   

Below is the screenshot showing the successful launch:

<img width="1085" alt="gtkwave" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b8c436bb42d7573a753b7de1dd16dab7a0637486/Samsung_PD_%23day0/gtkwave.png">
</details>

<details>
 <summary>yosys</summary>
Yosys is a framework for RTL synthesis. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. It is invoked using the command yosys.

Below is the screenshot showing the successful launch:

<img width="1085" alt="yosys" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b8c436bb42d7573a753b7de1dd16dab7a0637486/Samsung_PD_%23day0/yosys.png">
</details>

<details>
 <summary> Summary </summary>
	
I invoked all the shells using the given commands and attached corresponding screenshots

</details>	

# Day-1-Introduction to Verilog RTL Design and Synthesis

 <details>
 <summary>Introduction to RTL-Design, Test-bench, Simulators</summary>
	 
 **RTL**: It is a design abstraction that models a synchronous digital circuit in terms of the data flow between hardware registers, and the logical operations performed on those signals. In RTL code we write code for combinational and sequential circuits like that of HDL, and VHDL.

 
**Testbench**: It is a program written in any language for the purposes of exercising and verifying the functional correctness of the hardware model as coded. We write this testbench in Verilog. Using this testbench we apply a stimulus to the RTL Design and verify its functionality by checking the output.

**Simulator**: RTL design is checked for adherence to its design specification using simulation by giving simple inputs. The tool used for this purpose is called Simulator. The simulator looks at the input changes and then evaluates the output. It produces an output in the form of a .vcd file.  

</details>	
 <details>
 <summary>Labs on examples of iverilog and gtkwave</summary>

 We performed all the lab examples on the Linux operating system.

 **Iverilog**: Icarus Verilog is an implementation of the Verilog hardware description language compiler that generates netlists in the desired format (EDIF). It supports the 1995, 2001, and 2005 versions of the standard, portions of SystemVerilog, and some extensions.

 **Gtkwave**: GTKWave is a fully featured GTK+ based wave viewer for Unix, Win32, and Mac OSX which reads LXT, LXT2, VZT, FST, and GHW files as well as standard Verilog VCD/EVCD files and allows their viewing.

 We made a directory namely VLSI and inside that directory we cloned vsdflow repository. This repository consists of the required .lib files and verilog codes for practice. 

 Below is the output wave form in gtkwave generated by performing a simulation of good_mux using iverilog. 
 
 The syntax of the code is: iverilog RTL_design_code Testbench
 

<img width="1085" alt="gtkwaveform" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/16a2cefdc8b86645cce423a1fe983085cd3f6197/gtkwave_good_mux.png">
RTL design code of the 2:1 MUX
<img width="1085" alt="good_mux_design_code" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/fa2af7bbb534461466344e6a065345318906e4c5/design%20_of_the_mux.png">
Testbench for 2:1 MUX
<img width="1085" alt="testbench" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/16a2cefdc8b86645cce423a1fe983085cd3f6197/testbench_good_mux.png">

</details>
<details>
 <summary>Introduction to Yosys</summary>

 **Synthesis**: Synthesis in VLSI is the process of converting your code (program) into a circuit. In terms of logic gates, synthesis is the process of translating an abstract design into a properly implemented chip. It is a process of converting a RTL code into a gate level netlist. The tool used for this purpose is called synthesizer.

 **Yosys** : Yosys is a framework for RTL synthesis and more. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. Yosys is the core component of most our implementation and verification flows.

**Verification of synthesized design** : In order to make sure that there are no errors in netlist we need to verify the netlist generated by synthesizer. This can be done by giving netlist and testbench to a simulator which in turn produces a .vcd file , then verifying the vcd file gtkwave. The output produced by this vcd file should be same as the one generated by the RTL design code.

**Faster Cells Vs Slower Cells** :Load in digital circuit is of Capacitence. Faster the charging or dicharging of capacitance, lesser is the celll delay. However, for a quick charge/ discharge of capacitor, we need transistors capable of sourcing more current i.e, we need WIDE TRANSISTORS.

Wider transistors have lesser delay but consume more area and power. Narrow transistors are other way around. Faster cells come with a cost of area and power.

Selection of the Cells: We'll need to guide the Synthesizer to choose the flavour of cells that is optimum for implementation of logic circuit. Keeping in view of previous observations of faster vs slower cells,to avoid hold time violations, larger circuits, sluggish circuits, we offer guidance to synthesizer in the form of Constraints.
</details>

<details>
<summary>Labs on Yosys </summary>
 We were given the overview of this tool and the basic files required to perform the experiment on 2:1 MUX. 
 
 **Procedure** : First we need to read the liberty file using the code
 
 **read_liberty -lib <path of the .lib>**
 
 Then we need read the RTL Design code

 **read_verilog <RTL_Design_file>**

 After this we need to perform synthesis 

 **synth -top <instance_name>**
 
 generating netlist

 **abc -liberty <.lib path>**
 
This Netlist can be viewed in the synthesized circuit form using the **show** command    



<img width="1085" alt="ckt" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b16bd3962e6b14addfb035fca7c607c20f29a653/twoistoonemux.png">


The Nestlist code 
<img width="1085" alt="netlist" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f6284eee3d3d3865ac7099cbb31b27a44d7e8787/netlist.png">

Simplified Netlist code 
<img width="1085" alt="netlist" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f6284eee3d3d3865ac7099cbb31b27a44d7e8787/simp_netlist.png">
</details>


# Day-2-Introduction to Timing libraries, Hierarchical vs flat synthesis, and flip flop coding 

 <details>
 <summary>Introduction to timing libraries</summary>

 **Timing File** consists of ASCII representations of Timing, Area, and Power associated with the Standard cell. The Naming convention in the timing file follows PVT format (Process, Voltage, Temperature). For example, the standard library used in our case was  **sky130_fd_sc_hd_tt_025C_1v8**, this name suggests that we are using 130 nm technology and the process is typical, temperature is 25C, and 1v8 represents the voltage.

Below is the screenshot of a standard library file

<img width = "1085" alt="std_lib" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/8cc214f938b327466e90dde958d486b2d36f7b9d/day%232/lib_file.png">

The timing File also consists of the technology used for standard cells as in the above example it is **CMOS**, it also specifies the delay model, unit of time, unit of voltage, unit of resistance, and many other units. 

For each gate cell based on the number of inputs(N), there will be 2^N combinations, and for each combination leakage power, area, delay, and all related parameters are mentioned. For example, consider the below screenshot the gate mentioned in the screenshot consists of 5 inputs so there will be 2^5 i.e 32 combinations, and for all the combinations power, delay, value, and all the features are mentioned in it.

<img  width="1085" alt="std_lib" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/522961b79bd941674795678a161f1ee5465e484c/day%232/a21110.png">

The timing file consists of many different variations of the same gate cells.

Below image shows the comparison of the power consumption of different flavours of the same gate
<img  width="1085" alt="std_lib" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/power_consumption.png">

Below image shows the comparison of the delay times of different flavours of the same gate
<img  width="1085" alt="std_lib" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/delay.png">
</details>
<details>
 <summary>Hierarchical vs Flat synthesis</summary>
	
 **Hierarchical synthesis** : The basic flow of hierarchical design is simple… Dividing a design into multiple blocks (sometimes referred to as sub-chips, sub-blocks, modules, hierarchical blocks, etc.). Designers can work on the blocks separately and in parallel from RTL through physical implementation. Hierarchial design has blocks, subblocks in an hierarchy.

 Consider a multimodule combinational circuit which consists of two sub_modules one that of a **and** gate and other of a **or** gate. Below is the RTL Design code of multimodule.
 


```ruby
module sub_module2 (input a, input b, output y);
	assign y = a | b;
endmodule

module sub_module1 (input a, input b, output y);
	assign y = a&b;
endmodule


module multiple_modules (input a, input b, input c , output y);
wire net1;
sub_module1 u1(.a(a),.b(b),.y(net1));  //net1 = a&b
sub_module2 u2(.a(net1),.b(c),.y(y));  //y = net1|c ,ie y = a&b + c;
endmodule
```
The Schmetic of the multiple  model is as shown in the below figure.
<img  width="1085" alt="hand_writ_ckt" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/0c2e5b9a02719702743f4bf1683199e4fa698174/day%232/multi.jpg">

When we perform synthesis in yosys it generates the following schematic instead of the  above  schematic
<img  width="1085" alt="hier" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/hier_sch.png">

The yosys considers the module hierarchy and does mapping according to the instantiation.The netlist code for hierarchical implementation of the multiple_modules

```ruby
module multiple_modules(a, b, c, y);
	  input a;
	 input b;
	 input c;
	  wire net1;
	 output y;
  sub_module1 u1 (.a(a),.b(b),.y(net1) );
  sub_module2 u2 (.a(net1),.b(c),.y(y));
endmodule

module sub_module1(a, b, y);
 wire _0_;
 wire _1_;
 wire _2_;
 input a;
 input b;
 output y;
 sky130_fd_sc_hd__and2_0 _3_ (.A(_1_),.B(_0_),.X(_2_));
 assign _1_ = b;
 assign _0_ = a;
 assign y = _2_;
endmodule

module sub_module2(a, b, y);
wire _0_;
 wire _1_;
 wire _2_;
input a;
input b;
 output y;
 sky130_fd_sc_hd__lpflow_inputiso1p_1 _3_ (.A(_1_),.SLEEP(_0_),.X(_2_) );
 assign _1_ = b;
 assign _0_ = a;
 assign y = _2_;
endmodule
```
In the netlist we can observe that separate modules namely sub_module1 sub_module2 are getting created i.e submodules are getting instanstiated not the gate cells


**Flat synthesis** : In Flat synthesis the hierarchies the flattened  out and there is a single module in the netlist i.e the gates are instantiated directly instead of submodules. We apply flat synthesis on the same  design mentioned above. The command used to perform Flat synthesis from yosys are as follows

**read_liberty -lib <path of the .lib>**
 
 **read_verilog <RTL_Design_file>**

 **synth -top <instance_name>**

 **abc -liberty <.lib path>**
 
 **flatten**

**write_verilog -noattr <File_name>**

The synthesized circuit for a flattened netlist is shown in the below image , Here submodules u1 and u2 are flattened 
<img  width="1085" alt="hier" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/flat_sch.png">

The netlist code of the flattened synthesis is as follows
```ruby

module multiple_modules(a, b, c, y);
	 wire _0_;
	 wire _1_;
	 wire _2_;
	 wire _3_;
	 wire _4_;
	 wire _5_;
	 input a;
	 input b;
	 input c;
	 wire net1;
	 wire \u1.a ;
	 wire \u1.b ;
	 wire \u1.y ;
	 wire \u2.a ;
	 wire \u2.b ;
	 wire \u2.y ;
	output y;
	 sky130_fd_sc_hd__and2_0 _6_ (
	  .A(_1_),
	 .B(_0_),
	 .X(_2_)
	);
	 sky130_fd_sc_hd__lpflow_inputiso1p_1 _7_ (
	  .A(_4_),
	  .SLEEP(_3_),
	  .X(_5_)
	 );
	 assign _4_ = \u2.b ;
	 assign _3_ = \u2.a ;
	 assign \u2.y  = _5_;
	 assign \u2.a  = net1;
	 assign \u2.b  = c;
	 assign y = \u2.y ;
	 assign _1_ = \u1.b ;
	 assign _0_ = \u1.a ;
	 assign \u1.y  = _2_;
	 assign \u1.a  = a;
	 assign \u1.b  = b;
	 assign net1 = \u1.y ;
	endmodule
```
We can see that there is a single module which consist of the gate level instantion of the two submodules .


Performing Synthesis at sub_module level is one of the good practises for the massive designs as it simplifies the debugging process . It is also helpful in cases where there many instances of the same module , Instead of synthesizing all the instances we can synthesize one and duplicate it for others and stitch them together. Here is the synthesized circuit and netlist image of the sub_module1 

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/sub_module1_sch.png">
<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/sub_module1_net.png">
</details>

<details>
 <summary>Flop coding</summary>

 **Flop**: They are digital electronic circuits that are used to store information in bits as they have two stable states.Even though the input is not stable it gives stable output.
 
 **Why Flop**
 
 In a combinational circuit, the output changes after the propagation delay of the circuit once inputs are changed. During the propagation of data, if there are different paths with different propagation delays, there might be a chance of getting a *glitch* at the output. *glitch* is a signal value pulse that occurs when a logic level changes two or more times over a short period.

If there are multiple combinational circuits in the design, the occurances of glitches are more thereby making the output unstable.
To curb this drawback, we are going for flops to store the data from the cominational circuits. When a flop is used, the output of combinational circuit is stored in it and it is propagated only at the posedge or negedge of the clock so that the next combinational circuit gets a glitch free input thereby stabilising the output.

We use initialize signals or control pins called set and reset on a flop to initialize the flop, other wise a garbage value to sent out to the next combinational circuit.

**Asynchronous Reset D Flop**

Here the output signal goes low when the reset signal is high , it does not wait for the clock's edge(positive or negative edge ).i.e irrespective of the clock output changes

RTL Design code of positive edge trigerred asynchronous reset D Flop
```ruby
 module dff_asyncres ( input clk ,  input async_reset , input d , output reg q );
	always @ (posedge clk , posedge async_reset)
	begin
		if(async_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
endmodule
```
Simulation

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/asyncres_wave.png">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/asyncres_sch.png">

**Asynchronous set D Flop**

Here the output signal goes high when the reset signal is high , it does not wait for the clock's edge(positive or negative edge ).i.e irrespective of the clock, output changes

RTL Design code of positive edge trigerred asynchronous set D Flop
```ruby
module dff_async_set ( input clk ,  input async_set , input d , output reg q );
	always @ (posedge clk , posedge async_set)
	begin
		if(async_set)
			q <= 1'b1;
		else
			q <= d;
	end
endmodule
```
Simulation 

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/asyncset.png">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/asyncset_sch.png">

**synchronous reset D Flop**

Here the output signal goes low whenever the reset signal is high and at the clock edge(positive or negative)

RTL Design code of positive edge trigerred synchronous reset D Flop
```ruby
module dff_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
	always @ (posedge clk )
	begin
		if (sync_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
endmodule

```
Simulation

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/syncres_wave.png">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d014884bf2fa07de0fa6c458307678c51a5b9f25/day%232/syncres_sch.png">

 </details>

 <details>
<summary>Optimisation Techniques</summary>

There many special cases where we don't need any additional hardwares to implement the circuit. For Example consider a case where 3 bit number is multiplied by 2 in this case we dont need any additional hardware and only needs connecting bits to the output and grounding the LSB bit,same is realized by yosys.
```ruby
module mul2 (input [2:0] a, output [3:0] y);
	assign y = a * 2;
endmodule
```
When it comes to multiplying with the powers of 2 it justs need shifting as shown in the below image

<img  width="1085" alt="hand_writ" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/0c2e5b9a02719702743f4bf1683199e4fa698174/day%232/mul2.jpg">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/dcb471494ed4f1dc57ccdb1b59f552acd27d8168/day%232/mul2_sch.png">

Netlist 

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/dcb471494ed4f1dc57ccdb1b59f552acd27d8168/day%232/mul2_net.png">

The next special was multiplying a 3 bit number by 9 , the result is as shown in the below image

<img  width="1085" alt="hand_writ" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/0c2e5b9a02719702743f4bf1683199e4fa698174/day%232/mul8.jpg">

The  RTL  Design code

```ruby
module mul8 (input [2:0] a, output [5:0] y);
	assign y = a * 9;
endmodule
```

The synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/dcb471494ed4f1dc57ccdb1b59f552acd27d8168/day%232/mul8_sch.png">

Netlist 

<img  width="1085" alt="sub_module1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/dcb471494ed4f1dc57ccdb1b59f552acd27d8168/day%232/mul8_net.png">
  
 </details>

 # Day-3-Combinational and sequential logic optimizations 

 <details>
 <summary>Combinational Logic Optimization with examples</summary>

 **Combinational Logic Optimization** squeeze the logic to get most optimized design in terms of area and power. There are various techniques for optimizing the circuit
 
 - constant propagation(Direct propagation)
 - Boolean Logic Optimization(K-Means ,QUine Mckluskey)
   
**Constant Propogation** is an optimization technique used by  synthesis tools to minimize hardware implementation.Constant propagation prevents situations in which values are copied from one place or variable to another only to assign their value to a different variable.

**Example on Constant Propogation** 
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/9ee556e759953cfdd337c4c07302f7f415aab031/hand0.jpg">

Consider the above  combinational circuit it consists of and and nor gate, so it requires 6 CMOS transistor to implement , if A is made constant value 0 then A&B will give 0 then 0 and C are given to NOR gate which reduces the expression to C compliment(C`) i.e basically a inverter . By making an input constant we can reduce this combinational circuit to an inverter which can impleneted using only 2 CMOS transistor thus reducing the hardware implementation

**Example for Boolean Logic optimization**
consider a concurrent statement a?(b?c:(c?a:0)):(!c) , this statement is realized using multiple multiplexers. Simplying this equation using boolean reduction techniques we get the output as ~(a^b)

The command to optimize the circuit in yosys is **opt_clean -purge**.

**Example - 1**

RTL Design Code
 ```ruby
module opt_check (input a , input b , output y);
	assign y = a?b:0;
endmodule
```
Synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/opt_check.png">
 
**Example-2**
RTL Design Code
 ```ruby
module opt_check (input a , input b , output y);
	assign y = a?1:b;
endmodule
```
Synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/opt_check2.png"> 

**Example-3**
RTL Design Code
 ```ruby
module opt_check3 (input a , input b, input c , output y);
	assign y = a?(c?b:0):0;
endmodule

```
Synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/opt_check3.png"> 

**Example-4**
RTL Design Code
 ```ruby
module opt_check4 (input a , input b , input c , output y);
	assign y = a?(b?(a & c ):c):(!c);
endmodule


```
Synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/opt_check4.png"> 

**Example 5**
There is a multi-module  on this we need to try and optimize it 
The commands used for this are :

**read_liberty -lib <library_path>**

**read_verilog <verilog_file>**

**synth -top <module_name>**

**opt_clean -purge**

**abc -liberty <library_path>**

**flatten**



**Example 5**
RTL Design code
```ruby
module sub_module(input a , input b , output y);
	assign y = a & b;
endmodule

module multiple_module_opt2(input a , input b , input c , input d , output y);
	wire n1,n2,n3;
	sub_module U1 (.a(a) , .b(1'b0) , .y(n1));
	sub_module U2 (.a(b), .b(c) , .y(n2));
	sub_module U3 (.a(n2), .b(d) , .y(n3));
	sub_module U4 (.a(n3), .b(n1) , .y(y));
endmodule
```
Before flatten
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/multi_opt2_wf.png"> 

After flatten
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/multi_opt2_fl.png">

**Example 6**
RTL Design code
```ruby
	module sub_module1(input a , input b , output y);
	 assign y = a & b;
	endmodule

	module sub_module2(input a , input b , output y);
	 assign y = a^b;
	endmodule

	module multiple_module_opt(input a , input b , input c , input d , output y);
	wire n1,n2,n3;
	sub_module1 U1 (.a(a) , .b(1'b1) , .y(n1));
	sub_module2 U2 (.a(n1), .b(1'b0) , .y(n2));
	sub_module2 U3 (.a(b), .b(d) , .y(n3));

	assign y = c | (b & n1); 
	endmodule

```
Before flatten
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/multi_opt_wf.png"> 

After flatten
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/multi_opt_fl.png">

</details>

<details>
 <summary>Sequential Logic optimization</summary>

 There are various techniques for Sequential Logic Optimization
 
 - Sequentialal constant propagation
 
 - Advanced 
 	- State Optimization
  
  	- Retiming
   
   	- Sequential Logic cloning

**Sequential Constant Propogation**

Consider a case where asynchronous reset D Flip-flop is fed with d = 0(i.e GND) always so the output will always be 0 irrespective of the timing or circuit.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/9ee556e759953cfdd337c4c07302f7f415aab031/hand1.jpg">

*Advanced*

**State Optimisation**: This is optimisation of unused state. Using this technique we can come up with most optimised state machine.

**Cloning** : It is an optimization technique that duplicates a cell to reduce the load on heavily loaded cell. This technique is usually preffered while performing *PHYSICAL AWARE SYNTHESIS*. Lets consider a flop A which is connected to flop B and flop C through a combination logic. If B and C are placed far from A in the flooerplan, there is a routing path delay. To avoid this, we connect A to two intermediate flops and then from these flops the output is sent to B and C thereby decreasing the delay. This process is called cloning since we are generating two new flops with same functionality as A.

**Retiming** : Sequential circuits can be optimised by retiming. The combinational section of the circuitry is unaffected as it only rearranges the registers in the circuit.
It is a powerful sequential optimization technique used to move registers across the combinational logic or to optimize the number of registers to improve performance via power-delay trade-off, without changing the input-output behavior of the circuit.

**Example 1**
Here flop is inferred in output 
```ruby
module dff_const1(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b0;
		else
			q <= 1'b1;
	end
endmodule
```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const1_wave.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const1_sch.png">

**Example 2**
Here flop is not inferred in output 
```ruby
module dff_const2(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b1;
		else
			q <= 1'b1;
	end
endmodule

```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const2_wave.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const2_sch.png">

**Example 3**
 
```ruby
module dff_const3(input clk, input reset, output reg q);
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b0;
		end
		else
		begin
			q1 <= 1'b1;
			q <= q1;
		end
	end
	endmodule


```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const3_wave.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const3_sch.png">

**Example 4**

```ruby
	module dff_const4(input clk, input reset, output reg q);
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b1;
		end
	else
		begin
			q1 <= 1'b1;
			q <= q1;
		end
	end
	endmodule

```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const4_wave.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const4_sch.png">

**Example 5**

```ruby
	module dff_const5(input clk, input reset, output reg q);
	reg q1;
	always @(posedge clk, posedge reset)
		begin
			if(reset)
			begin
				q <= 1'b0;
				q1 <= 1'b0;
			end
		else
			begin
				q1 <= 1'b1;
				q <= q1;
			end
		end
	endmodule
```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const5_wave.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a6ae4306290a90ac5e5ffb9a8501a53525be304e/day3/dff_const5_sch.png">

</details>

<details>
	
 <summary>Sequential optimization of unused outputs</summary>

 **Example 1**
 ```ruby
	module counter_opt (input clk , input reset , output q);
	reg [2:0] count;
	assign q = count[0];
	always @(posedge clk ,posedge reset)
	begin
		if(reset)
			count <= 3'b000;
		else
			count <= count + 1;
	end
	endmodule
```
synthesis

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f1aea11b3381a7ad84d4fb6b5e5f216c3796ddc1/day3/counter_opt_rep.png">


<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f1aea11b3381a7ad84d4fb6b5e5f216c3796ddc1/day3/counter_opt_sch.png">

This is a 3 bit counter with output only LSB so instead of 3 d-flip flop only 1 is used

**Updated Counter**
```ruby
module counter_opt (input clk , input reset , output q);
	reg [2:0] count;
	assign q = {count[2:0]==3'b100};
	always @(posedge clk ,posedge reset)
	begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
	end
endmodule
```
synthesis

All the other blocks are for incrementing the counter but the output is from 3 input NOR gate

```ruby
module counter_opt (input clk , input reset , output q);
	reg [2:0] count;
	assign q = {count[2:0]==3'b100};
	always @(posedge clk ,posedge reset)
	begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
	end
endmodule
```
synthesis

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f1aea11b3381a7ad84d4fb6b5e5f216c3796ddc1/day3/updated_counter_rep.png">


<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f1aea11b3381a7ad84d4fb6b5e5f216c3796ddc1/day3/updated_counter_sch.png">

</details>

# Day 4 Gate level simulation(GLS), Blocking Vs Non Blocking and Synthesis Simulation mismatch

 <details>
 <summary>Gate level synthesis,blocking vs non blocking , Synthesis simulation mismatch</summary>

 **Gate level Synthesis** 
 Gate-level simulation is a fundamental component of VLSI design verification. This simulation technique involves creating models for the behavior of digital circuits at the gate level, representing individual logic gates and flip-flops. Through gate-level simulations, designers can gain insight into how the circuit will respond to various inputs and clock signals. By simulating signal propagation through gates, it becomes possible to validate the accuracy of logic functionality, pinpoint timing discrepancies, and detect potential issues like glitches or hazards.GLS generates the simulation output by running test bench with the netlist generated from the synthesis of design.

**Why GLS** 

- To verify logic correctness of design after synthesis

- If GLS is run with delay annotion then it can be used for timing analysis 

- To identify errors that might occur due to signal progation delay.

- As Design become more and more complex it becomes difficult to predict their behaviour accurately,GLS offers a comprehensive and a detailed view of circuit operation

**Synthesis Simulation Mismatch** 

Synthesis simulation mismatch denotes the disparities between the anticipated behavior of a circuit as simulated during design and its real-world performance after fabrication. This discrepancy is attributed to factors such as process variations, parasitic effects, and inaccuracies in simulation models. It's a critical concern to guarantee the functional alignment of the manufactured circuit with its intended design.

Synthesis simulation mismatched are mainly caused because of the following reasons 

- Missing sensitivity list
- Blocking vs Non Blocking assignments
- Non standard verilog code

**Missing sensitivity list**
The absence of a complete sensitivity list in VLSI design can give rise to problems. In hardware description languages (HDL) like Verilog, a sensitivity list is utilized to specify the inputs that should activate the execution of a specific process or code block. Inadequate or missing signals in the sensitivity list can lead to inaccurate or unforeseen behavior of the circuit during synthesis or simulation. Ensuring an accurate representation of inputs impacting the logic within a process is vital.

As the synthesizer does not look for sensitivity list and it looks only statements in the procedural block , it infers correct circuit and if we simulate the netlist code , there will be synthesis simulation mismatch. In to order tackle this issue this issue it is important to check the behaviour of the circuit first and then match it with the expected output seen in the simulation. 

**Blocking Vs Non Blocking Assignments**

*Blocking statements* are the type of assignment statements in Hardware Description Language. These assignments are executed sequentially in the order they appear in the code. The next statement will wait for the current one to finish.

Example of blocking assignment 
```ruby
always @posedge(clk) begin
	a = b;
	d = c;
end
```
Improper use of blocking assignments in the always block can lead to synthesis simulation mismatch 

*Non Blocking statements* are also a type of assgnment statements in HDL. These assignments are executed parallely, and the updates to the values  take effect at the end of the time step.

Example of non blocking assignment

```ruby
always @posedge(clk) begin
	a <= b;
	d <= c;
end
```
Inside always block it is always a good practise to use non blocking assignment statements
</details>

<details>

 <summary>Labs on GLS (Simulation synthesis mismatch)</summary>
 
 **Example 1** 
 
 In this example there is no mismatch between the RTL Design simulated wave and Netlist simulated wave.
 ```ruby
module ternary_operator_mux (input i0 , input i1 , input sel , output y);
	assign y = sel?i1:i0;
endmodule
```
simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/ter_rtl_wave.png">

Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/ter_sch.png">

Netlist Simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/ter_gls_wave.png">

In this we see that when select line is 0 , Output follows i0 and when select line is 1 output follows i1. This is same for both the simulations so there is no mismatch.

**Example 2**
Consider a example of mux.In this always block is triggered only when the select line is changed.
```ruby
module bad_mux (input i0 , input i1 , input sel , output reg y);
	always @ (sel)
	begin
		if(sel)
			y <= i1;
		else 
			y <= i0;
	end
endmodule
```
Simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/bad_rtl_wave.png">

Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/bad_sch.png">

Netlist Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/bad_gls.png">

In this we can see that there is simulation synthesis mismatch , in the RTL design simulation we see that output is changing only when select line is changing but thats not the correct functionality of a mux , the output should change when either the input or select line is changed , this is reflected in the netlist simulation.

**Example 3**
Consider a example of mux.In this the always block is triggered when there is a change in either input or select line. 
```ruby
module good_mux (input i0 , input i1 , input sel , output reg y);
	always @ (*)
	begin
		if(sel)
			y <= i1;
		else 
			y <= i0;
	end
endmodule
```
Simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/good_rtl.png">

Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/good_sch.png">

Netlist 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/good_gls.png">

Here simulation output are same , i.e output changes when input or select line changes.

</details>

<details>

 <summary>Labs on synthesis simulation mismatch (Blocking statement)</summary>
 
 **Example 4** 
 Here the output depends on the past value of x which is dependent on a and b  and it appears like a imaginary flop.
 
 ```ruby
 module blocking_caveat (input a , input b , input  c, output reg d); 
reg x;
always @ (*)
	begin
	d = x & c;
	x = a | b;
end
endmodule
```

 Simulation
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/blk_rtl.png">

 Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/blk_sch.png"> 

Netlist simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/blk_gls.png"> 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/2ea9ca60553c829f9162484cb1e4049c3064443c/day4/20230829_085956.jpg"> 

This a combinational circuit of or and and gate , in which the output of or gate is given as input to the and gate as shown in the figure , but in the RTL Design code blocking statements are used to define these operations in reverse direction(These statements are executed sequentially) so the and gate is getting input from the  previous output of or gate which acts as imaginary flop. As a result we are getting a different waveform in RTL design simulation , the correct waveform is  obtained  while doing netlist simulation. This causes Synthesis Simulation mismatch. This can be overcome by using non blocking assignment statements in the always block.  
</details>

# Day 5 Design For Testabilty(DFT)

 <details>
 <summary>DFT</summary>
	 
 - **Testabilty** is a relative measure of the effort or cost of testing a logic. A design is said testable if it is well *Controllable* and well *observable*.
     
 - **DFT(Design for testability)** refers to a set of design techniques used to ensure that Integrated circuits can be effectively tested after being fabricated. It aims at incorporating an additional hardware in the design to improve the reliabilty of semiconductor devices .

 - **Why DFT**
   - to make testing processs easier
   - to improve manufacturing quality
   - Reduce time to market as DFT helps in faster debugging and validationof design
   - It ensures long term reliability of the design
  
 - There are 3 main levels of testing after chips are fabricated
    - **Chip level**
    - **Board level**
    - **System level**

 - **Pros and cons**
    - *Pros*
       - Improved test coverage
       - Reduces tester complexity
       - Easy to debug
    - *Cons*
       - Increases complexity of design
       - increases area ,power ,timing and package pins
       - Dependency on external tools for performing DFT methods such as scan based testing  
       
 - **Terminologies in DFT**
    - *Controllability* :  It specifies the difficulty of setting a signal line to a required logic level from primary inputs. We intend  to propagate 0 or 1 depending on the input to each and every node within the target pattern.
    - *Observability* : It specifies the  difficulty of propagating the logic value of the signal line to primary output. It is the ability to measure the state of logic signal.
    -  *Fault* : It is the reperesentation of  defect /physical damage  at the abstracted function level which may/mayn't cause system failure.
    -  *Error* : This is caused by fault, which leads to the malfunction of the system.
    -  *Failure* : This is when the system is not yielding the expected output.
    -  *Fault Coverage* : It is the percentage of the logical faults that can be detected during the test.
             Fault coverage  = (Faults detected)/(Number of Potential faults)

 - **DFT Technique**
    - It refers to the various strategies and methodologies incorporated into design process to make testing and verification more efficient and effective.They are mainly characterized in 2 main techniques:
       - Ad-Hoc : This is a  DFT technique which is applied on a case by case basis to address specific challenges or issues.It includes
          - Custom Logic Design
          - Layout modification
          - Specialized Clocking schemes
          - Custom Testing methods
          - Design Rule Exceptions
          - Power Optimization Techniques
          - Mixed signal customization
        
		- Ad-hoc technique/steps :          

     		1. Avoid Combinational feedback
   
     		2. All flops must be intializable
              
     		3. Partioning a large circuit into small blocks
              
     		4. Provide test control for signals which are not controllable
       
     		5. While designing test logic we have to consider the ATE requirements 


 	- **Structured technique**

  		- Structured Design for Testability (DFT)  refers to the systematic application of design techniques that enhance the testability of integrated circuits (ICs). The goal of structured DFT is to make it easier and more efficient to test and diagnose defects in the manufactured ICs. Here are some key aspects of structured DFT in VLSI design scan chains, boundary sacn , MBist.
  


- **Scan chain Technique** : It is one of the One of the fundamental DFT techniques. A serial path for shifting in test patterns and capturing test results is built by including scan flip-flops in the architecture. This allows for comprehensive testing of the logic paths within the design. Structured DFT emphasizes proper insertion of scan chains and their management to maximize fault coverage. It is used to *shift in shift out* test data.Scan chains are formed by connecting flip-flops in a serial manner, often using multiplexers to enable the shift-in and shift-out operations. These chains provide easy access to the internal nodes of the design for testing. There are 3 types of scan flip flops namely multiplexed, clocked,lssd. The *Chain length*  means the number of flops in a single scan chain.Larger the chain length longer the time it take to shift in and shift out.

  No of ports required = 2 X Number of scan chain

  No of cycles to run pattern = 2 X longest scan chain in the design
  
-  **Purpose of Scan Chains** :

	-  Scan chains are used to detect manufacturing defects present in the combinational logic of the design.

 	-  To check whether each path of the manufactured devices is working at functional frequency

- **Basic ATE functionality**
	
   - Scan in phase
     
   - Parallel Measure
     
   - Parallel Capture
     
   - First scan out phase
     
   - Scan out phase

</details>

# Day 6 Introduction to logic synthesis

 <details>
 <summary>Introduction</summary>
	 
 <ins> **Digital Circuit** </ins>
 
 A Digital circuit is a fundamental component of modern electronic devices. It is designed to process and manipulate binary data which consists of ones and zeros , commonly known as "bits".Digital circuits are integral to a wide range of applications from simple logic gates to complex microprocessors.These descriptions have been articulated within the behavioural model of a design implementated in HDL and VHDL.These specification conveyed through a programming language constitutes the RTL representation.

 Here are sopme important points on digital circuits:

  - Binary Logic
  - Basic Components
  - Boolean Algebra
  - Clock Signals
  - Sequential Logic Gate
  - Combinational Logic Gate


<ins> **Synthesis** </ins>

Synthesis in VLSI is the process of converting your code (HDL or VHDL program) into a circuit. In terms of logic gates, synthesis is the process of translating an abstract design into a properly implemented chip. It is a process of converting a RTL code into a gate level netlist. The tool used for this purpose is called synthesizer.Some of the key concepts of Synthesis are :

**High-Level to Low-Level Transformation**: VLSI synthesis bridges the gap between the high-level hardware description, often in a Hardware Description Language (HDL) like VHDL or Verilog, and the low-level gate-level representation. It transforms an abstract design into a netlist consisting of logic gates, flip-flops, and interconnections.

**Optimization**: Synthesis tools aim to optimize the design for various factors, including area, power consumption, and performance. They strive to find the most efficient way to implement the given functionality within the constraints.

**Technology Mapping** : During synthesis, the design is mapped to a specific semiconductor technology library. This involves selecting appropriate gates and components from the library that best fit the design's requirements.

**Clock Domain Management** : Managing clock domains and ensuring proper synchronization is crucial. Synthesis tools handle clock gating, clock tree synthesis, and other techniques to ensure the design functions correctly under various clocking scenarios.

**Timing Analysis** : Timing analysis is a critical part of VLSI synthesis. It ensures that signals meet the required setup and hold times, and that the design operates at the desired clock frequency.

**Area and Power Optimization** : Achieving a balance between silicon area and power consumption is a constant challenge. Synthesis tools employ techniques like logic optimization, resource sharing, and power gating to address these concerns.

**Sequential and Combinational Logic** : VLSI synthesis differentiates between sequential logic (e.g., flip-flops) and combinational logic (e.g., logic gates) and optimizes them separately to ensure proper functionality.

**Verification**: The synthesized design undergoes rigorous verification to confirm that it behaves as intended. This includes simulation, formal verification, and other testing methods.

**Iterative Process** : VLSI synthesis is often an iterative process. Designers make adjustments to the high-level description based on the synthesis results, seeking a balance between design goals and constraints.

**Final Design Handoff** : Once synthesis is complete, the final netlist is handed off for physical design, which includes placement and routing, leading to the creation of masks for chip fabrication.

In conclusion, Synthesis is a pivotal step in the development of integrated circuits. It transforms abstract hardware descriptions into physical layouts, optimizing for factors like area, power, and performance. This process is essential for the creation of the complex and advanced semiconductor chips that power modern electronic devices.

<ins> **.lib file** </ins>

It is a collection of logical modules of different flavours of basic logic gates.It describes the timing and power characteristics of standard cells and other componenets used in IC Designs. It serves a comprehensive library that provides essential information to electronic design automation.

 *Contents of .lib*  

A typical Liberty file contains detailed information about the behaviour of standard cells, including

- **Timing Information** : This includes delay, transition and capacitance values associated with the standard cells. Timing information specifies how the cells behave under different input conditions.
- **Power Information** : Liberty file also provides data on power consumption , including static power and dynamic power characteristics. This information is crucial for optimizing the power consumption in IC.
- **Functional Behaviour** : Descriptions of the logical functionality of standard cells, such as input and output pins and logical equations and any additional attributesthat define their operation.
- **Operating Conditions** : Liberty files may include information about different operating condition in terms of process , voltage and temperature under which all cells are characterized.

Liberty files are essential for following reasons:

- **Timing Analysis** : EDA tools use Liberty files to perform static timing analysis, ensuring that the IC design meets specified timing constraints. This is critical for achieving desired performance targets.

- **Power Optimization** : Power consumption is a significant concern in modern IC design. Liberty files provide power data that allows designers to optimize power usage and meet energy efficiency goals.

- **Design Closure** : During the design process, designers use Liberty files to guide the synthesis, placement, and routing of standard cells. The data in these files helps achieve design closure by ensuring that the design meets performance, power, and area targets.

- **Variability Handling** : Variability in manufacturing processes can impact the behavior of standard cells. Liberty files may include data for different process corners to account for manufacturing variations.

<ins> **Constraints** </ins>

In VLSI design, constraints are essential parameters and limitations that guide the development process to ensure that the resulting integrated circuits (ICs) meet specific performance, timing, and functionality requirements. These constraints play a crucial role in achieving a successful VLSI design.


</details>

<details>

 <summary>DC Compiler</summary>

 **Design Compiler** , often abbreviated as DC, is a high-level synthesis tool developed by Synopsys, a leading provider of EDA solutions. It plays a pivotal role in the process of designing complex integrated circuits (ICs) and is an integral part of modern VLSI design flows.

 Important terms used 
 - **Synopsys Design Constraints(SDC)** : These are the design constraints which are supplied to DC to enable appropriate optimization suitable for achieving the best implementation.
- **.lib** : Design Library which contains the Standard cells.
- **.db** : Same as .lib but in a different format. DC understands libraries in .db format
- **.ddc** : Synopsys propreitary format for storing the design information. DC can write out and read in DDC.
- **Design** : RTL files which has the behavioral model of the design.

<ins> **DC synthesis flow** </ins>

```ruby
		Read STD Cell/tech.lib
			 ↓
		Read Design (Verilog and Design.lib)
			 ↓
		Read SDC
			 ↓
		Link the Design
			 ↓
		Synthesize
			 ↓
		Generate Report and analyse QoR
			 ↓
		Write out the Netlist
  ```
The DC compiler does not understand .lib , so the .lib is converted to .db format. lib format is for user reference.

<ins>**Labs on DC Compiler**</ins>

**Invoking DC compiler**
First we need to enable C shell and then invoke dC shell with the commands shown below

```ruby
>> csh
>> dc_shell
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/de0c4050082b98433594827daa8c1abae0c0e903/snaps/dc_invoke">



Then we echo target library and link_library which returns an imaginary pointer library namely your library, which needs to be set.
```ruby
>>>echo $target_library
>>>echo $link_library
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab3_ss2">


Consider a example of a Mux connected to D Flip flop as ahown in the figure as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/fdfd19c7e44993377e55fc70529f7e025e4f73db/day6/20230904_212145.jpg">

The RTL design code is 
```ruby
module lab1_flop_with_en ( input res , input clk , input d , input en , output reg q);
always @ (posedge clk , posedge res)
begin
	if(res)
		q <= 1'b0;
	else if(en)
		q <= d;	
end
endmodule
```
Synthesis of this design code can be done using the following commands
```ruby
read_verilog <path of design file>
read_db <path of .db>
write -f verilog -out <net_filename>
```
Below is the screenshot of the output window after compile
This generates the netlist file but it consists of some seqgen library as shown in the figure and not the .db file even though we have read the .db file, This is beacuse we didn't set link and target library,

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab1_dc_wisky_seqgen">

To set the link_library and target_library we use the following commands
```ruby
set target_library <path of .db>
set link_library { * path of the .db }
link
compile
write -f verilog -out <net_filename>
```
After compiling the we get the output as shown in the figure

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab1_link_compile">

The generated netlist

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab1_net_with_sky">


**Labs on Design Vision**

Design Vision is a widely used Electronic Design Automation (EDA) tool in the field of VLSI. It is developed by Synopsys and is primarily used for logic synthesis, formal verification, and other essential tasks in the VLSI design flow.

To launch Design Vision we need to enable c shell and then give design Vision
```ruby
csh
design_vision
```
After launching the design_vison first we need to the net to .ddc which is read by Design_vision tool which can be done by using the below command
```ruby
 write -f ddc -out <filename_name>
```
Then we can start GUI and then read the .ddc file generated above. This ddc file contains all the information of the tool memory of that particular session. ddc is synopys proprietary format i.e it can be read only br synopsys tools.When the .db is read it automatically reads the linked .db file as shown in the below figure. 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab2_dv1">

When we click lab1 and then schematic we get the schematic view of the Design

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab2_dv2">

If we want to see the gate level implementation then we need to double click the module.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab2_dv3">

**Lab on .synopsys_dc.setup**

Consider a case where there are multiple .db files used and we cannot skip any of them , then it is nearly impossible to indvidually set all the .db files. In order to resolve this we can create a file namely *.synopsys_dc.setup* file in home diresctory of workspace.

When dc_shell is invoked, the shell looks the .synopsys_dc.setup file in user_home_directory. The order of priority is, if file exists in user_home_directory then that will be picked and the installed (default) is ignored. If not found, then installed one is picked. All repetitive tasks which are needed for tool setup can be pointed in this file. So when the dc_shell is invoked all the .dbs are set automatically

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab3_ss1">

The .synopys_dc.setup file for the above example of mux and d flip flop is as follows

```ruby
set target_library /home/a.chinchani/DC_WORKSHOP/lib/sky130_fd_sc_hd_tt_025c_1v80.db
set link_library {* $target_library }
```

</details>

<details>

 <summary>Tcl scripting</summary>
 Tcl, short for "Tool Command Language," is a dynamic and interpreted scripting language that was created to serve as a simple and efficient scripting tool. Tcl is known for its ease of use, flexibility, and extensibility, making it widely adopted in various domains.
 
 This is widely used language in VLSI

 Basic Tcl Commands

 Assigning a variable
 ```ruby
set a 10
ser b 10
set a [expr $a + $b]
```

if else condition

```ruby
if { condition } {
<statements>
} else {
<statements>
}
```
while loop

```ruby
while {<condition>} {
/statements
}
```
For loop

```ruby
for {<looping variable>} {condition} {incr/decr} {
/statements
}

```
For each 

```ruby
foreach var list{
statement
}
```

For each in the case of collection

```ruby
foreach_in_collection var collection {
statement
}
```

Labs on TCL

Example 1 on assigning the variable and for loop

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab4_1">

Example 2 on while loop

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab4_2">

Example 3 is tool specific it returns the collection of all the standard cells containing and in the .lib file, it is done using

```ruby
get_lib_cells */*and*
```

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab4_3">

when we try to print this collection we get _sel3 which is basically a pointer address. Collection is basically the collection of pointers

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab4_4">

To get the cell name we need to use the command as used in the below screenshot

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab4_5">

These codes can be written in tickle file

Consider a example 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab4_8">


output

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67124783772161a8b5a7f1768299ad0895244d93/snaps/lab4_7">



</details>


# Day 7 Basics of STA

 <details>
	 
 <summary>Introduction to STA(Static Timing Analysis)</summary>

 **Static Timing Analysis** 
Static Timing Analysis (STA) is a crucial step in the design and verification of digital integrated circuits, ensuring that they meet timing requirements and operate reliably.

STA is used to assess the timing performance of digital circuits without the need for actual simulation. It ensures that signals propagate through a circuit within specified time constraints, guaranteeing proper functionality and meeting performance targets.
 
**Delay** 

Delay refers to the time it takes for a signal to propagate from one point in a digital circuit to another. Delay is a critical parameter in design because it affects the performance, power consumption, and reliability of the integrated circuit.

 A *Max Delay Constraint* refers to a design specification or requirement that imposes an upper limit on the delay a signal can experience while propagating through a specific path or circuit within an integrated circuit. Consider a example of 2 D flip flop connected with a combinational logic in between them.
 
 Tck >= Tcq + Tcomb + Tst

 "Min Delay constraint" refers to a design specification or requirement that sets a minimum allowable delay for a signal to propagate through a specific path or circuit within an integrated circuit. This constraint is used to ensure that certain signals within the circuit do not propagate too quickly, which can lead to timing violations and potential operational issues.
 
Thold < Tcq + Tcomb

 Delay can well understood with the water bucket analogy , consider a case in which 2 buckets of 5 gallon each are being filled using the inflow of water from 2 separate pipes whose inflows are 1 gallon per minute and 5 gallon per minute respectively. The time taken by the bucket 1 to fill from 20 % to 80% is 3 min and for the other one it is 0.6 min. This case can be corelatted in VLSI as follows.

 Inflow water => Inflow of current
 
 Pipe 1 with higher inflow => less trasnsition delay
 
 Pipe 2 with lower inflow  => high transition delay

The size of the bucket also matters , which can be correlated with the load capacitance.

Delay of the cell is a function of **input transition** and **load capacitance**

**Timing Arc**

Timing arcs in VLSI (Very Large Scale Integration) design are critical components of the timing analysis process. They define the relationship between the input and output transitions of a specific logic element, such as a flip-flop or a gate, and the resulting delay through that element. Timing arcs capture the intricate behavior of digital components, taking into account factors like rising and falling edges, setup and hold times, and the propagation delay. 

*Combinational Cells Timing arcs* : It captures the delay information from every input pin to every output pin which it can control
 
 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/0b1ef5a8-cf65-47f4-9f44-6d032ab26447)

 Consider a case of 2:1 Mux this has 3 timing arcs
 
 A -> Z

 B -> Z

 sel -> Z

 this implies that Z ooutput can change from either A,B or sel

 **Sequential Cells Timing arcs* 

 For D flip flop it is Clock to Q delay timing arc and setup , hold time arcs. 

 For Latches it is clock to Q delay timing arc , D to Q timing arcs ,setup hold time arcs


**Constraints** 

In VLSI (Very Large Scale Integration) design, **constraints** are specifications and limitations applied to various aspects of the design process to ensure that the resulting integrated circuit meets its intended requirements and performs as expected. These constraints play a crucial role in guiding the design and verification of VLSI circuits.

Why constraints ?

Consider a circuit as shown in the figure

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/1e441935-b3ec-466a-aef1-94eff67280f8)


Here if the setup time for all the components is 0.5 ns and and propagation delay of the selected gates are 0.5 ns and 0.7 ns for not and and gate respectively.

Tck for path from 1st flop is 2.2 ns 

Tck for path from 2nd clk is 1.7 ns

The max delay is 2.2 ns which is called the critical path as it detemines the clock frequeny

In practical cases we set the working frequency and then calculate the required propogation delay. In this example if the Tck path from the 1st flop setup time and clock to q delay is almost fixed 0.5 ns if we need to make this work at clock frequency of 200 MHz i.e 2 ns which implies the and gate propogation delay should be 1 ns . so who will tell the tool to pick the and gate with proper propagtion delay of 1 ns instead of 1.2 ns . So for this we need constraints

**Timing paths** in VLSI  design are specific routes or signal paths within a digital circuit where the timing characteristics, including signal propagation delays, setup times, hold times, and clock-to-q delays, are analyzed to ensure the circuit's correct and reliable operation. These paths are crucial for timing analysis and play a central role in achieving the desired performance and functionality of the integrated circuit. Timing paths typically include a starting point (often a flip-flop or input pin), a set of logic gates and interconnections, and an ending point (another flip-flop or output pin). 

Start points of timing path

- Input ports
- Clock pins of regs

End point of timing path

- Output ports
- D pin of D flip flop / D Latch


Always the timing path start at one of the start point and ends at one of the end point

Clock -> D (Reg 2 Reg)

Clock  -> Output port (I/O timing path)

input port -> D (I/O timing path)

input port -> Output port (These should not be present)


Consider the circuit 

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/416bcaf4-bf15-416e-94a1-14216b4d27c4)


- In this Reg 2 Reg is constrained by clock
  
- Reg to out is constrained by Output external delay , load and clock . 

- In 2 Reg is constrained by input external delay ,clock, input transition.

In addition to this Input transition delays are also constrained as signal transition are not ideal . As we know that delays are function of input transition and load capacitance they both need to be constrained.


</details>

<details>

<summary> Labs </summary>

Timing File (.lib) consists of ASCII representations of Timing, Area, and Power associated with the Standard cell. The Naming convention in the timing file follows PVT format (Process, Voltage, Temperature). For example, the standard library used in our case was sky130_fd_sc_hd_tt_025C_1v8, this name suggests that we are using 130 nm technology and the process is typical, temperature is 25C, and 1.8 V represents the voltage.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/opening_lib.png">

The timing File also consists of the technology used for standard cells as in the above example it is CMOS, it also specifies the delay model, unit of time, unit of voltage, unit of resistance, and many other units.

This also includes different different flavours of the same logic gates.

.lib also contains leakage power , area , timing sense of each different flavours of gate cells.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/and2_area.png">

A Look-Up Table (LUT) in a Liberty file is a component that defines the logical behavior and timing characteristics of a combinational logic cell within a digital library. Liberty files are used in the electronic design automation (EDA) industry to represent libraries of standard cells that can be used in VLSI (Very Large Scale Integration) design.

index1 represents input transition , index2 represeents output load capacitance

example of and2_1 gate index table

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/and2_index.png">

A Boolean function is considered "unate" if it satisfies the unateness property, which relates to the behavior of the function with respect to the input variables. Unate functions are important in logic optimization and simplification processes, such as those used in logic synthesis and minimization.

There are two main types of unateness:

Positive Unate Function: A Boolean function is considered positive unate with respect to a particular input variable if, for any assignment of values to the other input variables, the function either remains constant or increases as the specified input variable transitions from 0 to 1. In other words, the function depends only on the positive (1) values of that input variable.

Negative Unate Function: A Boolean function is considered negative unate with respect to a particular input variable if, for any assignment of values to the other input variables, the function either remains constant or decreases as the specified input variable transitions from 0 to 1. In this case, the function depends only on the negative (0) values of that input variable.

And gate is an example of positive Unateness

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/and2_1_unnate.png">

Comparing 2 differnt flavour of and gates namely and2_1 and and2_2 , we see that area of and2_2 > and2_1

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/and2_cmparea.png">

Sequential flops have clock pin as true

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/sdf_clktrue.png">

Unnateness of D flip flop negative edge triggered

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/sdf_unnate_clk.png">

Unateness of D latch positive edge triggered 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f151c2a9853ff8a3480daba1361086d8a79045f9/day7/sdltr_positive_edge_falling%20edge.png">

**lab on .lib in dc_compiler** 

example 1 : to print all the sequential gates 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f151c2a9853ff8a3480daba1361086d8a79045f9/day7/seq_dc.png">

example 2 : prints the library linked

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f151c2a9853ff8a3480daba1361086d8a79045f9/day7/dc_listlib.png">

example 3: Prints the list of cells from the collection

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f151c2a9853ff8a3480daba1361086d8a79045f9/day7/dc_and_list.png">

example 4: prints the pins associated with the gate cell and functionality of a particular gate

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f151c2a9853ff8a3480daba1361086d8a79045f9/day7/dc_lib_attribut_nand4bb.png">

example 5: prints the pins along with the direction of and2_0 gate 

<img  width="1085" alt="lib_dir_and" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f5aa4ba165a0fb2b7b9287f06584e6bc4cb8e860/day7cont/dc_lib_dir.png">

example 6: prints the pins along with the direction of nand4b_1 gate 

<img  width="1085" alt="nand4b_1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f5aa4ba165a0fb2b7b9287f06584e6bc4cb8e860/day7cont/dc_lib_nand4b_1.png">

it also prints the boolean expression i.e function of that cell

example 7: prints the pins along with the direction of and4bb_2 gate 

<img  width="1085" alt="and4bb_1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f5aa4ba165a0fb2b7b9287f06584e6bc4cb8e860/day7cont/dc_lib_and4bb_2.png">

it also prints the boolean expression i.e function of that cell

example 8: A tcl program which takes the list of cells as input and prints the output pins along with its functionality

```ruby
set mylist [list sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_1 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_2 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_4 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_8 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2b_1 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2b_2 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2b_4 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand3_1 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand3_2 \
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand3_4 ];

foreach var $mylist {
  foreach_in_collection var_pins [get_lib_pins ${var}/* ] {
      set pin_name [get_object_name $var_pins];
      set pin_dir [get_lib_attribute $pin_name direction];
      if { $pin_dir == 2 } {


          set pin_func [get_lib_attribute $pin_name function];

          echo $pin_name $pin_dir $pin_func ;
       }
    }
} 
```
<img  width="1085" alt="tclpgm1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f5aa4ba165a0fb2b7b9287f06584e6bc4cb8e860/day7cont/dc_tcl_pgm1.png">

example 9: Prints the attributes of the cell/pin

<img  width="1085" alt="pinattri" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f5aa4ba165a0fb2b7b9287f06584e6bc4cb8e860/day7cont/dc_attri.png">

<img  width="1085" alt="pinattri1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f5aa4ba165a0fb2b7b9287f06584e6bc4cb8e860/day7cont/dc_attri2.png">

example 10: List of all attributes

<img  width="1085" alt="listattri1" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f5aa4ba165a0fb2b7b9287f06584e6bc4cb8e860/day7cont/list_attr.png">

</details>

# Day-8-Advanced Constraints


	
 <details>
 <summary>Clock Terminology</summary>

 - We know that when the when the clock is constrained , Actually clock period gets constrained , which in turn limits the combinational delay 
 i.e 

   *Tclk >= Tcq + Tcomb + Tst*

   *Tcomb <= Tclk - (Tcq + Tst)*

 - **Clock Generator** are a critical component of VLSI (Very Large Scale Integration) circuits, playing a fundamental role in synchronizing various components of an integrated circuit 
    (IC). They provide clock signals that control the timing of digital operations within the IC. Clock generators are designed to produce clock signals with specific characteristics, 
    such as frequency, duty cycle, and phase, to meet the requirements of the overall system.

   Types of clock generators
   
   - Oscillators: These are widely used as clock generators. They generate continuous periodic signals without an external input. Common types include RC oscillators, LC oscillators, and crystal oscillators.

   - Phase-Locked Loops (PLLs): PLLs are versatile clock generators that can generate clock signals with adjustable frequency and phase. They are often used for clock synchronization and  multiplication.
   
   - Delay-Locked Loops (DLLs): DLLs are used to align the phase of a clock signal with respect to another reference clock signal.
   
   - Ring Oscillators: These are simple but effective oscillators often used for generating clock signals with relatively low frequencies.
   
   - Crystal Oscillators: They are highly stable and accurate oscillators that use piezoelectric crystals to generate clock signals.

- **Clock Distribution**

   Once generated, clock signals need to be distributed to various parts of the IC while maintaining their timing integrity. Clock trees are used for this purpose, which involve a 
  hierarchical network of buffers and repeaters to ensure the clock signal reaches all parts of the chip with minimal skew.

   **Clock skew** is a phenomenon in digital design and VLSI (Very Large Scale Integration) circuits where clock signals, which are supposed to be synchronized and have the same edge (rising 
   or falling), arrive at different parts of the circuit at slightly different times.

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/fcc681ed-e268-4965-b71e-5f0bbaa632cd)

  Consider the above circuit in this the clock arrives at flop B at 100 ps and at flop A at 100 ps. From this it clear that clock doesnot arrive at same time for all flops. This 
  difference in arrival of clock is called skew.

  	- Deterministic Clock Skew: Deterministic clock skew is predictable and results from known factors such as wire delays, signal routing, and clock distribution. It is typically 	caused by the physical characteristics of the circuit and can be analyzed and compensated for during the design phase. Techniques like clock tree synthesis and buffer insertion 	are used to mitigate deterministic skew.

  	- Random Clock Skew: Random clock skew, also known as process-induced skew, is caused by manufacturing process variations that affect the timing of signals. These variations can 	lead to slightly different propagation delays for clock signals across different parts of a chip. Random skew is not easily predictable and can vary from chip to chip, even 		within the same manufacturing batch. To address random skew, designers often use techniques like over-design and guard-banding to ensure that the circuit operates reliably under 	worst-case conditions.

	- Global Clock Skew: Global clock skew refers to the difference in arrival times of a clock signal at various points across the entire chip. It affects all elements of the chip 	and can lead to synchronization issues between different clock domains. Managing global clock skew is a critical aspect of clock distribution in large and complex integrated 		circuits. Global skew can be reduced by careful clock tree synthesis and by minimizing the length of critical paths in the design.

	- Local Clock Skew: Local clock skew is specific to a particular region or block within the chip. It can result from variations in the lengths of wires or traces that carry the 	clock signal to different parts of a block. Local skew is often easier to manage than global skew because it affects a smaller portion of the chip. Techniques like buffer 		insertion and clock gating can be used to mitigate local clock skew.

	- Positive and Negative Skew: Clock skew can be further categorized into positive skew and negative skew based on whether clock signals arrive later or earlier than the ideal 		clock edge, respectively.

	   - *Positive Skew*: Positive skew occurs when clock signals arrive at different destinations later than the ideal clock edge. It can lead to setup time violations.
	   - *Negative Skew*: Negative skew occurs when clock signals arrive earlier than the ideal clock edge at different destinations. Negative skew can result in hold time violations.

 
	**Clock Jitter** is a timing variation or uncertainty in the period or phase of a clock signal. It represents the deviation of the actual clock signal edges from their ideal, 
         regularly spaced positions. Clock jitter can occur due to various factors and can have significant implications for the performance and reliability of digital systems.
 

	**Clock latency** refers to the time delay or propagation delay that a clock signal experiences as it travels from its source to various points within an integrated circuit (IC) 
         or digital system. It represents the time it takes for the clock signal to propagate through various components, interconnects, and buffers before reaching its destination.

	- Source latency: The source latency of a clock, also known as clock source latency, refers to the delay or latency introduced by the clock generation circuitry at its source 
          before the clock signal is distributed to other parts of the integrated circuit (IC) or digital system. 
 
 	- Network latency : Network latency in the context of a clock typically refers to the delay or time delay introduced when transmitting a clock signal across a network or 
         communication medium. 


- **Clock Modelling**
 
     We should model the clock for

    - period
    - Source latency
    - Clock skew
    - Clock Network
    - Clock Network latency


</details>

<details>

 <summary> Constraining Design using DC_compiler </summary>

 - Commands in DC Compiler
   ```ruby
   - get_ports * => returns all the ports present in the design
   - get_ports *<keyword>* => returns a collection of port whose name contains that keyword
   - get_ports * -filter "direction == in" => returns all the ports whose direction is input.
   - get_clocks * => returns all the clocks in the design
   - get_clocks *<keyword>* => returns a collection of clocks whose name the given keyword
   - report_clocks <clock_name> => reports all the details of the given clock_name
   - get_cell * -hier => list all hierarchical and physical cells
   - create_clock -name <clock_name> - per <period> [clock definition point] => creates a clock with the given period at the given clock definition point. By default it creates 50% duty 
     cycle clock 
   - create_clock -name <clock_name> - per <period> [clock definition point] -wave {rising,falling} => creates the clock with the given period and the rising edge , falling edge occurs 
     at the given time mentioned in curly braces.
   - set_input_delay -max <value> - clock [<clock_name>] [<definition_port/point>] => This sets the maximum input delay by the given value.
   - set_input_delay -min <value> - clock [<clock_name>] <definition_port/point> => This sets the minimum input delay by the given value.
   - set_input_transition -max <value> [ <defination port> ] => This sets the maximum input transition delay by the given value
   - set_input_transition -max <value> [ <defination port> ] => This sets the minimum input transition delay by the given
   - set_output_delay -max/min <value> - clock [<clock_name>] [<definition_port/point>] => This sets the maximum/minimum output delay.
   - set_output_load -max <value> [<defination_point/port>] => sets the maximum load at the output port mentioned.
   ```

- labs
  
   The design used for the labs is as shown in the below figure .

   ![WhatsApp Image 2023-09-08 at 22 02 32](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/2fd11433-7af8-42fa-a46c-a08f2dcee797)

   The design is read using the command *read_verilog* , then it is linked with the .db and then compiled, Here we can see that design contains 3 Asynchronous Reset flops
  
   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_read_verilog_1.png">

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_read_verilog_compileultra.png">

   **Here are the screenshots of all the get commands**
  
   This returns all the cells of the design

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_getcells_1.png">

    This returns all the cells which are not hierarchical. 

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_getcells_2.png">

   This part of code prints the ports along with their direction.

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_getports.png">

    This returns the reference name of the cells.
  
   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_ref_name.png">

   Now we convert the design into .ddc format  and read this in design_vision

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_dv1.png">

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab1_dv2.png">

   The schematic and circuit of design is as shown in the figure

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab_1_schematic.png">

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab_1_gatesch.png">

   This lists all the pins in the design , and also prints the attributes of the particular pin of the design

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab2_getpins.png">

   The tcl script for selecting only clock pins from the pin collection

    ```ruby
   foreach_in_collection my_pin [get_pins *] {
	set pin_name  [get_object_name $my_pin]:
	set dir [get_attribute [get_pins $pin_name] direction];
	if { [regexp $dir in] } {
		if { [get_attribute [get_pins $pin_ name] clock ] } {
			echo $pin_name ;
   			}
   		}
   	}
   ```

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab2_list_clockpin.png">

   This screenshot shows how the clock is created using the create_clock is as shown in the figure

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab3_create_clk.png">

   This is the screenshot of the output of the program along with the pin and clock name
   ```ruby
    foreach_in_collection my_pin [get_pins *] {
	set pin_name  [get_object_name $my_pin]:
	set dir [get_attribute [get_pins $pin_name] direction];
	if { [regexp $dir in] } {
		if { [get_attribute [get pins $pin_ name] clock ] } {
   			set clk [get_attribute [get_pins $pin_name] clocks];
   			set clk_name [get_objects_name $clk ];
                       
			echo $pin_name $clk_name;
   			}
   		}
   	}
  ```
   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab3_create_clk_pgm.png">

   We can create clock at any port but according to this example it is created on on he U12/Y pin , the tool accepts it but thats a bad clock as it corrupts the data

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab3_badclk.png">

   Creating the waveform with 25% duty cycle

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab3_twentyfivedc.png">

   creating a cock starting with falling edge

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab3_startne.png">

   creating a specific clock here rise edge is at 15 ns

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab3_specificclk.png">

   Before adding constraints to path

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_without_uncertainity.png">

   setting up a clock latency with delay 1 ns

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_latency.png">

   Adding network latency of 0.5 ns

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_nwlatency.png">

  Adding setup and hold delay

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_uncertain.png">

  Now the path is constrained and slack is met , We see that the clock delay is added to the clock period and clock_uncertainity gets subtracted in case of max

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_with_uncertainity.png">

  In case of hold clock_uncertainity gets added to the clock delay

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_hold.png">

  But input and output exeternal delay are not constrained

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_io.png">

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/834ba41eaa4610ed2a26bf90e3ae50272bb012d2/day8/lab4_verbose.png">

  We model the input delay by commands

  set_input_delay -max 5 - clock \[get_clocks MYCLK] \[get_ports IN_A]

  set_input_delay -max 5 - clock \[get_clocks MYCLK] \[get_ports IN_B]

  This sets the input external delay as 5 ns.

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab5_inputAmax.png">

  But the dealy_min path was not constrained

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab5_mindelayuncon.png">

  The minimum delay path was constrained using command

  set_input_delay -min 1 - clock \[get_clocks MYCLK] \[get_ports IN_A]

  set_input_delay -min 1 - clock \[get_clocks MYCLK] \[get_ports IN_B]

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab5_mindelaycon.png">

  **Adding input transition delay and output load to the design**

  set_input_transition -max 0.3 \[get_ports IN_A]

  set_input_transition -max 0.3 \[get_ports IN_B]

  set_input_transition -min 0.1 \[get_ports IN_A]

  set_input_transition -min 0.1 \[get_ports IN_B]
  
  Screenshot of input transition delay from port IN_A
 
  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab5_trans_max.png">

  Adding constraints to output 

  set_output_delay -max 5 \[get_clocks MYCLK] \[get_ports OUT_Y]

  set_output_delay -min 1 \[get_clocks MYCLK]\[get_ports OUT_Y]

  Screenshot of output_delay 
  
  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab5_outtrans_max.png">

  set_load -max 0.3 \[get_ports OUT_Y]

  We can set the load min using the below command but if we don't explicitly mention then it by defaults sets the value of max i.e 0.3 in this case.
  
  *set_load -min 0.1 \[get_ports OUT_Y]*

  Screenshot after constraining the output load

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab5_outload_max.png">

  In this the value of min load is 0.3 i.e the same value set in max load cap
  
  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab5_outload_min.png">

  **Generated Clock**

 	A generated clock, in the context of digital design and VLSI (Very Large Scale Integration), refers to a clock signal that is derived or generated from a primary clock source 		rather than being the primary clock signal itself. Generated clocks are used for various purposes in digital circuits and can have different frequencies, phases, or 			characteristics compared to the original clock source. Here are some common use cases for generated clocks:

- *Frequency Division*: Generated clocks are often used to create lower-frequency clocks from a higher-frequency master clock. This is achieved by dividing the frequency of the primary clock using digital counters or dividers. It allows different parts of the circuit to operate at slower clock speeds for power savings or to meet timing requirements.

- *Frequency Multiplication*: Conversely, generated clocks can be used to create higher-frequency clocks from a lower-frequency source. This is often done using PLLs (Phase-Locked Loops) or DLLs (Delay-Locked Loops). Frequency multiplication is useful for driving specific high-speed components or meeting timing constraints.

- *Clock Skew Control*: Generated clocks can be employed to control clock skew, which is the variation in arrival times of clock signals across the chip. By generating clocks with adjusted phases, designers can minimize clock skew and ensure that data is captured reliably in flip-flops and latches.
  
- *Clock Gating* : Clock gating is a power-saving technique where clocks to certain parts of the circuit are enabled or disabled dynamically based on activity. Generated clocks can be used to control clock gating circuits, allowing for efficient power management by turning off clocks when they are not needed.

- *Clock Domain Isolation* : In complex designs, different sections of a chip may operate in separate clock domains. Generated clocks can be used to create domain-specific clocks, enabling isolated operation with respect to clock signals. This is essential for managing timing constraints and avoiding issues associated with crossing clock domains.

- *Synchronization* : When signals need to cross from one clock domain to another, synchronization is required to prevent data corruption. Generated clocks can be used to create synchronization signals and ensure proper data transfer between domains.


The command to create a generated clock is 

create_generated_clock -name <name_of_generated_clock> - master <master_clock_name> -source \[<master_clock_definition_point>] -div <value> \[<generated_clock_definition_point>]

Here a generated clock namely MYGEN_CLK is created , we can see that its attribute is G

<img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab6_gen_clk.png">


when we report timing we get respect to MYCLK

<img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab6_repmyclkgen_clk.png">

when we add constraints to the MYGEN_CLK we get timing with repect to MYGEN_CLK

set_clock_latency -max 1 \[get_clocks MYGEN_CLK}

set_output_delay -max 5 \[get_ports OUT_Y] -clock \[get_clocks MYGEN_CLK]

set_output_delay -min 1 \[get_ports OUT_Y] -clock \[get_clocks MYGEN_CLK]

<img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab6_repmygen_clk.png">


The design used for this experiment is as follows

```ruby

module lab8 circuit (input rst, input clk , input IN_A , input IN_B , output OUT_Y , output out_clk output reg out_div_clk)
reg REGA, REGB , REGC ;
always @ (posedge clk , posedge rst )
begin
	if(rst)
	begin
		REGA <= 1'b0 ;
		REGB <= 1'b0 ;
		REGC <= 1'b0 ;
		out_div_clk <= 1'b0 ;
	end
	else
	begin
		REGA= IN_A | IN_B;
		REGB<- IN_A ^ IN_B;
		REGC <= !(REGA & REGB) ;
		out_div_clk <= ~out_div_clk
	end
end

assign OUT_Y = ~REGC ;

assign out_clk = clk;

endmodule
```
Loading the new design 

<img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab6_load_design_mod.png">

Instead of writting constraints everytime we can create a .tcl program and then source it

```ruby
create_clock -name MYCLK -per 10 [get_ports clk];
set_clock_latency -source 2 [get_clocks MYCLK];
set_clock_latency 1 [get_clocks MYCLK];
set_clock_uncertainty -setup 0.5 [get_clocks MYCLK];
set_clock_uncertainty -hold 0.1 [get_clocks MYCLK];
set_input_delay -max 4 -clock [get_clocks MYCLK] [get_ports IN_A];
set_input_delay -max 4 -clock [get_clocks MYCLK] [get_ports IN_B];
set_input_delay -min 1 -clock [get_clocks MYCLK] [get_ports IN_A];
set_input_delay -min 1 -clock [get_clocks MYCLK] [get_ports IN_B];
set_input_transition -max 0.4 [get_ports IN_A];
set_input_transition -max 0.4 [get_ports IN_B];
set_input_transition -min 0.1 [get_ports IN_A];
set_input_transition -min 0.1 [get_ports IN_B];
create_generated_clock -name MYGEN_CLK -master MYCLK -source [get_ports clk] -div 1 [get_ports out_clk];
create_generated_clock -name MYGEN_DIV_CLK -master MYCLK -source [get_ports clk] -div 2 [get_ports out_div_clk]; 
set_output_delay -max 4 -clock [get_clocks MYGEN_CLK] [get_ports OUT_Y];
set_output_delay -min 1 -clock [get_clocks MYGEN_CLK] [get_ports OUT_Y];
set_load -max 0.4 [get_ports OUT_Y];
set_load -min 0.1 [get_ports OUT_Y];

```



The report_timing after sourcing the tcl script

<img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab6_rep_moddesign.png">

When we give report_port -verbose

<img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab6_verb_1.png">

<img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab6_verb_2.png">


- When we give set_input_delay -max 3 -clock <clock_name>  \[<definition_point>]

  Here -max 3 implies that the data arrives 3 ns late compared to clock

  set_input_delay -max -3 -clock <clock_name>  \[<definition_point>]

  Here the data is arriving 3 ns before the rising edge which helps in setup time

  so negative max relaxes the path in case of setup

  Positive max tightens the path in case of setup

  In case of hold it is the opposite case negative min tightens the path and positive min relaxes the path.

- Now consider the case where two inputs In_C and In_D are given to combinational logic and it should be constraint , This design is independent of the original design

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/a595756f-21f0-4518-85bb-351eb3959551)

  This can be done by using max_latency or using the virtual lab

  The command for max_latency is

  set_max_latency <value> -from \[<source_port_name>] -to \[<destination_port_name>]

  The command for creating virtual clock

  create_clock -name <virtual_clock_name> -period <value>

  For virtual clock there is no latency and no clock defination point

  Consider a case as shown in the figure

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/389239b9-8175-43ca-a885-faff95ccc5c5)

  In this path from Flipflop 1 to design can be constrained using the set_input_delay command similar to one defined above. But the path from flip flop 2 to design is from fall edge to 
  rise edge This can be modelled using

   set_input_delay -max <value> -clock <clock_name> -clock_fall -add \[<destination_point>]

  Here the -add is signify that we are appending this to already constrained path.

  In cases where there are multiple load attached to a net , Transition delay can get further delayed depending on loading strain.

  In such cases set_driving_cell is more recommanded.

  **NOTE**
     - set_input_transition => It is used mainly for top level primary Input/output .
     - set_driving_cell => It is used for intrernal path.
 

  Command for set_driving_cell is

  set_driving_cell -lib_cell <lib_cell_ref_name> \[all_inputs]

  **Labs on set_max_latency virtual_clocks**

  The design is read and compiled

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_lab14_read.png">

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_lab14_compile.png">

  When we do report_timing -to OUT_Z , we get unconstrained path.

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_unconstrained.png">

  Here are the some of the "all" commands along with their output

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_all_attributes.png">

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_all_attri2.png">

  Here is a tcl program which gives reference names of all connection(-fanout) from IN_A.

  <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_pgm_refname.png">

  Now coming back to constraining the above design we give

  set_max_delay 0.1 -from \[all_inputs] -to \[get_ports OUT_Z]

  Then when we give report_timing -to OUT_Z we see that timing path is violated

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_violated.png">

   Again when we compile the design is optimized and timing is met

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_met_withsigpng.png">

   Viewing the design in Design_vision

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab7_sch.png">

   **Lab on virtual clock**

   **Virtual CLock** is a clock created without a definition point.
  
   Creating virtual clock and constraining it.

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab8_commandvirt.png">
   
   when we give report_timing -to OUT_Z -sig 4 , we get the path is violated
        
   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab8_violated.png">
   
   Again when we compile the design is optimized and slack is met

   <img  width="1085" alt="listattri1" src= "https://github.com/AbhishekChinchani/Samsung_pd/blob/5e577b9b9aeed5ee06eed790f5bc84ca7b05f561/day8/lab8_met.png">

   
  

   

    
  

   

   

  
  



  





  
  
   
  

  

   

   

</details>




# Day-9-Optimizations


	
 <details>
 <summary>Introduction to Combinational and Sequential Optimization</summary>

 Optimization in VLSI design is a crucial aspect of creating efficient and high-performance integrated circuits (ICs). VLSI optimization involves improving various aspects of IC design, such as power consumption, area utilization, timing, and manufacturability.

 The goals of optimization :

   - Cost based Optimization
     
     	- Optimization till cost is met
     	- Over optimization of one goal can harm other goals.

   - Performance Optimization:

       - Speed: Improve the operational speed of the IC by minimizing delays, optimizing critical paths, and ensuring that the design meets specified timing requirements.
       - Throughput: Enhance the overall system throughput by optimizing data flow and minimizing bottlenecks in the circuit.

   - Power Optimization:

        - Dynamic Power: Minimize dynamic power consumption to extend battery life in portable devices and reduce power dissipation in data centers.
        - Static Power: Reduce static power (leakage power) to lower overall power consumption when the IC is in standby or idle mode.



   - Goals for Synthesis
          
     	- Meet Timing
     	
     	- Meet Area
     	
     	- Meet power

**Combination logic Optimisation**

**Combinational Logic Optimization** squeeze the logic to get most optimized design in terms of area and power. There are various techniques for optimizing the circuit
 
 - constant propagation(Direct propagation)
 - Boolean Logic Optimization(K-Means ,QUine Mckluskey)
   
**Constant Propogation** is an optimization technique used by  synthesis tools to minimize hardware implementation.Constant propagation prevents situations in which values are copied from one place or variable to another only to assign their value to a different variable.

**Example on Constant Propogation** 
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/9ee556e759953cfdd337c4c07302f7f415aab031/hand0.jpg">

Consider the above  combinational circuit it consists of and and nor gate, so it requires 6 CMOS transistor to implement , if A is made constant value 0 then A&B will give 0 then 0 and C are given to NOR gate which reduces the expression to C compliment(C`) i.e basically a inverter . By making an input constant we can reduce this combinational circuit to an inverter which can impleneted using only 2 CMOS transistor thus reducing the hardware implementation

**Example on Boolean Logic optimization**

consider a concurrent statement a?(b?c:(c?a:0)):(!c) , this statement is realized using multiple multiplexers. Simplying this equation using boolean reduction techniques we get the output as ~(a^b).

**Resource Sharing**

Resource sharing in VLSI design refers to the practice of efficiently utilizing hardware resources, such as logic gates, memory elements, or functional units, to reduce the overall area, power consumption, and complexity of an integrated circuit (IC). Resource sharing is a fundamental technique in VLSI design and is often employed to optimize the use of limited resources while maintaining or improving the desired functionality.

Consider a example , y = sel ? (a*b) : (c*d) 

The schematic of the above expression is as shown in the figure

![WhatsApp Image 2023-09-13 at 21 54 49](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/f379ba09-918a-44b8-b716-e83c3b51b9d6)

We see that in order to implement this we need two multipliers which consume a lot of area, So instead of using 2 multipliersnwe can reduce to one multiplier and use 2 MUX as shown in the figure

![WhatsApp Image 2023-09-13 at 21 55 36](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/42d487a9-c3c4-42a1-8ea9-b2e1d58e4b81)

**Logic Sharing**

Logic sharing in VLSI design refers to the practice of reusing or sharing logical elements, such as gates or functional blocks, to reduce the overall complexity, area, and power consumption of an integrated circuit (IC). This technique is commonly used to optimize chip designs while ensuring that the desired functionality is maintained.

Consider 2 equations

y = a & b & c

z = (a & b) | c

Here a & b is a common logic between y and z , so we can use the same logic for both the cases

![WhatsApp Image 2023-09-13 at 22 55 36](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/f6ccbbba-d77f-43f2-932c-124a2a999e8c)

**Preferential vs Balanced implementation**

consider the below equation

y = a & b & c & d & e

this can be implemented in 2 ways as shown in the figure ,

![WhatsApp Image 2023-09-13 at 23 03 01](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/c863a48d-646e-40c0-9ab9-4518ba6dfbdf)

In the first case input to y delay is same for all 5 variables so this is a case of Balanced implementation.

In the second case input to y delay is different for the variable , this is case of sequential implementation

Out of this which one is selected is decided by the *constraints*

**Sequential Optimization**

Basic Sequential Optimization

- Sequential Constant propagation
- Retiming
- Unused Flop Removal
- Clock Gating

  	

Advanced

- State Optimization
- Sequential logic cloning

Consider a case where asynchronous reset D Flip-flop is fed with d = 0(i.e GND) always so the output will always be 0 irrespective of the timing or circuit.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/9ee556e759953cfdd337c4c07302f7f415aab031/hand1.jpg">

**Optimization of Unloaded Outputs**

Optimizing unloaded outputs typically involves reduction of power consumption , area, delay for unused or idle pins . It refers to flip-flops whose outputs are not connected to any subsequent logic gates or do not affect the functionality of the overall circuit. so these flip flops can be removed thus retaining the function and reducing the area , power of the design.

**Controlling sequential optimization**

- compile_seqmap_propagate_constants If this variable is not set to true, the sequential constant propagating circuits are retained in circuit and not optimized.
- compile_delete_unloaded_sequential_cells If the variable is not set to true, it doesn't remove the counter cells as discussed, it retains all counters in the circuit.
- compile_register_replication If the variable is set to true, this replicates the registers in cloning optimization so that timing is met.
    
</details>

<details>

 <summary> Labs on Sequential and Combinational Optimization </summary>

 1. **Opt_check**
    
    The RTL code of the opt_check is as follows
    ```ruby
    module opt_check (input a , input b , input c , output y1, output y2);
	wire a1;
	assign y1 = a?b:0;
	assign y2 = ~((a1 & b) | c);
	assign a1 = 1'b0;
    endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt1_report.png">
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt1_dv.png">

2. **Opt_check2**

   The RTL code of the opt_check is as follows
    ```ruby
   module opt_check2 (input a , input b , output y);
	assign y = a?1:b;
   endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt2_report.png">
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt2_dv.png">

3. **Opt_check3**
   
    The RTL code of the opt_check is as follows
    ```ruby
   module opt_check3 (input a , input b, input c , output y);
	assign y = a?(c?b:0):0;
   endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt3_report.png">
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt3_dv.png">

4. **Opt_check4**
   
   The RTL code of the opt_check is as follows
    ```ruby
   module opt_check4 (input a , input b , input c , output y);
 	assign y = a?(b?(a & c ):c):(!c);
   endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt4_report.png">
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt4_dv.png">

    After constraining the maximum delay to 60 ps and setting the cell size of U$ to xnor2_4 we get the violated report

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt4_withsizeviolated.png">

    After again compiling it using compile_ultra we get the faster cell i.e xnor2_1
   
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab1_opt4_violated.png">

**Resource Sharing**

 Consider the example 
 ```ruby
module resource_sharing_mult_check (input [3:0] a , input [3:0] b, input [3:0] c , input [3:0] d, output [7:0] y  , input sel);
	assign y = sel ? (a*b) : (c*d);

endmodule
```

    
  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_withopti.png">
  
    The report before adding constraint to the design are as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_withoptirep.png">

Then constraining with max_delay 2.5 ns 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_withoptiviowith1viol.png">

after optimizing it we get

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_withoptiviowith2_met.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_withoptiarea.png">

After this we set the max_delay to 0.1 ns , the report and area are as follows 

    
   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_withoutoptiarea.png">
   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_withoutoptirep.png">

After this we set maximum area using the below command

*set_max_area 800*

The area and report for the above case are as follows

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_areaopt_area.png">
    
   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_areaopt_rep.png">



**Labs on Sequential Optimizations**

**Tie cells**

Tie cells also known as tie-high and tie-low cells, are components used in vlsi design to ensure that specific signal are held at a predetermined logic value regardless of input condition. These cells are particularlly useful in preventing floating or undefined states in digital circuit.

**dff_const**
  ```ruby
   module dff_const1(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b0;
		else
			q <= 1'b1;
	end

  endmodule
  ```
As it is not a sequential constant we see the flop as shown in the figure 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab3_dff_const1.png">

**dff_const2**
```ruby
module dff_const2(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b1;
	else
		q <= 1'b1;
end

endmodule
```
It is a sequential constant propagation so th flops are optimized

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab3_dff_const2.png">

In some cases we don't need to simplify the circuit in that case we can use the following command to prevent constant sequential propagation

set compile_seqmap_propagate_constants false

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab3_dff_const2_expt.png">

**dff_const3**
```ruby
module dff_const3(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
This is not an example of sequential constant propagation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab3_dff_const3.png">

**dff_const4**
```ruby
module dff_const4(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b1;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab3_dff_const4.png">

**dff_const5**
```ruby
module dff_const5(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b0;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab3_dff_const5.png">
</details>

<details>

<summary>Special optimization</summary>

**Boundary Optimization**

"Boundary optimization" in VLSI (Very Large Scale Integration) design generally refers to the optimization of boundaries or interfaces between different components or modules within an integrated circuit (IC) or system-on-chip (SoC).


*Lab*

RTL Design code
```ruby
module check_boundary (input clk , input res , input [3:0] val_in , output reg [3:0] val_out);
wire en;
internal_module u_im (.clk(clk) , .res(res) , .cnt_roll(en));

always @ (posedge clk , posedge res)
begin
	if(res)
		val_out <= 4'b0;
	else if(en)
		val_out <= val_in;	
end
endmodule


module internal_module (input clk , input res , output cnt_roll);
reg [2:0] cnt;

always @(posedge clk , posedge res)
begin
	if(res)
		cnt <= 3'b0;
	else
		cnt <= cnt + 1;
end

assign cnt_roll = (cnt == 3'b111);

endmodule
```

Loading the design and compiling

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab4_read_ver.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab4_comp_ver.png">

No boundary , Entire design is optimized

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab4_flat_sch.png">

If we don't want boundary optimization then we need to use the below command

set_boundary_optimization <name_pin> false

example : *set_boundary_optimization u_im false*

The following image shows the design with hierarchical module u_im in the design.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab4_sch_bound.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab4_sch_bound_im.png">

**Register Retiiming**

Register retiming is a technique used in Very Large Scale Integration (VLSI) design to optimize the performance of digital circuits by rearranging the registers in the circuit without changing its functionality. The primary goal of register retiming is to minimize the critical path delay, which is the longest path in the circuit from an input to an output.

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/849a0de6-08f5-4891-80f4-d4e3da617666)

In the above example as we can see that there is a huge positive slack of 48 ns , so the max frequency which it can work is 20MHz , but by slicing the big logic we can improve the frequency . The tool do not share the logic equally, it optimizes the design to the extent. So, If it is shared as shown, the delay of the design now will be 20ns in the critical path. This, Improving the performance of the design to 50 MHz. 

*Lab*

Consider a example in which a 4-bit multiplier multiplying two 4-bit numbers and three 8-bit registers through which data is propagated to output.

```ruby
module check_reg_retime (input clk , input [3:0] a, input [3:0] b , output [7:0] c , input reset);

wire [7:0] mult;
assign mult = a * b;
reg [7:0] q1;
reg [7:0] q2;
reg [7:0] q3;




always @ (posedge clk , posedge reset)
begin
	if(reset)
	begin
		q1 <= 8'b0;
		q2 <= 8'b0;
		q3 <= 8'b0;
	end
	else
	begin
		q1 <= mult;
		q2 <= q1;
		q3 <= q2;
	end
end
assign c = q3;

endmodule
```

Reading the design 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab6_read_ver.png">

The schematic before retime

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab6_des_org.png">


After constraing the design with the given specs when we give report_timing we get violated report on the input side

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab6_rep_org_viol_asrc.png">

In order to rectify this we retime it using following command

*compile_ultra -retime*

After this the violation reduces and is now only on output path 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab6_rep_viol_retime.png">

The Design after retime is

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab6_sch_retime.png">

The multiplier used in this has the following design

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab7_des_mult.png">

**Isolating Output ports**

n VLSI (Very Large Scale Integration) design, isolating output ports often refers to ensuring that the output signals of a circuit or module are properly isolated and do not interfere with each other or with other parts of the system. This isolation is crucial for maintaining signal integrity, reducing noise, and preventing unintended interactions.

Consider a below example, which contains more number of outputs to be connected after implementation of design, this may cause a violation of internal delays as cell delay is a function of load capacitance. Inorder to avoid internal failure, we isolate by inserting a buffer at output port. So, the buffer drives the external load.Now, the internal paths are decoupled from output paths.

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/c0ccce07-236a-4fa6-bd14-c783b30961f3)


*Lab*

RTL Design code
```ruby
module check_boundary (input clk , input res , input [3:0] val_in , output reg [3:0] val_out);
wire en;
internal_module u_im (.clk(clk) , .res(res) , .cnt_roll(en));

always @ (posedge clk , posedge res)
begin
	if(res)
		val_out <= 4'b0;
	else if(en)
		val_out <= val_in;	
end
endmodule


module internal_module (input clk , input res , output cnt_roll);
reg [2:0] cnt;

always @(posedge clk , posedge res)
begin
	if(res)
		cnt <= 3'b0;
	else
		cnt <= cnt + 1;
end

assign cnt_roll = (cnt == 3'b111);

endmodule
```

The Design before isolating the ports 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab7a_sch_dv_zoom.png">

The timing report before isolating ports

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab7a_report_withoutbuf.png">

The command for isolating ports

*set_isolate_ports -type buffer \[all_outputs]*

The Design after isolating the ports

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab7a_sch_withb.png">

The timing report after isolating the port

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab7a_report_withbuf_reg0d.png">



**Multicycle path**

A multicycle path in VLSI (Very Large Scale Integration) design refers to a timing path within a digital circuit where a signal takes multiple clock cycles to propagate from a source register (or flip-flop) to a destination register. This is in contrast to a single-cycle path where the signal must propagate and settle within a single clock cycle.

Multicycle paths are typically encountered in digital designs when specific timing constraints or requirements allow for signals to have longer propagation delays. These paths are often used for various purposes, including achieving certain functionalities, optimizing critical paths, or accommodating variations in clocking schemes.


For a single cycle path, the setup check is done at the consecutive edge of the flop and hold is done at the same edge of the flop. Hold is always checked edge before setup. For a half cycle path, the setup check is done at the subsequent fall edge of the flop and hold is done at the previous falling edge of the flop. In a half cycle path, setup is very stringent and hold is relaxed. Fir a multicycle path, the -setup switch specifies the number of cycles after the launch edge, it needs to check setup and the -hold switch specifies the number of cycles the launch edge moves to check with capture.

*Lab*

The RTL design code 
```ruby
module mcp_check (input clk , input res  , input [7:0] a , input [7:0] b, input en , output reg [15:0] prod);

reg valid; 

always @ (posedge clk , posedge res)
begin
	if(res)
		valid <= 1'b0;
	else 
		valid <= en;
end



always @ (posedge clk , posedge res)
begin
	if(res)
		prod <= 16'b0;
	else if (valid)
		prod <= a * b;
end

endmodule
```

The tcl file for constraints

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_tcl35.png">

The report before optimization

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_rep_viol_heavy.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_rep_viol_heavy_with_compile.png">

Now using the command 

set_multicycle_path -setup 2 -to prod_reg\[*]/D -from \[all_inputs] 

The input report timing 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_rep_prodregd.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_rep_prodregdtoinp.png">

When we give report_timing -delay min we get the violated report as we have only optimized setup path and not hold path

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_rep_min.png">

Then optimizing the hold path by the following command

set_multicycle_path -hold 1 -to prod_reg\[*]/D -from \[all_inputs] -to prod_reg\[*]/D 

report_timing after optimizing hold path

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_rep_min_met.png">

But the output slack is not met , because high load on the output side

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_outload_viol_rep.png">

By isolating the port we can rectify this

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/5959a04f9aaf466128753d1e090a12cef3096ac5/day9/lab8_final_met.png">


**False_paths**

In VLSI  design and digital circuit timing analysis, *False paths* refer to paths within the circuit that, while physically existent, do not need to meet timing constraints. These paths are "false" in the sense that they are not relevant for circuit operation or performance, and as such, they are ignored during timing analysis. False paths are important to identify because they can significantly simplify the timing analysis process, making it more efficient and accurate.

</details>
    
# Day-10-QOR

<details>

<summary> Report_timing </summary>

Quality checks in Very Large Scale Integration (VLSI) design and manufacturing are crucial to ensure the reliability and functionality of integrated circuits (ICs). VLSI quality checks involve various stages of the design and manufacturing process to identify and rectify potential issues.Quality checks in VLSI are iterative and continuous throughout the design and manufacturing process to guarantee the reliability, performance, and manufacturability of integrated circuits. Advanced simulation and verification tools are often used to automate and streamline these checks.

Propagation delay, in the context of digital electronics and integrated circuits, refers to the time it takes for an electrical signal to travel from the input of a digital logic gate or circuit to its output. It is a critical parameter in digital design because it affects the speed and performance of the circuit. Propagation delay is typically measured in time units, such as nanoseconds (ns) or picoseconds (ps), and it depends on various factors, including the specific technology used, the length of interconnecting wires, and the complexity of the circuit.

Rising Edge Propagation Delay (tpdr): This is the time it takes for the output signal to transition from a low (0) to a high (1) level after the input signal has made a similar transition. 

Falling Edge Propagation Delay (tpdf): This is the time it takes for the output signal to transition from a high (1) to a low (0) level after the input signal has made a similar transition. 

We know that Rise to fall delay is not same as fall to rise delay as mobility of electrons and holes are not same.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/WhatsApp%20Image%202023-09-18%20at%2011.41.24.jpg">


In this we can see that in the first case when both A and B are 0 the output Y is 1 , which implies That both a and b help helps in charging the capacitor, but in the next case when either A/B is 1 only the other one charges the capacitor so , it is clear that A to Y delay is not same as B to Y delay

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/theory_example.png">

Inverter gate :

A rise -> Y fall (0.5 ns)

A fall -> Y rise (0.4 ns)

AND gate :

A rise -> Y rise (0.7 ns)

A fall -> Y fall (0.65 ns)

B rise -> Y rise (0.65 ns)

B fall -> Y fall (0.6 ns)

Now the different timing paths along with delays are as follows

1. DFFA(Clk -> Q r) -> INV(A r) -> INV(Y f) -> AND(A f) -> AND(Y f) -> DFFC(f)

    0.5      +          0.5            +         0.65      =  1.65ns

2.  DFFA(Clk -> Q f) -> INV(A f) -> INV(Y r) -> AND(A r) -> AND(Y r) -> DFFC(f)

    0.4      +          0.4            +         0.7      =  1.5ns

3. DFFA(Clk -> Q r) ->  AND(B r) -> AND(Y r) -> DFFC(r)

   0.5      +          0.65         =   1.15 ns

4. DFFA(Clk -> Q f) ->  AND(B f) -> AND(Y f) -> DFFC(f)

   0.4      +          0.6         =   1.0 ns


The path with the highest delay is 1st path so that path is called the critical path. Critical path is the one which decides the operating frequency of that circuit

- report_timing -from DFFA/CLK -to DFFC/D -delay max 

	we get the **first path**

- report_timing -from DFFA/CLK -to DFFC/D -delay min

	we get the **second path** 

- report_timing -delay min -to DFFC/D

	we get **fourth path**

- report_timing -delay max -to DFFC/D

	we get the **first path*8

- report_timing -delay max -rise_to DFFC/D

	we get the **second path**

- report_timing -delay max -fall_to DFFC/D

	we get the **first path**

Now consider the clock period as 5 ns, setup time is 0.5 ns and hold time is 0.4 ns.

DFFA(Clk -> Q r) -> INV(A r) -> INV(Y f) -> AND(A f) -> AND(Y f) -> DFFC(f)

0.5      +          0.5            +         0.65      =  1.65ns

This time is called as arrival time 

The required time is Clock period - setup time 

5 - 0.5 = 4.5ns

setup slack = Required - Arrival (4.5 - 1.65 = 2.85 ns)

For Hold setup

The hold time is 0.1 ns

Required time  = hold time + uncertainity = 0.1 + 0 = 0.1 ns

DFFA(Clk -> Q f) ->  AND(B f) -> AND(Y f) -> DFFC(f)

0.4      +          0.6         =   1.0 ns

This is the arrival time 

Hold slack = Arrival - required (1 - 0.1 = 0.9 ns)


Now consider another example

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/theory2.png">

- report_timing -max_paths 2

   	This returns the worst slack from each pin end . In this case the path with slacks -1.2 ns and -1.0 ns



- report_timing -max_paths 2 -nworst 2 

	This returns the worst slack , In this case it is -1.2 ns and 1.1 ns

</details>

<details>

 <summary>Labs</summary>

 The example used in this lab has the following design code
 ```ruby
 module lab8_circuit (input rst, input clk , input IN_A , input IN_B , output OUT_Y , output out_clk , output reg out_div_clk);
reg REGA , REGB , REGC ; 

always @ (posedge clk , posedge rst)
begin
	if(rst)
	begin
		REGA <= 1'b0;
		REGB <= 1'b0;
		REGC <= 1'b0;
		out_div_clk <= 1'b0;
	end
	else
	begin
		REGA <= IN_A | IN_B;
		REGB <= IN_A ^ IN_B;
		REGC <= !(REGA & REGB);
		out_div_clk <= ~out_div_clk; 
	end
end

assign OUT_Y = ~REGC;

assign out_clk = clk;

endmodule
```

 When we report_timing along with capacitance trans nets input, This is for setup check as we can see path type is max , launch edge is 0 ns and capture edge is 10 ns. Also we can see 
 that slack is *required time - arrival time*

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/lab1_rep1.png">

 When we give *report_timing -from IN_A* 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/2596dd3a7ae79395623be98c0ae52d86985fc806/day10/new/lab1_rep2.png">

 When we give *report_timing -rise_from IN_A -sig 4 -trans -inp -cap -nets* 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/lab1_rep3.png">

 When we give *report_timing -rise_from IN_A -to REGA_reg/D -sig 4 -trans -inp -cap -nets* , we can see that there is mismatch in rise to fall delay and fall to rise delay as compared with second report.

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/a20d12f0ab0b69a0a13770694e728585593c1598/day10/new/lab1_rep4.png">

 When we give *report_timing -delay min -from IN_A* we can see that this is for hold check as we can see path type is min , launch edge is 0 ns and capture edge is 0 ns. Also we can see 
 that slack is *arrival time - required time*

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/22106adcf6e3da3c1c62257582a787a0ceda69dd/day10/new/lab1_rep5.png">

 When we give *report_timing -thr U15/Y* 
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/97a1d1aaa2baac49e3230dc133eb5de04a4cf163/day10/new/lab1_rep6.png">

 When we give *report_timing -thr U15/Y -delay min*
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d2c2a84b88dbf06c962f8f7abf67241278e9d4d2/day10/new/lab1_rep7.png">

 *Checking whether the deign is loaded correctly or is there any Human error*

 Reading the design , after linking

*check_design*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/lab2_check_design1.png">

*check_timing* this showed all the paths were unconstrained

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/f9696cfc0d6a669c679ee1014fcc09ce6d57d908/day10/new/lab2_rep1.png">

*report_constraints* ,This gives the default value of the constraints

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/928192fdc205f372138c4a580e4e65ccd88a174f/day10/new/lab2_rep2.png">

After adding constraints to the design when we give *check_timing*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/lab2_check_timing2.png">

when we give *report_timing*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/215874b12bc7483b63a10485ec5a97ae40eee355/day10/new/lab2_report1.png">

*report_constraints*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4051dddb605ded6ee2dc66ed138ba245528eb097/day10/new/lab2_report2.png">

Consider a case of 128 : 1 Mux

Design Code 
```ruby
module mux_generate ( input [127:0] in, input [6:0] sel, output reg y);
integer k;
always @ (*)
begin
for(k = 0; k < 128; k=k+1) begin
	if(k == sel)
		y = in[k];
end
end
endmodule
```
when we read this file , it infers it as latch because we have used always block

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/mux128_infers_as_latch.png">

Then we link and do compile_ultra, if we want to see what all cells it has inferred,

*write -f verilog -out <filename>*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/write_verilog_128mux.png">

We constraint the max delay using command

*set_max_delay -from \[all_inputs] -to \[all_outputs] 3.5*

We set the max capacitance 

*set_max_capacitance 0.025 \[current_design]*

*report_timing* we see its violated

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/cdc3707cc36ae11d822ce0bef1331068dc110880/day10/new/lab2_treport.png">

*report_constraints -all_violators*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/9759b73aad3a2686ebbdfe9235cb423cbf64a618/day10/new/lab2_report_constraints_violators1.png">

when we do compile_ultra 

*report_constraints*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/d4d2eb7d21edf0901aa403cc04210dd19e4e1414/day10/new/lab2_report_constraints_violators2.png">

*report_timing*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/67510e94b9f5c8b998463f038eaeb9614a03fc10/day10/new/lab2_trep1.png">

Consider another example of 128 bit enable
```ruby
module en_128 (input [127:0] x , output [127:0] y , input en);
	assign y[127:0] = en ?x[127:0]:128'b0;
endmodule
```

after reading this code and compiling this code

*report_timing -from en -inp -nets -caps* we see that there are 128 fanouts

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/0cd3a23a4e9e674da7f07cd236507fec174bbac3/day10/new/lab2_trep2.png">

after setting the max cap as 0.03 

*report_constraints*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/50a2b2373d921405d8718b39397ece4eaef77d94/day10/new/lab2_cons1.png">

after compile_ultra

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/ad625dad523d32ed9e3868cbfe0f2cb830a044e3/day10/new/lab2_trep3.png">

Now viewing this in Design_vison by writing out ddc

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/lab2_dv1.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/lab2_dv2.png">

Now set the trans constraints 

Before compile ultra *report_constraints*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/dac7685ce73d71ccc1fe532bb621308847df1773/day10/new/last1.png">

After compile ultra

*report_constraints*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/bc0dec9e19f2d1c89a080174b3d89a825fc5c5b3/day10/lab2_constraints_aft_transition.png">

*check_timing*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/2a158391db95a3ef34432f342717ceb0316172e3/day10/new/last_new.png">

*report_timing -nosplit -sig 4 -inp -trans -cap*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/2a158391db95a3ef34432f342717ceb0316172e3/day10/new/lat_one.png">

</details>


# Day-11-Introduction to SOC

 <details>
 <summary>Introduction to SOC</summary>

- SoC, or System-on-Chip, is a comprehensive integrated circuit that combines various hardware and software components into a single chip. SoCs are a fundamental building block of modern electronic systems, and they play a crucial role in a wide range of applications, from smartphones and tablets to IoT devices and embedded systems. 

- SoCs integrate multiple hardware components, including one or more processor cores, memory, peripherals (such as GPUs, DSPs, and communication interfaces), custom IP blocks, and often even sensor interfaces, onto a single chip. This integration offers advantages in terms of reduced power consumption, smaller form factor, and improved performance.

- SoCs are designed to perform specific functions or tasks within an electronic system. They can be tailored to the requirements of the target application, making them highly versatile.
- SoCs can be customized to include specific hardware accelerators or IP blocks to optimize performance, power efficiency, and functionality for a particular application.
- Designing an SoC is a complex and multidisciplinary task that involves hardware design, software development, verification, and testing.

</details>

<details>

 <summary>EXYNOS 2100</summary>

 Exynos 2100 was one of Samsung's flagship system-on-chip (SoC) designs. It was used in some of Samsung's high-end smartphones and other devices.

 **Architecture**

*CPU Cores* :

- The Exynos 2100 featured a tri-cluster CPU architecture.
- One prime Cortex-X1 core: This high-performance core was designed for demanding tasks and offered a significant boost in single-threaded performance.
- Three Cortex-A78 cores: These were high-performance cores intended for multi-threaded tasks, providing a balance between performance and efficiency.
-  Four Cortex-A55 cores: These were energy-efficient cores used for less demanding tasks to save power. 
 
*GPU* : 

- The Exynos 2100 was equipped with the Mali-G78 GPU, which was designed to deliver excellent graphics and gaming performance.
- It featured multiple execution cores and supported the latest graphics APIs.

*AI and Machine Learning* : 
- The SoC incorporated dedicated AI (Artificial Intelligence) and machine learning accelerators to enhance AI-related tasks such as image recognition, voice processing, and more.
- Samsung's proprietary NPU (Neural Processing Unit) or AI Engine likely played a role in this.

*Memory*: 

- The Exynos 2100 supported LPDDR5 (Low Power DDR5) RAM for fast and efficient memory access. This enabled smooth multitasking and app performance.

*Connectivity* :

- The chip likely included a 5G modem to support high-speed mobile data connectivity.
- It would have featured various connectivity options, including Wi-Fi, Bluetooth, and GPS.
  
*Multimedia* : 

- The Exynos 2100 supported advanced multimedia features, including high-resolution camera sensors, 8K video recording, and hardware-based codecs for efficient video playback and encoding.

*Security* : 

- Samsung typically includes a range of security features in its flagship SoCs. This may include hardware-based encryption, secure boot processes, and trusted execution environments for enhanced device security.

*Power Efficiency* : 

- The 5nm manufacturing process, combined with the heterogeneous CPU architecture, was aimed at providing a good balance between performance and power efficiency.
  
</details>

<details>

 <summary> Video_summary </summary>

- Chips are made using extremely pure mono crystalline Silicon ingot called *bull* with only one impurity for every 10 million silicon atoms.
- These silicon bulls are fabricated in different diameters, common ones are 100mm,150mm,200mm,300mm
- Transitors are built on p and n conductive layers that exist in a doped wafer. These are smallest control units in microchips.
- Semiconductor Manufacturing Process Summary:

	*Design and Layout*: The process begins with the design of the integrated circuit (IC) or microchip. Engineers use specialized software to create a detailed layout of the chips 		specifying the location and arrangement of transistors, interconnects, and other components.

	*Mask Creation*: The chip's design is used to create a series of photomasks, which are high-precision templates that define the patterns to be etched onto the silicon wafer 			during 	fabrication.

	*Wafer Preparation*: Silicon wafers, typically made from highly purified single-crystal silicon, are cleaned and polished to create a flat, defect-free surface. The wafers are 		also coated with a thin layer of material, such as silicon dioxide (oxide), to act as an insulator.

	*Photolithography*: Photomasks are used in a photolithography process to project the chip's design onto the silicon wafer. Ultraviolet (UV) light or deep ultraviolet (DUV) light 		is passed through the masks to define the circuit patterns on the wafer's surface. 

	*Etching*: After photolithography, a chemical or plasma etching process is used to remove excess material from the wafer's surface, leaving behind the desired patterns. This 			step defines the locations of transistors, interconnects, and other features. There can be etched using wet or plasma etching.

	*Ion Implantation*: Dopant ions (such as boron or phosphorus) are implanted into the silicon wafer to modify its electrical properties, creating N-type and P-type regions 			necessary for transistor operation.

	*Deposition*: Thin layers of materials (such as metal or dielectrics) are deposited onto the wafer's surface using techniques like chemical vapor deposition (CVD) or physical 			vapor deposition (PVD). These layers form the conductive pathways and insulating barriers on the chip.

	*Chemical Mechanical Polishing (CMP)* : CMP is used to planarize the wafer's surface, ensuring a uniform thickness of deposited material across the chip.

	*Lithography and Etching (Repeated)*: Multiple iterations of lithography and etching are performed to create the various layers of the chip, including the metal interconnect 			layers 	that link transistors and components.

	*Annealing*: Heat treatments, called annealing, are applied to activate dopants, relieve stress, and improve the performance and reliability of the semiconductor materials.

	*Testing and Inspection* : At various stages of manufacturing, the wafers undergo extensive testing and inspection to identify defects, verify functionality, and ensure quality.

	*Dicing*: The processed wafer contains multiple chips separated a tiny space between them called as *scribe line* . This processed wafer is cut into individual chips using a 			process called dicing. Each chip will become a separate microchip.

	*Packaging* : The individual microchips are placed into packages that protect them from environmental factors and facilitate connection to external circuits. Packaging also 			includes adding pins or balls for electrical connections.

- These microchips should be made in clean room . A clean room is a controlled environment designed to minimize contamination and maintain specific environmental conditions critical to the fabrication of integrated circuits and other microelectronics devices. Clean rooms are essential for ensuring the reliability and performance of semiconductor components. 
 
</details>

# Day-12-BabySOC Modelling

<details>

 <summary> Introduction</summary>

 **Modelling** 

 Modeling in the context of VLSI (Very-Large-Scale Integration) refers to the process of creating abstract representations of electronic circuits and systems that are implemented on integrated circuits (ICs) or chips. VLSI modeling plays a crucial role in the design, simulation, and verification of complex semiconductor devices and electronic systems. 

In VLSI design, modeling is an iterative process where designers move from high-level abstractions to lower-level details while ensuring that the design meets its specifications, performance targets, and power requirements. Proper modeling and simulation are essential for reducing design errors, optimizing performance, and bringing reliable semiconductor devices to market.

**Intellectual Property**

Intellectual property (IP) in the context of VLSI (Very-Large-Scale Integration) refers to the legal protections and rights associated with the designs, innovations, and creations developed in the field of semiconductor and integrated circuit (IC) design. IP in VLSI is essential to protect the investments and innovations made by designers, semiconductor companies, and organizations. 

The three main intellectual property which we are going to model are

   - RVMYTH Modelling
   - PLL Modelling
   - DAC Modelling


**RVMYTH**

The RVMYTH is based on RISC V architecture. RISC-V stands for "Reduced Instruction Set Computing - Version 5." It is gaining significant attention in the world of computer architecture due to its open-source nature and flexibility. RISC-V provides a foundation for building custom processors tailored to specific applications, from embedded systems to high-performance computing. This open ISA allows developers and organizations to design their own processors or adopt existing implementations, promoting innovation, cost-efficiency, and compatibility across a wide range of hardware platforms.There are two primary integer variants in RISC V, known as RV32I and RV64I.

RV32I

- RV32I is one of the standard base instruction set extensions in the RISC-V (pronounced "risk-five") architecture. In RISC-V, the letter "RV" stands for "RISC-V" itself, followed by the number "32," which indicates a 32-bit architecture, and "I," which denotes the base integer instruction set.
- RV32I is the base integer instruction set in RISC-V, providing the fundamental operations for processing integer data. It includes instructions for tasks like arithmetic, logical operations, data movement, branching, and control flow.
- RV32I signifies that this variant of RISC-V uses 32-bit data and address widths. This makes it suitable for embedded systems, microcontrollers, and other applications where a smaller memory footprint and lower power consumption are desired.
-  RV32I is designed with simplicity and orthogonality in mind, following the principles of Reduced Instruction Set Computing (RISC). Instructions are typically uniform in size and are easy to decode, which simplifies the processor's control logic.
-   RV32I defines a set of 32 general-purpose registers (integer registers), labeled x0 through x31. Some of these registers have special purposes, like x0, which is hardwired to zero, and x1, which is typically used as the link register for function calls.

RV64I

- RV64I is a standard base instruction set extension in the RISC-V architecture. In RISC-V, the letter "RV" stands for "RISC-V" itself, followed by the number "64," which indicates a 64-bit architecture, and "I," which denotes the base integer instruction set.
- RV64I is the base integer instruction set in RISC-V, providing fundamental operations for processing 64-bit integer data. It includes instructions for tasks like arithmetic, logical operations, data movement, branching, and control flow.
- RISC-V uses 64-bit data and address widths. This makes it suitable for a wide range of computing applications, including general-purpose computing, servers, workstations, and high-performance computing.
- RV64I defines a set of 32 general-purpose registers (integer registers), labeled x0 through x31. However, in a 64-bit architecture, these registers are extended to 64 bits in width, allowing for the manipulation of 64-bit integer data.

**PLL**

A Phase-Locked Loop (PLL) is a fundamental building block in VLSI (Very-Large-Scale Integration) design, particularly in the field of analog and mixed-signal integrated circuits. PLLs are versatile and widely used in various applications, providing essential functionality for clock generation, frequency synthesis, clock recovery, and many other tasks in semiconductor devices.

A Phase-Locked Loop (PLL) is an electronic feedback system that can generate an output signal with a controlled phase and frequency in relation to an input reference signal.PLLs are extensively used in VLSI design due to their ability to synchronize and stabilize clock signals, recover data from communication signals, and create high-quality clock sources for digital circuits.PLLs are composed of several key components, including a phase detector, a voltage-controlled oscillator (VCO), and a loop filter.

The main function and application of PLL

*Clock Generation and Distribution* :

PLLs are frequently used to generate high-frequency, stable clock signals for digital systems, such as microprocessors and memory devices.
They allow for precise control of clock frequency, phase, and duty cycle, which is critical for synchronous digital circuits.

*Frequency Synthesis*:

PLLs can be used to generate output frequencies that are integer multiples (or fractions) of an input reference frequency.
This capability is vital in various communication systems, such as wireless devices and digital television, where different frequencies must be synthesized.

*Clock Recovery*:

In communication systems, PLLs are employed to extract and synchronize clock information from incoming data signals.
They are essential for demodulating and processing digital data streams accurately.

*Phase Synchronization* :

PLLs are used in phase-locked systems to ensure that the phase of the output signal is locked to the phase of the reference input signal.
This is critical in applications like radar systems, where phase coherence is necessary.

**DAC**

Digital-to-Analog Converter, is an essential component that converts digital signals into analog signals. DACs play a crucial role in various applications, including telecommunications, audio systems, signal processing, and more.

*Function of DAC*

- A DAC is used to convert discrete digital values (usually binary) into continuous analog signals.
- It takes a binary input code and generates a corresponding voltage or current output, where each digital value maps to a specific analog voltage or current level.
</details>

<details>

 <summary>Lab</summary>

 **Task1** 

 *4:1 MUX*

 Design Code:

 ```ruby
 module mux_generate ( input [3:0] in, input [1:0] sel, output y);
	assign y = in[sel];
endmodule
```

Testbench:
```ruby
`timescale 1ns/1ps
module tb_mux;

	reg [3:0] in;

	reg [1:0] sel;

	wire y;

	mux_generate uut (.in(in),.sel(sel),.y(y));

initial 

begin

	
in=4'b1010;
sel = 2'b00;
#2 sel=2'b00;
#2 sel=2'b01;
#2 sel=2'b10;
#2 sel=2'b11;
#2 sel=2'b00;
#100 $stop;
end

initial 
begin
	$dumpfile("tb_mux.vcd");
	$dumpvars(0,tb_mux);


end

endmodule
```

GTKWave of 4:1 MUX
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/569efc3b26928d79a63420fb445c33ddc0e9332b/day12/mux_gtk_without_x.png">

**Task2**

<u>Baby SOC modelling</u>

1. Modelling rvmyth
   
*Commands* 
```ruby
iverilog mythcore_test.v tb_mythcore_test.v 
./a.out
gtkwave tb_mythcore_test.vcd
```

GTKWave for rvmyth
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/569efc3b26928d79a63420fb445c33ddc0e9332b/day12/risc5_rvmyth.png">

10-bit digital output namely D is observed in rvmyth. It works as RISC V processor with 5 cycles fetch , decode , read , execute and write.It is basically a logic which adds the natural numbers till the sum is less than 1000 and when it exceeds 999, it starts subtracting the natural number in the reverse order.

2. Modelling DAC

*Commands*
 ```ruby
iverilog avsddac.v avsddac_tb_test.v
./a.out
gtkwave avsddac_tb_test.vcd
```  
GTKWave for DAC

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/04df7701-2026-46bf-8cc8-16907908468d)

 This is a 10 bit digital to Analog converter, which has Vhigh 3.3v and Vlow as 0v .It coverts the equivalent 10 bit sign to its respective output. EX: D[9:0] = 111111011 = equivalent to 1019 Out = Vref * (1019/1024) =3.2878986 Which is matched with gtkwave.

3. Modelling PLL
   
*Commands*
```ruby
iverilog avsd_pll_1v8.v pll_tb.v
./a.out
gtkwave test.vcd
```
 GTKWave for PLL
 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/371508bb-3b24-405d-b751-9d854febb928)

4. Modelling rvmyth and adc interface

*Commands*
```ruby
verilog rvmyth_avsddac.v rvmyth_avsddac_TB.v
./a.out
gtkwave rvmyth_avsddac.vcd
```
gtkwave
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/569efc3b26928d79a63420fb445c33ddc0e9332b/day12/rvmyth_dac_integrated.png">\

5. Modelling rvmyth and pll interface

*Commands*
```ruby
iverilog rvmyth_pll.v rvmyth_pll_tb.v
./a.out
gtkwave test1.vcd
```

gtkwave 
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/569efc3b26928d79a63420fb445c33ddc0e9332b/day12/rvmyth_pll_integrated.png">

6. Interfacing all_modules

*Commands*
```ruby
iverilog vsdbabysoc.v testbench.v avsdpll.v avsddac.v mythcore_test.v
./a.out
gtkwave dump.vcd
```
gtkwave
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/569efc3b26928d79a63420fb445c33ddc0e9332b/day12/top_module_crct_one.png">

</details>

# Day-13-Post Synthesis Simulation
<details>

<summary>Synthesis</summary>
Synthesis refers to the process of transforming a high-level description of a digital circuit into a gate-level representation that can be implemented in hardware. This process involves several key steps and is a crucial part of the VLSI design flow:

1. Design Specification: The first step is to have a clear and detailed specification of the digital circuit's functionality. This specification defines what the circuit should do and what its inputs and outputs are.

2. High-Level Design: Next, a high-level design of the circuit is created. This is often done using hardware description languages (HDLs) such as VHDL or Verilog. High-level design focuses on the logical functionality of the circuit and is independent of the specific hardware implementation.

3. Synthesis: The synthesis process takes the high-level design and maps it to a gate-level representation. This involves selecting specific gates (e.g., AND, OR, XOR) and interconnections to implement the desired logic functions. The output of the synthesis process is often a netlist, which is a description of the circuit in terms of gates and their connections.

4. Technology Mapping: After synthesis, technology mapping is performed to select the actual physical gates from a technology library that matches the gate-level representation. Different libraries may contain gates with varying characteristics, such as speed, power consumption, and area.

Overall, synthesis is a critical step in the VLSI design process, as it bridges the gap between the high-level design description and the physical implementation of the circuit on a silicon chip. The goal is to produce a design that is not only functionally correct but also optimized for factors such as speed, power consumption, and area utilization.

**Post-synthesis** typically refers to a phase in the design flow that occurs after logic synthesis. Here's what this phase involves:

   1. Timing Analysis: Timing analysis is performed to ensure that the design meets the required timing constraints. This involves checking setup and hold times, clock-to-q delays, and 
       other timing parameters.

   2. Functional Verification: The post-synthesis design must be functionally verified to ensure that it behaves as intended and matches the original high-level specification.

   3. Power Analysis: Power analysis is crucial to estimate the power consumption of the design and ensure it meets power budget constraints.

   4. Constraint Updates: Any necessary updates to design constraints may be made during this phase, based on the results of timing and power analysis.

   5. Scan Insertion: In some cases, scan chains may be inserted into the design during post-synthesis for testing and debugging purposes.

   6. Gate-Level Simulation: Gate-level simulations may be run to validate the design's functionality and to refine the design further.

</details>

<details>

 <Summary> 4:1 MUX</Summary>

A 4:1 multiplexer (MUX) is a digital circuit that has four input lines (usually labeled as D0, D1, D2, and D3), one or more select lines (often referred to as S or A, B, etc.), and a single output line (often labeled as Y or Z). The purpose of a 4:1 MUX is to select one of the four input lines and route it to the output based on the binary value of the select lines.

Here's how a 4:1 MUX works:

Inputs (D0, D1, D2, D3): The four input lines represent the data inputs. Each of these lines can carry a binary signal (0 or 1).

Select Lines (S0, S1): The select lines determine which input is connected to the output. In a 4:1 MUX, you typically have two select lines (S0 and S1), which together can represent four possible binary combinations (00, 01, 10, 11).

Output (Y): The output line carries the selected input value based on the select lines.

**Synthesis of 4:1 MUX in DC shell**

Commands
```ruby
set target_library <path_of_target_library>
set link library { * <path_of_target_library> }
read_verilog mux_4_1.v
link
compile_ultra
```


Then we view the schematic in design Vision
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4dcfb8e21be314b5bac810d882ce9e101b71e66a/day13/mux_sch_dv.png">

**Gate level Simulation**

Commands
```ruby
iverilog <netlist_file_name> <testbench>
./a.out
gtkwave <vcd_file_name>
```

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4dcfb8e21be314b5bac810d882ce9e101b71e66a/day13/mux_actual.png">

Here we can see that both the pre synthesis and post synthesis have same wave form 

We can see that, (input is 1010)

when select line is 00 output is 0

when select line is 01 output is 1

when select line is 10 output is 0

when select line is 11 output is 1

</details>

<details>
<summary>BabySOC Post Simulation</summary>

We know that BabySOC consists of 3 IP's namely

- RVMYTH
- DAC
- PLL

Out of these 3 only RVMYTH is synthesizable 

Commands for synthesizing
```ruby
set target_library <path_of_target_library>
set link library { * <path_of_target_library> }
read_verilog mythcore_test.v
link
compile_ultra
write -f verilog -output rvmyth_core_test.v
```

The simulation after synthesis

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4dcfb8e21be314b5bac810d882ce9e101b71e66a/day13/gls_rvmyth.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4dcfb8e21be314b5bac810d882ce9e101b71e66a/day13/rvmyth_gls.png">

We can see that the functionality is same as the one compared with pre synthesis. i.e sum of first n natural numbers upto 1000 and then it again decrements in the same way.


**BabySOC post synthesis**

As we know that only rvmyth is synthesizable we synthesize rvmyth and then check the functionality with the .lib of DAC and PLL.

Command for converting .lib to db
```ruby
read_lib <file_name>
write_lib lib_name -f db -o <new_db_file_name>
```

Commands for synthesizing rvmyth_core
```ruby
set target_library <path_of_target_library>
set link library { * <path_of_target_library> }
read_verilog vsdbabysoc.v
link
compile_ultra
```

**Gate level Simulations**

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4dcfb8e21be314b5bac810d882ce9e101b71e66a/day13/gls_command_final.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4dcfb8e21be314b5bac810d882ce9e101b71e66a/day13/gls_final_one.png">




















</details>


# Day-14 Synopsys DC and Timing Analysis

<details>

<Summary> PVT Corners </Summary>

PVT corners, refer to the different combinations of Process, Voltage, and Temperature conditions that integrated circuits may encounter during their operation. Understanding and accounting for PVT corners is crucial in VLSI design because they significantly impact the performance, power consumption, and reliability of electronic devices.

1. **Process Corner**
   
	- *Process Variations* : Semiconductor manufacturing processes are subject to inherent variations. These variations can lead to differences in transistor characteristics, such 	  as threshold voltage, mobility, and oxide thickness. As a result, integrated circuits produced on the same manufacturing line may have slightly different electrical properties.

	- Process Corners: To model these variations, designers define process corners. There are typically three main process corners:

		- Nominal (N): Represents the ideal or typical process conditions.

		- Fast (F): Represents the corner where transistors are faster and typically have lower threshold voltages.

		- Slow (S): Represents the corner where transistors are slower and generally have higher threshold voltages.


 2. **Voltage Corner** 

 	- *Voltage Variations* : Integrated circuits can operate at different supply voltages. Higher supply voltages typically result in faster operation, while lower supply voltages 	  reduce power consumption but may slow down the circuit's performance.

 	- Voltage Corners: Designers consider different voltage corners to account for supply voltage variations. These corners include:

		- Low Voltage (LV): Represents the scenario where the supply voltage is at its lowest allowable level.

		- Nominal Voltage (NV): Represents the standard or nominal supply voltage.

		- High Voltage (HV): Represents the scenario where the supply voltage is at its highest allowable level.


3. **Temperature Corner**

 	- *Temperature Variations* : Integrated circuits can experience variations in temperature during operation. Temperature affects the mobility of electrons and holes in 			  transistors, which in turn affects their performance.

	- *Temperature Corner* : Designers consider different temperature corners to accommodate temperature variations. These corners may include:

		- Low Temperature (LT): Represents the scenario where the temperature is at its lowest expected level.

		- Nominal Temperature (NT): Represents the standard or nominal operating temperature.

		- High Temperature (HT): Represents the scenario where the temperature is at its highest expected level.


4. **Importance of PVT Corner in VLSI**

   	- PVT corner analysis is crucial for ensuring that a VLSI chip operates reliably under different conditions.
   	- It helps identify worst-case scenarios where the chip may fail to meet performance, power, or reliability requirements.
   	- Designers can use PVT corners to optimize their circuits for a balance of performance, power consumption, and reliability.
   	- PVT corner-aware designs are essential for robust and resilient integrated circuits, especially in critical applications like automotive, aerospace, and medical devices.  
</details>

<details>

<Summary>LABS</Summary>

Steps
- Get all the .lib files by cloning https://github.com/Geetima2021/vsdpcvrd.git
- Delete the lines from the .lib with the error stated. (REPEAT THIS FOR ALL THE .LIB)
- After deleting the lines , load LC shell and convert it into .db using the following commands
  ```ruby
  read_lib <library_name>
  write_lib <library_name> -f db -o <name_of_the_db_file>
  ```
- Now generate a constaraint file
  ```ruby
   set_units -time ns
  create_clock -name MYCLK -per 2 [get_pins {pll/CLK}];

  set_clock_latency -source 1 [get_clocks MYCLK]
  set_clock_uncertainty -setup 0.5 [get_clocks MYCLK]; 
  set_clock_uncertainty -hold 0.4 [get_clocks MYCLK]; 

  set_input_delay -max 1 -clock \[get_clocks MYCLK] [all_inputs];
  set_input_delay -min 0.5 -clock \[get_clocks MYCLK] [all_inputs];
  set_output_delay -max 1 -clock \[get_clocks MYCLK] [all_outputs];
  set_output_delay -min 0.5 -clock \[get_clocks MYCLK] [all_outputs];

  set_input_transition -max 0.2 \[all_inputs];
  set_input_transition -min 0.1 \[all_inputs];

  set_max_area  800;

  set_load -max 0.2 \[all_outputs];
  set_load -min 0.1 \[all_outputs];
  ```
- Now set the required db files (sky130.db,avsddac.db,avsdpll.db), read the design , link the library and do compile_ultra
- Commands for implementing this are as follows
  ```ruby
  set target_library { <sky130_PVT_corner> , avsddac.db , avsdpll.db}
  set link_library {* sky130_PVT_corner> , avsddac.db , avsdpll.db}
  read_verilog vsdbabysoc.v
  link
  source <constraints_file_name>
  compile_ultra
  report_qor
  ```
- **Outputs**
  	- 
  
  
  
 

read_verilog vsdbabysoc.v (current_design is clk_gate)
read_file {vsdbabysoc.v avsd_pll_1v8.v avsddac.v mythcore_test.v} -autoread -format verilog -top vsdbabysoc
link
report_global_timing
</details>










 
   

 

















 
 



   

	
  
   	       
   
      
      
           

             
      

 


















