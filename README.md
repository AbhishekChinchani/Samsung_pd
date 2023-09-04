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



<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/de0c4050082b98433594827daa8c1abae0c0e903/snaps/dc_invoke">


 		
  
   	       
   
      
      
           

             
      

 


















