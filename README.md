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

	- For sky130_fd_sc_hd__ff_100C_1v65
	   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_100C_1v65_1.png">
	   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_100C_1v65_2.png">
	
	- For sky130_fd_sc_hd__ff_100C_1v95
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_100C_1v95_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_100C_1v95_2.png">
	
	- For sky130_fd_sc_hd__ff_n40C_1v56
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_n40C_1v56_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_n40C_1v56_2.png">
	
	- For sky130_fd_sc_hd__ff_n40C_1v65
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_n40C_1v65_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_n40C_1v65_2.png">
	
	- For sky130_fd_sc_hd__ff_n40C_1v76
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_n40C_1v76_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ff_n40C_1v76_2.png">
	
	- For sky130_fd_sc_hd__ss_100C_1v40
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_100C_1v40_2.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_100C_1v40_1.png">
	
	- For sky130_fd_sc_hd__ss_100C_1v60
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_100C_1v60.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_100C_1v60_2.png">

	- For sky130_fd_sc_hd__ss_n40C_1v28
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v28_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v28_2.png">
	
	- For sky130_fd_sc_hd__ss_n40C_1v35
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v35_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v35_2.png">
	
	- For sky130_fd_sc_hd__ss_n40C_1v40
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v40_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v40_2.png">

	- For sky130_fd_sc_hd__ss_n40C_1v44
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v44_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v44_2.png">
	
	- For sky130_fd_sc_hd__ss_n40C_1v76
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v76_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/ss_n40C_1v76_2.png">
	
	- For sky130_fd_sc_hd__tt_025C_1v80
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/tt_025C_1v80_1.png">
	  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/27d1798c5fac68f0b8c1c8db089c19b2affc1099/day14/tt_025C_1v80_2.png">
  
  
  
 - Table and Graph for setup

    ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/8c3076d7-7141-47b4-8ac7-eba6bafd29f5)


    ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/e22a229d-4f45-4073-8ca9-be8cdc622fcf)



 - Table and Graph for hold

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/053b4eae-12e4-455e-909f-c2a716b2d3e1)


   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/8634f4e9-c58a-4ac7-ac74-231f928a25ed)


- **Observation**

   Hold violations are more prone in faster cells and setup is more prone in slower cells.

   The worst corner for setup is ss_n40C_1v28 , if this corner is satisfied then all the others will be satisfied automatically.

   The best PVT corner is **ff_n40C_1v76** as it has no setup violation and very minimal hold violation.

  </details>

  # Day 15 - Inception of EDA and PDK

  <details>

  <Summary>Introduction</Summary>
  An integrated circuit (also known as an IC) is a set of electronic circuits on one small flat piece (or "chip") of semiconductor material, usually silicon. An integrated circuit is typically mounted on a printed circuit board 
  (PCB) to create a functional electronic system.

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/7664cd73-461f-44b0-a543-4eb01ea06c16)

  The main components of a chip are as shown below

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/54951b17-adaf-422f-ac1e-0fe19d2a3cc6)

  **DIE**  refers to a specific part of a silicon wafer that contains an individual integrated circuit (IC) or chip.Each silicon wafer is divided into multiple smaller sections, each of which contains a copy of the same integrated 
  circuit design. These smaller sections are called "dies." Each die is essentially an individual chip that can function on its own once it's separated from the wafer.

  **Pads** refer to the external connections or pins on an integrated circuit (IC) that allow it to interface with the outside world. Pads serve as the physical connection points through which electrical signals are input to or output 
   from the IC.Pads play a crucial role in the functionality of an IC. They are the points at which signals, such as data, power, clock, and control signals, are brought into or sent out of the chip.

   Types of pads

   - Input Pads: These are used to receive external signals into the IC. For example, input pads might be used for data inputs from sensors or user interfaces.
   - Output Pads: These are used to send signals generated within the IC to external devices or other parts of a circuit. For instance, output pads might be used to send data to a display or to transmit data to another IC.
   - Power Pads: These pads are used to provide power to the IC. They are typically connected to the power supply voltage (VDD) and ground (GND).
   - Ground Pads: Ground pads are connected to the ground reference voltage (GND) and are essential for proper functioning and noise reduction in the circuit.
   - No-Connect Pads: Some pads may not be connected to anything and are labeled as "no-connect" to avoid unintended connections.

  **Core** refers to a fundamental functional block or module within an integrated circuit (IC) design. Cores are designed to perform specific tasks or functions, and they can be combined with other cores and components to create 
   complex ICs that serve various purposes.

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/84cef53e-da5d-4f9b-bdc3-2b3f2d449226)


  This particular component is housed in a QFN-48 package, which stands for Quad Flat No Leads and has 48 pins. Each of these pins serves as a connection point that interfaces with other components or packages on the design board. The 
  package itself measures 7mm by 7mm in size. At the heart of this package, there is typically a microchip positioned in the center. The pins on the periphery of the package, often referred to as "outbounds," play a crucial role in 
  facilitating the exchange of data between the external world and the chip contained within the package.

  </details>

  <details>

  <Summary>RTL to GDSII </Summary>

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/c6741cb2-33f7-4732-8a8c-04ea932d2db9)

  - **Synthesis**  refers to the process of transforming a high-level hardware description of a digital circuit, often written in a hardware description language (HDL) like VHDL or Verilog, into a netlist representing the logical and 
   physical components that will make up the actual integrated circuit. Synthesis is a crucial step in the VLSI design flow. Standard cells are fundamental building blocks used in this process. They have a regular layout, and each 
   cell is represented in various views or models, including electrical, HDL, and SPICE. Additionally, there are abstract and detailed layout views available for standard cells. These standard cells play a pivotal role in constructing 
   the final layout of the integrated circuit.

   - **Floor Planning** is a crucial early-stage process that involves defining the physical layout and placement of various functional blocks, modules, and components within an integrated circuit (IC). Floor planning is essential for 
    optimizing factors such as chip area, signal routing, power distribution, and thermal management.

		- *Chip Floorplan* : It refers to the specific floorplan designed for an integrated circuit (IC) or semiconductor chip. It is a layout or diagram that details the physical arrangement and placement of various 			   components,functional blocks, and critical elements within the chip's silicon area.

   		- *Macro Floorplan* : A "macro floorplan" is a specific type of floorplan used in semiconductor and integrated circuit (IC) design. In IC design, a macro typically refers to a predefined and pre-characterized 
                   functional block or module that performs a specific function. A macro can be anything from a processor core to a memory block or any other complex building block within an IC.
  
		- *Power Planning* : Power planning in VLSI (Very Large Scale Integration) design is a critical aspect of semiconductor chip design that involves managing and distributing electrical power within an integrated circuit 		   (IC). Effective power planning is essential for achieving reliable and efficient operation while minimizing power consumption.


  - **Placement**  is a crucial step in the physical design process of creating integrated circuits (ICs). It involves determining the optimal location for each logical cell, or standard cell, within the chip's silicon area. Effective 
    placement has a significant impact on factors like performance, power consumption, and chip area utilization. The primary objective of placement is to arrange standard cells in a way that minimizes the total wirelength (the total 
    length of wires connecting the cells), optimizes chip area utilization, and meets various design constraints such as timing, power, and manufacturability.

  - **CTS** stands for "Clock Tree Synthesis." CTS is a crucial step in the physical design process of creating integrated circuits (ICs), and it specifically deals with the generation and optimization of the clock distribution 
    network within the chip. The primary goal of CTS is to ensure that clock signals are distributed efficiently and reliably to all flip-flops and sequential elements, minimizing clock skew and meeting the required timing 
    constraints.Clock Tree Synthesis is a critical step in VLSI design, as clock distribution plays a significant role in the overall performance, power consumption, and reliability of integrated circuits. Advanced algorithms and 
    tools are used to automate and optimize the CTS process for complex and high-performance ICs.

  - **Routing** in VLSI (Very Large Scale Integration) design is a fundamental step in the physical design process of creating integrated circuits (ICs). It involves the generation of physical connections (metal traces or wires) 
    between the various components and logic elements on the chip, ensuring that data signals, control signals, and power are routed efficiently and meet design constraints. Routing plays a critical role in determining the 
    performance, power consumption, and overall functionality of the IC.

  - **Sign Off** refers to the final stage of the design process before the design is sent for fabrication (manufacturing). Sign-off involves a comprehensive set of checks, analyses, and validations to ensure that the integrated 
    circuit (IC) design meets all of the necessary criteria, constraints, and specifications before it is sent to the foundry for manufacturing. This stage is critical because any design errors or issues not caught at this point can       in costly and time-consuming problems later in the manufacturing process or after the ICs are in operation.

  - **Physical Verification** It involves a series of checks and analyses to verify that the physical layout of the integrated circuit (IC) adheres to various design rules, constraints, and manufacturing requirements. The goal of 
     physical verification is to ensure the manufacturability, functionality, and reliability of the IC design before it is sent for fabrication. It involves
          -
      1. *Design Rule Checking (DRC)*:

	  - Geometry Checks: DRC verifies that the layout adheres to the design rules specified by the foundry. These rules include minimum feature sizes, spacing requirements, width and spacing of metal layers, and other 			    geometric constraints.
        
	  - Layer-Specific Rules: Different layers in the IC have specific design rules. DRC checks for compliance on all metal, polysilicon, diffusion, and other layers.
  
      2. *Electrical Rule Checking (ERC)*:


	   - Electrical Connectivity: ERC ensures that there are no electrical shorts or opens in the layout. It verifies that the actual connections in the layout match the intended connectivity in the schematic.

	   - Antenna Checking: ERC also checks for charge buildup issues, known as antenna effects, that can result from the deposition and etching processes during manufacturing.		

       3. *Layout Versus Schematic (LVS) Verification*:

	   - Netlist Consistency: LVS compares the layout netlist with the schematic netlist to ensure that they are equivalent. Any mismatches or discrepancies are flagged for resolution.

	   - Parasitic Extraction: Parasitic elements, such as capacitance and resistance, are extracted from the layout and compared with the schematic to verify electrical equivalence.



  </details>

  <details>

  <summary>OpenLane Flow</summary>

  OpenLane is an open-source digital ASIC (Application-Specific Integrated Circuit) design flow and toolchain developed by Google and the Skywater Technology Foundry. It provides a 
  complete, automated environment for designing and manufacturing digital chips, from RTL (Register-Transfer Level) design to GDSII (Graphic Data System II) tape-out. OpenLane is built 
  upon various open-source tools and methodologies and is intended to simplify and democratize the ASIC design process.

  1. Synthesis Exploration:

	- Synthesis exploration is a utility used to generate reports that display the design's delay and area characteristics.
 
 	- It helps identify the most suitable design strategy to proceed with by analyzing these reports.
		
		
  2. Design for Testability (DFT):

	- After synthesis, DFT steps prepare the design for testing before fabrication (optional).These steps include:

		- Scan Insertion

   		- Automatic Test Pattern Generation (ATPG)

		- Test Patterns Compaction
  
  		- Fault Coverage Analysis

  3. Physical Implementation (Automated PnR):

	- Physical implementation, often referred to as Automated Place and Route (PnR), is conducted using open-source tools like OpenRoad.It encompasses various steps:

		- Floor and Power Planning

		- End Decoupling Capacitors and Tap Cells Insertion

		- Placement (Global and Detailed)

		- Post Placement Optimization

		- Clock Tree Synthesis (CTS)

		- Routing (Global and Detailed)

		- Logic Equivalent Check (LEC) to ensure functionality consistency after netlist modifications.






  4. Dealing with Antenna Rules Violations: A specific phase during physical implementation addresses Antenna Rules Violations.
     It involves inserting Antenna Diodes to mitigate issues caused by long metal wire segments acting as antennas, which can accumulate charge and potentially damage transistor gates 
     during fabrication.
     Solutions include bridging and adding antenna diode cells.

	- Static Timing Analysis (STA):STA involves several steps, including RC extraction (from .def to .spef format) and the use of tools like OpenSTA (within OpenROAD).
	  It generates timing reports to check for violations in timing paths and ensure that the design meets its timing constraints.
          Physical Verification (DRC & LVS):

	- Magic is utilized for Design Rule Checking (DRC) and SPICE Extraction from Layout.Netgen, along with Magic, is employed for Layout vs. Schematic (LVS) checks, comparing the 
          extracted SPICE data from Magic with the Verilog netlist.
  
  </details>

  <details>

  <summary>Labs</summary>

  **Skywater130 PDK Files**

  The skywater130 PDK contains 3 directories:

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/66593625-d29c-4047-afcc-f26bba6557f0)

  1. skywater-pdk : It contains all pdk related files (.lib,.lef)
  2. open-pdks : It contains scripts that bridge the compatibility gap between closed-source and open-source PDKs for Electronic Design Automation (EDA) tools.
  3. sky130A : It contains open source compatible EDA files.
 
  The commands for invoking Openlane
  ```ruby
  docker
  flow.tcl -interactive
  ```

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/fa0d814b-c91f-496d-b655-991aa2716c34)

  Importing the package

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/e17158f9-5fc4-4818-811d-6cfee9ad4687)

  Preparing Design:

  The "prep" phase sets up the file structure for your design within OpenLane.


  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/e8be61d9-2fe8-4fe7-8d77-f9a6475abe38)


  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/1e22d5c2-0f2c-4170-ba0c-32ad42957568)

  Inside a runs folder a folder is created with date is created

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/26dffd53-c19e-4146-a161-0109412d9152)

  *Config file in the new directory shows the default parameters taken by the run*.

  After running the command *run_synthesis*

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/5fad7610-5f25-4793-91d3-6a7ac09ed0da)

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/9529e973-a787-4bf3-a14e-7646612d6380)

  The number of d flip flops = 1613

  Total Number of cells = 14876

  D flip flop ratio = 1613/14876 = 0.108429

  In percentage => 10.8429%

  </details>



# Day 16 Good Floorplan and Bad Floorplan

<details>

 <summary>Utillization Factor and aspect ratio</summary>

 Consider the below circuit 

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/777642d2-cc5f-46b6-b60b-0c07dce082fd)

 This circuit consits of 2 Flipflops , 1 And gate and 1 OR gate

 Now convert this design into physical implementation 

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/b80a6896-c8a4-4179-8d1c-af53d414d323)


 To define the height and width of the core and die we need to know the dimensions of standard cells

 Lets consider the area of standard cell as 1 sq unit and area of the flip flop cell also as 1 sq unit.

 Now we remove the wires and do a rough calculation of min area occupied by netlist.

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/fbdfe6e6-3486-4edc-918f-9a420b0cf5ba)

 The area is **4 sq unit**

 **Utilization Factor** : It is defined as the ratio of area occupied by netlist to the total area of core 

 Utilization Factor = area occupied by netlist / total area of core

 Consider the below circuit

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/e2e24a6e-7329-4717-be04-e895bb7162d4)

 In this the utilization factor is 1 (4/4)

 **Aspect Ratio** : It is defined by the ratio of height and width of the core.

 Aspect Ratio = Height/Width

 In this the aspect ratio is 1 (2/2)

</details>

<details>

<summary>Concept of preplaced cells</summary>

Consider the below circuit 

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/64c7a60d-8a79-4a35-a1dc-ead7b2e7c7c2)

These circuits can be split into blocks as shown in the figure

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/ff41ea26-6a12-4559-90c5-5637867d0590)

These blocks can be considered as blackboxes with extended pins , They are known as Ip's and they can be used multiple times in the design

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/fd21405e-61d6-4fae-9609-506862a705bb)


These are example of IP's 

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/db44fc1d-a376-4fb3-b1e4-391138b1cd2f)

</details>

<details>

 <summary> Decoupling Capacitors</summary>

 Consider a complex circuit as shown in the figure

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/84f3cbdf-2190-43f0-813a-a7e7b39404e2)

 - During the switching case the circuit requires high peak current.
 - But there will be some voltage drop beacuse of R and L , as a reult the voltage at node A will be Vdd'.
 - Now if this drop is higher then the noise margin then the Voltage goes to undefined state i.e it can act as 1 or 0.
 - Referring to the noise margin graph, there are three regions: logic 0, undefined, and logic 1. If Vdd falls between Vil and Vih, it is considered undefined, posing a risk.
 - So to overcome this problem we use decoupling capacitor

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/1d07b57f-5471-4ebf-a2a1-a9acdfcb8198)

- Decoupling Capacitor provide the require amount of the current to the nodes so that they dont do into undefined state
- They are placed parallel to circuit
- These capacitors are strategically placed between blocks to ensure that all blocks receive the necessary power supply when switching occurs.

After placing the decoupling capacitances

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/c8787058-1b73-4d9a-b580-30621415ef79)



</details>

<details>

 <summary> Power planning </summary>

 Consider the below case

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/9888ed9e-3779-466c-89a7-3c3bfa8cf08d)

 - Now the output at the driver is high , this signal should be sent to another driver.
 - This is a 16 bit bus which is again connected to an inverter
 - So all the logic 1 bits should eventually discharge and all logic 0 should charge .
 - During Discharging all the logic 1 discharge at the same time reulting in bounce , if this bounce exceeds the noise margin then that bit enters the undefined state
 - During charging phase all the logic 0 should be charged at same causing Voltage Droop
 - So to overcome this we use multiple power supplies
 - These multiple power supplies will be directed to the nearest blocks, ensuring that each block receives a reliable power supply without any possibility of missing out.

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/8fb9c928-cf8a-4d0b-9207-46659fbedb86)

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/791cbdbe-2cb0-421f-b750-146741e4f115)


</details>

<details>

 <summary>Pin placement and logical cell placement blockage </summary>

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/0a471798-c601-4274-997a-9f5c4fa0f16b)

 This has 4 input and 4 output pins, 2 input clock pins and 1 output clock pins

 pin placement 

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/f1c234dc-6f48-43f5-8924-4a81bf4213cd)

 - These pins are placed in random order
 - Clock pins are larger because they need to send the signals to all flip flops



 



</details>

<details>

 <summary> Floorplan using Openlane</summary>

 Running the floorplan using the command *run_floorplan*
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/run_floorplan_2.png">

 The values chosen are chosen based on set of prioprities, the least pripriority is for floorplan.tcl then config.tcl in designs and the highest is for sky130A_sky130_fd_sc_hd.tcl 

 1. floorplan.tcl
  
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/floorplan_tcl_1.png">

 2. config.tcl in design picorv32a folder

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/design_tcl_3.png">

 3. sky130A_sky130_fd_sc_hd.tcl in picorv32a directory

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/sky-130_tcl_4.png">

 The values chosen in our case are *utilization ratio 35* , *vertical metal layer as 2* , *horizonatal metal layer as 3*

 The reult is stored as .def file

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/def_result_6.png">

 command to invoke magic is
 ```ruby
 magic -T <path_of_tech_file> lef read <path_of_lef_file> def read <path_of_def_file>
 ```

 The floorplan in magic is as follows

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/After_running_magic_7.png">

 As the mode is set to 1 all the pins are equidistant

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/equidistant_8.png">

 We can select and check its metal layer by just selecting it in magic and giving what command in tkkon2.3

 1. Horizontal pin
    
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/metal3_layer_what_9.png">

 2. Vertical pin

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/metal2_layer_what_10.png">

 At the bottom left we can see that all the standard cells are present

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/standard_cells_11.png">

</details>

<details>

 <summary>Netlist Binding and intial place design</summary>

 - First the circuit is converted into the netlist as shown in the figure

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/07e376ac-7c61-44d5-a0c3-0e821ed4e47e)

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/68406be7-c046-4458-b8cc-b39f8b594840)

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/9428d74c-01a6-4bec-9683-5adbd14ec30d)

- A Library consist of different flavours of the gates as shown in the figure

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/02ff2978-901a-4aa9-a0bc-cf5c82808b45)

- For placement we need floorplan , netlist , physical view of lgic gates

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/5468da51-5ee4-4ce9-a972-8de75963a659)




</details>

<details>

 <summary>Final placement optimization </summary>

 Consider the initial placement as shown in the figure

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/ad7b63d5-cc94-4d30-87ee-9475b43cb31d)

 - At this stage we estimate wire length and capacitance and based on that we insert repetators
 - Repeater insertion involves placing buffers along the signal path to reinforce the signal and duplicate it. It's worth noting that adding more repeaters consumes additional chip area.
 - Consider the above circuit , Lets estimate the wire length between Din1 and Dout1, we see that there are not that far enough so they can be directly connected without any repeater 
   buffers
 - Consider the case between Din2 and Dout2 , Din2 is placed far enought from FF1 so we nees to insert a repeater buffer.
 - While the connection between FF1 (yellow) and Din 1 is acceptable, there's a challenge when crossing other flip-flops due to excessive distance. To address this, buffers are 
   introduced, and to avoid congestion, they are placed on a separate layer.

  The optimized placement after placing required buffers or repeaters is as shown in the figure

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/878441b5-f8ea-4913-ad37-f77bff181e3e)


 


</details>

<details>

<summary>Placement Labs</summary>

To run tbe placement we use the command *run_placement*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/placement_12.png">

The placement in the magic is as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/6ec05f96bc0b992cb54ddf15ac3cb199f2b60901/Day17/placement_sch_13.png">

The placement of different cells can be seen in the below image 

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/20577a88-cf3f-44f4-a500-7670bbb238dd)




 
</details>

<details>

 <summary>Standard Cell Design Flow</summary>

 The standard cell design flow and characterization process are essential aspects of designing integrated circuits (ICs) using CMOS technology.

 **Inputs**

 - *Process Design Kits* : Process Design Kits (PDKs) are essential tools used in semiconductor manufacturing and integrated circuit (IC) design. They provide a comprehensive set of information, data, and files necessary for designing and simulating semiconductor devices and ICs using a specific semiconductor manufacturing process technology.
 - *DRC and LVS* : *DRC* stands for "Design Rule Checking," and it is a critical step in the semiconductor and integrated circuit (IC) design and manufacturing process. DRC is a set of automated checks that ensure that the layout of an IC adheres to the design rules specified by the semiconductor foundry or manufacturing facility. These design rules are essential to ensure that the resulting IC can be manufactured reliably and accurately. **LVS** is a process that verifies the accuracy and consistency between the physical layout of an IC (the layout design) and its logical schematic or netlist.
 - *SPICE* : *SPICE* models, often simply referred to as "SPICE," are essential tools used in electronic circuit design and simulation. SPICE stands for "Simulation Program with Integrated Circuit Emphasis." It is a computer program used to model and simulate the behavior of electronic circuits. SPICE models provide a way to mathematically describe and analyze the performance of electronic components and circuits.

**Design Steps**
- *Circuit Design* :n this phase, engineers create the logical schematic representation of the digital circuit. They specify the functionality, connectivity, and desired performance parameters.It refers to the process of creating and optimizing electronic circuits on a microchip or integrated circuit (IC) at a very high level of complexity. VLSI design is a critical aspect of semiconductor engineering and involves the creation of complex digital and analog circuits that can include millions or even billions of transistors on a single chip.
  
- *Layout Design* : After the logical design, engineers create a physical layout of the circuit, adhering to DRC and LVS rules. This involves placing transistors and interconnecting them while considering factors like area, power, and signal integrity.It refers to the process of creating the physical representation of an IC on a semiconductor wafer. This physical representation includes the placement and interconnection of various components, transistors, wires, and other elements that make up the IC.
  
- Characterization*: Characterization is the process of quantifying how the standard cells behave under various conditions. This step ensures that the cells meet timing, power, and noise requirements. GUNA is a software tool used for this purpose.


**Outputs**
- CDL (Circuit Description Language): CDL files describe the logical behavior of standard cells, including their connectivity, functionality, and timing information.
- GDSII (Graphic Database System II): GDSII is a file format used to represent the final layout of the IC in a binary form. It is used for chip fabrication.
- LEF (Library Exchange Format): LEF files provide information about the physical properties of the standard cells, which is necessary for placement and routing in the IC design process.
- Timing, Noise, Power Libraries: These libraries store information on the timing characteristics, noise behavior, and power consumption of standard cells. They are essential for synthesis and optimization tools.
- Extracted Spice Netlist (.cir): This is a SPICE-compatible netlist that includes parasitic elements extracted from the layout. It is used for accurate simulation of the designed circuit.


</details>

<details>

 <summary>Standard Cell Characterization</summary>

 - *Link Model File of CMOS* : This step involves linking the Liberty file, which defines the properties, timing, and other characteristics of the CMOS process technology.

 - *Specify Process Corner(s)*: Process corners represent different manufacturing variations and operating conditions (e.g., fast, slow, nominal). The characterization process evaluates 
   the standard cell's behavior across these corners.

 - *Specify Cell Delay and Slew Thresholds*: These thresholds determine how the cell's timing characteristics are characterized, helping capture both the rising and falling edges of 
   signals.

 - *Specify Timing and Power Tables*: Timing tables describe the cell's propagation delay, setup time, hold time, and other timing parameters under different conditions. Power tables 
   specify the cell's power consumption.

 - *Read Parasitic Extracted Netlist* : The parasitic elements extracted from the layout of the standard cell are incorporated into the characterization process to account for their 
    impact on signal delays and power consumption.

 - *Apply Input or Stimulus*: Simulated inputs or stimuli are applied to the standard cell to evaluate its response under various conditions.

 - *Provide Necessary Simulation Commands*: Simulation commands are used to run simulations on the standard cell to gather data on its performance.
</details>





# Day-17 Standard Cell Characterizations

<details>

 <summary>IO placer revised</summary>

 We can change the allignment of the Input/output pins by the changing the FP_IO_MODE. By Default it is set to 1. This can be changed by using the below command
 ```ruby
set ::env(FP_IO_MODE) 2
```

Before changing the mode the layout in magic

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/b3ac947e-d901-45d4-b4c2-ec1c63b18510)

After changing the mode 2

![mode_3](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/ae1ce9c5-b361-4eab-8467-0dca8d6feb86)





</details>

<details>

 <summary>Spice Simulation for CMOS Inverter</summary>

 - The First task is to create a SPICE Deck file which contains the connectivity information of netlist ,inputs provided, tap points to view outputs.The SPICE is created by defining component connectivity, component values, identifying the nodes and naming them.
 - A substrate is a component or pin that requires connectivity information and can be used to adjust the threshold voltages of NMOS and PMOS transistors. The orientation of the substrate pin differs between NMOS and PMOS symbols. Determining the value of output load capacitance involves extensive computational analysis.
 - To define the component values for PMOS and NMOS, specifically the W/L ratios (e.g., 0.375μ/0.25μ), it is often assumed that they share the same values, even though PMOS should ideally be twice the size of NMOS. The specified output capacitance is typically 10fF, and the applied gate voltage is commonly a multiple of the channel length, such as 2.5V. A node is identified when a component is positioned between two nodes.

The defination of components f an CMOS Inverter is as below
```ruby
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u W=0.25u
cload out 0 10f
Vdd vdd 0 2.5
Vin in 0 2.5
```
-  M1 component is the PMOS whose drain is connected to OUT , Gate is connected to IN , Substrate and Source are connected to vdd.It also contains the W/L ratio.
-  M2 component is the NMOS whose drain is connected to OUT , Gate is connected to IN , Substrate and Source are connected to 0.It also contains the W/L ratio.
- The load capacitance is connected between out port and ground and the value is 10fF. Similarly, the supply voltages are connected between groud and respective nodes and the voltage is 2.5V.

The Simulation commands are as follows
```ruby
.op
.dc Vin 0 2.5 0.05
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```
This command implies that gate voltage is varied from 0 to 2.5V in steps of 0.05V. This is done to note the output characteristics with respect to input voltage. The model file must be described as follows that contains the complete model description of NMOS and PMOS of the length.

The layout of the CMOS inverter is as follows

![layout_3](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/7f2d84c4-636a-4732-aa1d-4fd8e3c206b1)

Now to create .spice we use the commands as shown in the figure

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/extract_all_tkcon_7.png">

After executing the above command .ext is created as shown in the below figure

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/extract_all_tkcon_list_8.png">

Now type *ext2spice cthresh 0 nthresh 0* in tkcon

Then give *ext2spice*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/ext2spice_command.png">

This creates a .spice file

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/ext2spice_spice_create_10.png">


 
</details>

<details>

 <summary>16 Mask CMOS Fabricaion</summary>

 Complementary Metal-Oxide-Semiconductor (CMOS) technology is a widely used fabrication process in the semiconductor industry for building integrated circuits (ICs) and microchips. CMOS technology offers advantages such as low power consumption, high noise immunity, and compatibility with digital logic circuits. The term "16-mask CMOS fabrication" likely refers to a specific CMOS process node with 16 masking layers involved in the manufacturing process.

 The 16 mask CMOS fabrication steps are as follows

 - *Substrate Preparation*: Begin with a silicon wafer as the starting material. The wafer is cleaned and prepared for further processing.

 - *Gate Oxide Formation (Mask 1)*: A thin layer of silicon dioxide (SiO2) is grown or deposited on the silicon wafer to serve as the gate dielectric.

 - *Polysilicon Gate Formation (Mask 2)*: Polysilicon is deposited and patterned to create the gate electrodes for both NMOS and PMOS transistors.

- *N-Well and P-Well Formation (Mask 3)*: To create regions for NMOS and PMOS transistors, n-type and p-type ion implantation processes are used.

- *Source and Drain Formation (Masks 4 and 5)*: Ion implantation and subsequent annealing processes are used to define the source and drain regions of transistors.

- *Gate Spacer and Silicidation (Masks 6 and 7)*: Insulating spacers are added to the gate structures, and a metal silicide is formed on the source and drain regions to lower contact resistance.

- *Interlayer Dielectric (ILD) Deposition (Mask 8)*: A layer of insulating material, often silicon dioxide, is deposited and planarized to create a flat surface for metal interconnects.

- *Contact and Via Formation (Masks 9 and 10)*: Contact holes are etched through the ILD to connect the metal interconnects to the underlying transistor nodes.

- *Metal Layer 1 (Mask 11)*: Metal lines and interconnects are formed to connect various parts of the circuit.

- *Intermetal Dielectric (IMD) Deposition (Mask 12)*: Another insulating layer is deposited to separate metal layers and provide isolation.

- *Metal Layer 2 (Mask 13)*: Additional metal interconnect layers may be added if necessary.

- *Passivation Layer (Mask 14)*: A protective layer is deposited to safeguard the underlying layers and provide electrical insulation.

- *Pad Opening (Mask 15)*: Openings are created in the passivation layer for wire bonding or solder bump connections.

- *Testing and Packaging (Mask 16)*: The chips are tested for functionality and performance, and then packaged for final use.

Each of these steps involves a specific mask that defines the pattern and location of features on the silicon wafer. The number of masks used can vary depending on the complexity of the integrated circuit design and the specific technology node being employed. As technology nodes advance, more masks may be required to achieve smaller feature sizes and higher levels of integration.

**CMOS Inverter layout in Magic**

When a poly crosses n-diffusion it is NMOS

In Magic if we select that and give *what* in tkcon window we get

![NMOS_$](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/9f750e25-60d8-4890-a2f4-748591d5b694)

When a poly crosses n-diffusion it is PMOS

In Magic if we select that and give *what* in tkcon window we get

![PMOS_5](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/683772b7-59de-46a0-9cd4-bf23a3c6b224)

The connection of Y with the drain of PMOS and NMOS is as shown in the figure

![OUTPUT_Drain_6](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/2c668534-7550-44b3-b7c5-02bff0972583)

The other connection of Source of PMOS and Source of NMOS are as follows

![PMOS_SOURCE_GND_7](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/5c9220ca-170d-4199-b837-116deba902bc)

![NMOS_VDD_8](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/b910a20e-c4d8-42e6-a368-09f59b284bf5)

When we delete some layers we get drc errors

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/after_deleting_inv.png">

The errors in INV are as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/The_errors_in_inv.png">


These can be rectified by adding the suitable metal layers

![layout_3](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/7f2d84c4-636a-4732-aa1d-4fd8e3c206b1)


</details>
<details>

<summary>Labs on DRC</summary>
First we need to clone the open_pdks.git from RTimothyEdwards

These are list of various *.mags* in the directory

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/mag_files_list_12.png">

The met3.mag is as shown below

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/met_3_13.png">

Now we see that rule 3.4 is not the visible one but we can visualize it as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/box_info_met3_2.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/box_info_met3_1.png">



![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/26e31234-281a-4168-a4fb-60042f8219f0)

Now we *load poly*

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/6b469407-3dab-4f81-92d6-c87c4cd248cf)

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/poly_viol_1.png">

These violations can be rectified by editing the .tech files drc rules

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/10320969-c27d-401f-b587-049e78c25b02)


![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/134110dc-98a0-448e-9695-9e252bb5d815)


<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day17_layout/poly_viol_crct_1.png">

The other violations and their corrections are as follows

- First we need to copy the 3 poly metal and paste it into 2 different places and add pmos and nmos substrate and contact. This is to fix the issue with poly resistor spacing to diff and tap.Then we edit the .tech files to rectify this.

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/4d6f8c42-1c4d-44f6-8492-b70f6aa17f50)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/74d195c3-8837-4c79-99be-2f40f9454a92)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/190b4a34-ebec-48af-b66c-03fe4b4bac75)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/6017cc26-1b06-4e5f-8769-28c973efec5e)

- Second one is describing DRC errors as geometrical construct
  
![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/ffb0eeba-8bcc-4e55-8473-0738462b0c35)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/2d163133-cb6b-4971-be5c-a47a009f61db)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/5b0c18f6-5a47-413e-a580-9233f5413e2f)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/ca2cefa6-5ee0-4d6d-9190-41c3a67505aa)

- Shrinking the Nwell to fix the NMOS 6 drc violation

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/dbd6355e-2313-498b-b3f3-5c19ecedc5a2)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/dbe090a2-69ad-44f0-964a-41b67ccd5114)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/eab2dbad-3ef3-4c9e-b3f8-2af0ddf57931)

![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/b9d72959-d4bf-453e-8d0e-ef7ce5c1cb3e)






















 
</details>

# Day-18 Pre timing Analysis and Importance of good clock tree

<details>

 <summary>Steps to convert Grid into track info</summary>

 **LIBRARY EXCHANGE FORMAT**

 - A "library exchange format" typically refers to a standardized format for sharing or exchanging information about libraries.
 - LEF is a standard file format used for exchanging library information between various Electronic Design Automation (EDA) tools and semiconductor foundries.
 - These libraries contain essential information about the components that make up integrated circuits, such as logic gates, standard cells, and other design elements.
 - LEF files describe the characteristics of individual cells or components within a semiconductor library.
 - LEF files define the pins of each cell. This includes pin names, directions (input, output, or bidirectional), layers they connect to, and other relevant information.
 - Here we are converting .mag files of inverter to .lef .

   The track info detail is as follows
   
   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b380cee4bd1280d5fd58e7f58727ff5d19326b96/Day18/track_info_4.png">

   We set the grid by using keyword G

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/command_G_1.png">

   Now we set the Grid using the command
   ```ruby
   grid 0.46um 0.34um 0.23um 0.17um
   ```

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/grid_command_2.png">

   - Rule 1 : Input and output port should lie on the intersection of horizontal and vertical track
  
   - Rule 2 : The width of a standard cell should be odd multiple of the horizontal track pitch

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/grid_command_rule1_3.png">

   Here we can see that the width is 3 times the horizontal track pitch.

   
   
   
   
</details>

<details>

 <summary>Steps to convert magic layout to lef</summary>

 First save the layout with our name *sky130_inv_abhishek*

 Then use *lef_write* command This creates a .lef file

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/List_of_vsdstdcell_put_before_6.png">

 The lef file is as follows

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/lef_file_with_name_6.png.png">

</details>

<details>

 <summary>Introduction to timing libs and steps to include lef cell</summary>

 ```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
cp sky130A_vsdinv.lef /home/nur.nazahah.mohd.amri/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/libs
cp sky130_fd_sc_hd__* ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/
vim config.tcl
```

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/Modification_config_7.png">

run_synthesis

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/image_our_inverter_8.png">

We can see that the cell of our name is getting used

</details>

<details>

 <summary>Introduction to Delay Table</summary>

 - Clock gating is a power-saving technique used in digital integrated circuits, particularly in modern VLSI (Very Large Scale Integration) designs. It involves controlling when and how the clock signal is supplied to specific sections or components of a digital circuit. The primary goal of clock gating is to reduce dynamic power consumption by enabling or disabling the clock signal to certain parts of the circuit when they are not actively in use.The example of clock gating can be seen in the below image

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/325c8ee6-a985-45e7-a6e9-0e88b60d7c87)

 - We need to look into the timing characteristics of the buffer, in the case where we want to swap out the buffer for a gate.

 - For each level of buffering, we should have an identical buffer being used, and each node should be driving the same node.

 - Keep in mind that the load at the output will be varying, and since the load of one buffer is varying, the input transition of the following buffer will also vary.

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/8313bde1-65eb-4c5c-9550-9adf51d5cec7)

 - The example of delay table is as follows

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/e1c12dbf-9efb-49b0-b90e-78c1d95c2845)



</details>

<details>

 <summary>Delay Tables</summary>

 - Each type of cell will be having its own individual delay table, as the internal pmos and nmos width/length ratio gets varied, the resistance changes, then RC constant gets varied as 
  well, meaning the delay of each cell gets varied.
 - The values of delay which are not available in the table are extrapolated based on the given data.
 - If the Starting delay is 40 ps with C load as 50 pF the value will be between x9 and x10. As shown in the figure

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/b4572dcc-37b4-4139-a313-a555ce4c8741)

 - The observations of the delay table are as shown in the figure

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/798ba80f-e1df-4a64-91ee-987376266c15)

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/352ddee1-691d-4724-9e7e-f2119fd8e20e)

 
</details>

<Details>

 <summary>Steps to configure synthesis settings to fix slack and include vsdinv</summary>

 The various configuration of Synth are as follows
 
 - SYNTH_STRATEGY: control the area and timing
 - SYNTH_SIZING: control in cell sizing instead of buffering
 - SYNTH_BUFFERING: control if we want to buffer high fanout net
 - SYNTH_DRIVING_CELL: ensure more drive strength cell to drive input

In openlane 

```ruby
echo $::env(SYNTH_STRATEGY)
set ::env(SYNTH_STRATEGY) "DELAY 0"
echo $::env(SYNTH_STRATEGY)
echo $::env(SYNTH_BUFFERING)
echo $::env(SYNTH_SIZING)
set ::env(SYNTH_SIZING) 1
echo $::env(SYNTH_SIZING)
echo $::env(SYNTH_DRIVING_CELL)
```

- With SYNTH_STRATEGY of Delay 0, the tool will focus more on optimizing/minimizing the delay, index can be 0 to 3 where 3 is the most optimized for timing (sacrificing more area).
- SYNTH_SIZING of 1 will enable cell sizing where cell will be upsize or downsized as needed to meet timing.

  
After modifying the configuration when we give *run_synthesis*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/After_setting_env_10.png">

When we give run_floorplan we get a error of macro placement so we need to comment the lines from flooplan.tcl

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/Changing_floorplan_tcl_9.png">

Then when we run_floorplan it works then we need to give *run_placement*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/placement_11.png">

The placement in magic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/placement_image_12.png">

The cell with my name is as shown below

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/In_placement_cellname_Abhishek_16.png">

</Details>

<details>

 <summary>Setup Time analsysis and flop setup time</summary>

 - Setup time is a critical timing parameter that relates to the proper operation of flip-flops, latches, and other sequential elements within digital circuits.
 - Setup time is defined as the minimum amount of time that data must be stable at the input of a flip-flop or latch before the clock edge arrives for the data to be reliably captured 
   and stored.

 - Here we assume that the clock period is T and combinational delay is o , so o < T

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/ff2d86e0-f202-4ced-a233-2004aa3305d9)

- But actually it should be less than o < (T-S) , where S is the setup time

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/9dcd506b-70ae-4eb8-a4fd-f9bb030ffaef)

</details>

<details>

 <summary>Clock Jitter and Uncertainity</summary>

 - Clock jitter is a phenomenon in electronics and digital systems that refers to the variation in the timing of a clock signal from its ideal, periodic timing.
 - Jitter can occur for various reasons, and it is a key concern in applications where precise timing is critical, such as high-speed digital communication, signal processing, and high-performance computing.
 - Consider the below example

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/a5b6df4b-b3d5-4d68-8476-97c576c623b5)

- Here the clock is expected to reach the clock pin at exactly 0s or at Ts, but in real scenarios, the clock signal may not be able to reach at the exact moment, as the clock source generation may have its own built-in variation.
- The combinational delay will become more stringent as a result. Thus we change our combinational delay to factor in the uncertainty factor from the jitter.

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/2874176a-5241-441c-a267-845fa08e1751)


</details>

<details>

 <summary>Steps to configure OpenSTA</summary>

 - First we need to write a pre_sta.conf file

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/pre_sta_conf_18.png">

 - Then we need to run *sta pre_sta.conf*

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/After_sta_pre_conf18.png">
   
</details>

<details>

 <summary>Steps to optimize synthesis </summary>

 In openlane 
 ```ruby
 cd ~/Desktop/work/tools/openlane_working_dir/openlane
 echo $::env(SYNTH_MAX_FANOUT)
 set ::env(SYNTH_MAX_FANOUT) 4
```

Then we need to give the below commands
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
report_net -connections _18242_                           
replace_cell _41568_ sky130_fd_sc_hd__dfxtp_4             (Pick the highest fanout, cap, slew and replace the worst violations of the cell by increasing drive strength --> upsize cell from 2 to 4)
report_checks -fields {net cap dlew input pins} -digits 4
report_tns
report_wns
```
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_18242_20.png">

 Here we can see the delay for the below cell is very high 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_18242_Violated_image_21.png">

 After replacing the cell and reducing the fanout the delay got reduced , slack also got reduced

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_22.png">

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_23.png">

</details>

<details>

 <summary>Clock Tree Synthesis TritconCTS and signal integrity</summary>

 **Labs to run CTS using tritcon**

 In STA use the below command 
 ```ruby
write_verilog ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/crct2/results/synthesis/picorv32a.synthesis.v
```
Here we can see that when we see that the picorv32a is modified at the time of execution

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_25_write_verilog.png">

Then we need to use the below commands in openlane 

```ruby
run_floorplan
run_placement
run_cts
```

Here we can see that cts output files are generated

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_27_run_cts.png">

**Verifying the CTS design**

Use the below commands in openlane 

```ruby
echo $::env(LIB_TYPICAL)
echo $::env(CURRENT_DEF)
echo $::env(CTS_MAX_CAP)
echo $::env(CTS_CLK_BUFFER_LIST)
echo $::env(CTS_ROOT_BUFFER)
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_28_verify_CTS.png">

</details>

<details>

 <summary>Timing Analysis with real clocks</summary>

 **Steps to analyze timing with real clock**

 Running these commands in openlane
 ```ruby
openroad                                                                                                       
read_lef designs/picorv32a/runs/13-01_14-09/tmp/merged.lef
read_def designs/picorv32a/runs/13-01_14-09/results/cts/picorv32a.cts.def
write_db pico_cts.db
read_db pico_cts.db
read_verilog designs/picorv32a/runs/crct2/results/synthesis/picorv32a.synthesis_cts.v
read_liberty -max $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read_liberty -min $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
set_propagated_clock [all_clocks]
read_sdc designs/picorv32a/src/my_base.sdc
report_checks -path_delay min_max -format full_clock_expanded -digits 4
```
These are the outputs of the above commands

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_29_commands_openlane.png">

We can see that min is met

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_30_min_type_met.png">

Max is violating 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_31_max_type_viol.png">

**Steps to execute STA with right timing library**

In order to meet the max slack we follow the below commands

```ruby
exit        (Exit openroad)
openroad
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -fields {slew trans net cap input pin} -format full_clock_expanded
echo $::env(CTS_CLK_BUFFER_LIST)
```

After report checks we can see that both min and max are met

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_33_max_met.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_34_min_met.png">

**Steps to observe impact of bigger CTS buffers on setup and hold timing**

First we nee to run these in openlane, Here we are changing current def to placement def

```ruby
exit 
echo $::env(CTS_CLK_BUFFER_LIST)
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]
echo $::env(CURRENT_DEF)
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/placement/picorv32a.placement.def
run_cts
```
The output of the above command is as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_35_impact_buf1.png">

In openlane we need to give these commands to see the impact of big buffers, Here we are just checking timing by loading def , lef and cts.v

```ruby
openroad
read_lef /openLANE_flow/designs/picorv32a/runs/13-01_14-09/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/cts/picorv32a.cts.def
write_db pico_cts1.db
read_db pico_cts1.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -fields {slew trans net cap input pin} -format full_clock_expanded 
```

We can see that max slack got improved from 5.10 to 5.18

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/761107244e787fc993096256e7e37e52c5167a56/Day18/report_35_impact_buf_slack_improve.png">









</details>

# Day-19 Final Step RTL to GDSII

<details>

 <summary>Introduction to maze Routing use Lee's Algorithm</summary>

 **Routing** 

 Routing refers to the process of connecting various components, such as transistors, logic gates, and other electronic elements, on an integrated circuit (IC) using a network of interconnected wires or metal layers. Efficient and 
 optimized routing is crucial for the performance and functionality of VLSI chips. There are two main types of routing in VLSI: global routing and detailed routing.

 **Maze Routing Lee's Algorithm**

 The Lee algorithm, also known as the Lee-Moore algorithm, is a pathfinding or maze routing algorithm used in computer science, particularly in VLSI design and printed circuit board (PCB) design. Its primary purpose is to find the 
 shortest path between two points on a grid or maze, considering obstacles or blocked areas. It is a breadth-first search (BFS) algorithm and is often used in detailed routing stages of VLSI design.

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/779782fc-5a67-490b-9151-37e8c87df9f1)

 The steps in Lee Algorithm

 *Initialization* :

 - Create a grid or maze where each cell can be either empty (open) or blocked.
 - Mark the starting point as the source cell and the destination point as the target cell.
 - Initialize a queue data structure to manage the cells to be explored.

 *Breadth-First Search* :

 - Begin with the source cell and enqueue it in the queue.
 - Set its distance or step count as 0.
 - Start a loop until the queue is empty.
 - For each cell in the queue
 - Explore the neighboring cells (up, down, left, right) that are not blocked and have not been visited. If a neighboring cell is not visited, mark it as visited, enqueue it, and set its distance or step count as the distance of the 
   current cell plus one. Continue this process until the destination cell is reached or until there are no more cells to explore.

*Backtracking* :

 - Once the destination cell is reached, the algorithm can backtrack from the destination to the source by examining the neighboring cells and choosing the one with a lower distance value at each step. This retraces the shortest path 
   from the destination to the source.

*Path Construction*:

- After backtracking, the path from the source to the destination is reconstructed, and the shortest route is found.
- The Lee algorithm is especially useful in detailed routing for VLSI design because it helps find the shortest path while taking into account the grid structure and obstacles. It is an efficient way to navigate around obstacles, 
  avoid congestion, and connect various components on an integrated circuit

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/acfa396e-fd15-4474-b2f7-6f25de87874e)

  ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/53494707-cbe3-4c51-ba0b-1d4a3b0f3d5c)

One of the key advantages of the Lee algorithm is its ability to guarantee that the shortest path is found. However, it may require a significant amount of memory and can be computationally intensive for large grids or mazes. There are variations and optimizations of the Lee algorithm to address these limitations, such as bidirectional Lee algorithm, A* algorithm, and hierarchical versions for PCB routing.

</details>

<details>

 <summary>Design Rule Checks</summary>

 - Design Rule Checks (DRC) are a crucial part of the integrated circuit (IC) design and manufacturing process, especially in VLSI (Very Large Scale Integration) design.
 - DRC is a set of guidelines and checks used to ensure that the layout of an IC adheres to manufacturing and design rules. These rules are essential to guarantee that the IC can be manufactured successfully and will function as 
   intended.

 - Some of the Design Rule checks are as shown in the figure

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/1f1dae6c-5cee-4291-8f89-c61e6acd962b)

 - One type of DRC violation is a signal short, where two wires that are not intended to be connected becomes in contact on the same layer.

 - This could lead to functional failure, so this needs to be taken care of.

 - To fix this, we need to simply moving one of the wires onto a different metal layer.

 - However, please keep in mind that there are new drc rules that need to be taken into account.

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/1a3628ae-8b89-44d8-a20c-b8eab78c087d)

 - Performing parasitic extraction, where the resistances and capacitances of the wires are extracted and will be used for further processes.

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/caa86bae-1ac6-4788-b1f5-28170f960245)

      
</details>

<details>

 <summary>Labs</summary>
 If exited from openlane 
 
```ruby
cd work/tools/openlane_working_dir/openlane
make mount
pwd
ls -ltr
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag 13-01_14-09
```

In openlane 
```ruby
echo $::env(CURRENT_DEF)    (Ensure current_def is on the CTS stage)
gen_pdn                     (To generate power distribution network)
```
We get the error

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e76f7c793bc6da02d128f1253e7a0d6a8cd9962b/Day19/gen_pdn_error_1.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e76f7c793bc6da02d128f1253e7a0d6a8cd9962b/Day19/gen_pdn_error_2.png">

**Basics of global and detail routing and configure TritonRoute**

```ruby
echo $::env(CURRENT_DEF)            (Ensure the def file of pdn has been created)
echo $::env(ROUTING_STRATEGY)
set ::env(CURRENT_DEF) <path_of_cts.def>
run_routing
```
when we run the command *run_routing* we get

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day19/run_routing.png">

The results can be seen in the result folder

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/master/Day19/image_out_routing.png">





</details>

# Day-20 Floorplanning and powerplanning labs in ICC2
<details>

 <summary>Theory</summary>
 Physical design flow, in the context of integrated circuit (IC) or semiconductor design, refers to the series of steps and processes involved in transforming a logical design (usually described in a hardware description language like 
 VHDL or Verilog) into a physical layout that can be manufactured as an actual semiconductor device. 

 - Netlist Synthesis: This step begins with a logical design, often expressed as a high-level netlist. During netlist synthesis, the design is converted into a gate-level representation, where logical gates and their interconnections 
   are defined. This process often involves technology-specific libraries and mapping the logical gates to their physical counterparts.
 - Floor Planning: Floor planning involves determining the placement of major components of the design, such as functional blocks, memory cells, and I/O pads, within the chip's layout area. The goal is to optimize for area, power, and 
   performance while adhering to manufacturing constraints.
 - Placement: Placement involves determining the precise locations of individual gates and cells on the chip. Algorithms are used to optimize for factors such as wirelength, signal delay, and power consumption. This step plays a 
   critical role in the overall performance of the chip.
 - Global Routing: In global routing, the paths for interconnections between cells are defined, but not yet detailed. It focuses on creating a feasible routing structure that adheres to design rules while avoiding congestion.
 - Clock Tree Synthesis: This step focuses on creating a clock distribution network that ensures that clock signals reach all parts of the chip with minimal skew and jitter.
 - Physical Verification: The layout is subjected to a series of checks, such as Design Rule Checking (DRC) and Layout vs. Schematic (LVS) checks, to ensure it adheres to manufacturing and design rules.
 - Extraction: Extraction involves deriving accurate electrical models of the interconnections between components from the physical layout. This data is critical for further simulations.
 - Static Timing Analysis (STA): STA is performed to verify that the design meets its timing requirements under various operating conditions, taking into account process variations and parasitic elements.
 - Power Analysis: Power analysis involves estimating and optimizing power consumption at various levels, including dynamic and leakage power.
 - Signoff: Before the design can proceed to manufacturing, it undergoes a final signoff stage where all requirements are met, and all checks pass. This includes not only DRC and LVS but also other criteria like thermal analysis and 
   electromigration checks.
 - Tapeout: Once the design passes all the checks and meets the specifications, it is considered ready for fabrication. The final design data is prepared and sent to the semiconductor foundry for manufacturing.

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/a10c21bb-afe6-42a4-abcc-1e21b1351f09)

 
</details>
<details>

 <summary>Labs</summary>

 - Git clone all the required repositories
   ```ruby
   git clone https://github.com/manili/VSDBabySoC.git
   git clone https://github.com/Devipriya1921/VSDBabySoC_ICC2.git
   git clone https://github.com/bharath19-gs/synopsys_ICC2flow_130nm.git
   git clone https://github.com/kunalg123/icc2_workshop_collaterals.git
   git clone https://github.com/google/skywater-pdk-libs-sky130_fd_sc_hd.git
   git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
   ```

- Edit the avsdpll.lib and vsdbabysoc.tcl

  1. vsdbabysoc.tcl

  - Modifying the contents to my path, remove -lib in read_lib commands, and replace MYCLK to clk since the clock used in the design is {clk}
   
  - All of the commands have been inserted in gvim and the tool will run it once at a time


  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/vsdbabysoctcl_1.png">


  2. avsdpll.lib
 
  - Remove all the unwanted pins

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/modifying_avsdpll_2.png">

  - Open dc_shell and source the vsdbabysoc.tcl

  Design_vision opens eith the schematic as shown below

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/vsdbabysoc_sch_3.png">

  Core1

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/vsdbabysoc_core_sch_4.png">


- Reports

  report_area

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/area_5.png">

  report_power

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/power_6.png">

  report_timing

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/timing_7.png">


- Editing top.tcl,icc2_common_setup.tcl,icc2_dp_setup.tcl,init_design.read_parasitic_tech_example.tcl,init_design.mcmm_example.auto_expanded.tcl, pns_example.tcl and running ICC2_shell

  top.tcl

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/top_edit_1_8.png">

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/top_edit_2_8.png">

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/top_edit_3_8.png">

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/top_edit_4_8.png">

  icc2_common_setup.tcl

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/common_setup_edit.png">

  icc2_dp_setup.tcl

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/dp_setup_1.png">

  init_design.read_parasitic_tech_example.tcl

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/parasitic.tech_edit_1.png">

  init_design.mcmm_example.auto_expanded.tcl

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/mcmmexpanded_1.png">

  pns_example.tcl

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/345210fba1467736b5f818beea3156cffe3bf8b8/day20/pns_1.png">
  
  ```ruby
  csh
  icc2_shell
  ```

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/top_tcl_execute_9.png">

  ```ruby
  set_propagated_clock [all_clocks]
  report_timing
  estimate_timing
  ```
  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/eed88ec503442f53d12c4021f719565fcd068c7a/day20/rep_new_1.png">

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/eed88ec503442f53d12c4021f719565fcd068c7a/day20/estimate_no_rules.png">
  

  Schematic

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/top_gui_10_2.png">

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/top_gui_10_1.png">

- Then we check the violators.rpt

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/violations_cap_11.png">

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/violations_tim_12.png">

- Now we change the utilaztion factor to 40%, first we need to modify the vsdbabysoc.sdc and rerun the synthesis

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/new_sdc_13.png">

- Changing the utiliztion to 40% i.e 0.4

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/modifying_util_factor_14.png">

- Rerunning the icc2_shell

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/gui_after_mod_15.png">

- Now if we set the boundary using command

  intialize_floor -boundary {<co-ordinates> from left hand side in anticlockwise direction> -core_utilization <value>}

  The one used in our case was - boundary {{0 0} (1200 0} {1200 650} {0 650}} -core_utilization 0.4

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/gui_ut_40_bounday_10_3.png">

- Giving commands
  ```ruby
  set_propagated_clock [all_clocks]
  report_timing
  ```

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/viol_after_mod_16.png">

- Again checking violators.rpt

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/b0434225f5f46b7e97d5e6295e112843dabede98/day20/viol_after_mod_improve_slack_17.png">

- **Observation** : We can see that slacks have got reduced.

</details>

# Day-21 Placement CTS Routing
<details>

 <summary>Theory</summary>

 - **Placement** : It refers to the process of determining the physical locations of various electronic components on an integrated circuit (IC) design. This step is crucial in the overall IC design process, as it affects the final performance, power consumption, and manufacturability of the chip.The primary objective of placement is to assign a physical position to each logic gate, flip-flop, or other components on the chip. The goal is to minimize wirelength, reduce congestion, and optimize for factors like signal delay and power consumption.
 - **Routing** : Routing in VLSI (Very Large Scale Integration) design is the process of connecting the various components (logic gates, flip-flops, etc.) placed on an integrated circuit (IC) with wires, also known as interconnects.The primary objective of routing is to create an efficient and reliable network of interconnections between the components placed on the chip. This network must meet timing constraints, minimize wirelength, and avoid congestion.
 - **Clock Tree Synthesis** : Clock Tree Synthesis (CTS) is a crucial step in the design of digital integrated circuits, especially those with synchronous logic, such as microprocessors and application-specific integrated circuits (ASICs). The primary purpose of CTS is to create a well-organized and optimized distribution network for clock signals, ensuring that all sequential elements (like flip-flops) receive clock signals with minimum skew, low latency, and low power consumption.
   
</details>
<Details>

 <summary>Labs</summary>

 - Analysing the ICC2_run at core utilization of 40%

 - In top.tcl we can see that
   
 	- create_placement is used to create placement for the design. floorplan option is selected to make the design planning styled as placement.
  
 	- Pin Placement is done by sourcing pns.tcl to sync with the current technology file regarding power grid creation.

    	<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/create_placement_1.png">

        <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/create_placement_2.png">

 - **Reports that were generated from the run**

 	- check_design.pre_pin_placement

		<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/check_design_3.png">

 	- report_port_placement.rpt

    	<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/report_pin_placement_4.png">

    - icc2_output.txt
   
        <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/report_placement_5.png">

  	- vsdbabysoc.post_estimated_timing.rpt

  		<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/vsdbabysoc_timing_6.png">

   	- vsdbabysoc.post_estimated_timing.qor

  		<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/vsdbabysoc_qor_7.png">

   		<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/vsdbabysoc_qor_8.png">

   	- vsdbabysoc.post_estimated_timing.qor.sum

		<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/vsdbabysoc_qor_summary_9.png">

- Clock Tree Analysis

  	- Here when gui opens we need to go to window sections and in that we need to select clock tree synthesis analyser
 
 	- PLL schematic

		<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/cts_window.png">

 	- Fanout

 		<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/23fc7886927369dd77f9cfc47f43c890b1d098ed/Day21/cts_window_2.png">

  	
</Details>

# Day 22 CTS Analysis

<details>

 <summary>Clock tree synthesis</summary>

 - Clock Tree Synthesis involves the generation of a clock distribution network that ensures a stable and synchronized clock signal throughout the entire chip or circuit.
 - CTS is performed for several importnant reasons :
   
   1.Synchronization: In digital circuits, synchronous operations are critical. A clock signal is used to coordinate the activities of various elements within the circuit, ensuring they work together harmoniously. CTS is done to 	 
     distribute this clock signal uniformly to all parts of the chip so that all operations occur in sync.

   2.Minimizing Clock Skew: Clock skew refers to the variation in arrival times of the clock signal at different parts of the chip. Excessive clock skew can lead to timing violations and impact the overall performance and reliability 
     of the circuit. CTS is employed to minimize clock skew, ensuring that the clock signal arrives at all elements at nearly the same time.

   3.Timing Closure: Achieving timing closure is a crucial objective in chip design. CTS helps in meeting timing constraints by distributing the clock signal efficiently. When the clock signal reaches all elements simultaneously, it 
     becomes easier to manage and control the timing of the circuit.

   4.Power Efficiency: CTS can be used to design a power-efficient clock distribution network. By strategically placing buffers and repeaters and optimizing clock tree topology, designers can minimize power consumption in the clock 
    distribution network, which is especially important in portable and battery-powered devices.

- Various Algorithms used for CTS

   1. H-Tree

   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/aeaeffdc-8156-47e5-a3a2-5836ae5ee712)

  Steps:

  - Find out all the flops present
  - Find out the center of all the flops
  - Trace clock port ot the center point
  - Divide the core into two parts, trace both the parts and reach to each center
  - From the center, again, divide the area into two and again trace till center at both the end
  - Repeat this algo till the time we reach the flop clock pin
 
2. **Clockwise multi-source clock tree synthesis (CTS) algorithm** : It is a specific approach to designing and optimizing the clock distribution network in digital integrated circuits. In this algorithm, multiple clock sources are considered, and the clock tree is designed to distribute clock signals from these sources in a clockwise direction.
 
   ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/1ad68f9f-0d5e-47f4-851c-e5cae80dfc7a)

  Steps:

  - Identify and specify the multiple clock sources in the design. These sources may be associated with different clock domains or regions of the chip.
  - Create a clock tree topology that outlines the placement of buffers and repeaters, the routing of clock lines, and the interconnection of clock network elements. In a multi-source CTS, the tree should be designed to distribute 	 
    clock signals from all selected sources.
  - Determine the type and sizes of buffers to be used in the clock tree. Sizing is crucial for optimizing power consumption, signal integrity, and clock skew. Consider the characteristics of each clock source when sizing buffers.
  - Physically lay out the clock distribution network, including the placement of buffers and the routing of clock lines. Ensure that the routing accommodates the distribution of clock signals from multiple sources in a clockwise 
    manner
  - Implement clock gating cells as needed to selectively enable or disable clock signals to specific circuit portions when they are not in use. Ensure that clock signals are synchronized as they traverse the clock tree.
  - Ensure that the clock tree meets timing constraints, such as setup and hold times, for all flip-flops and other clocked elements in the design. Adjust buffer sizes and placement as necessary to achieve timing closure.
  - After synthesizing the clock tree, perform thorough verification, including simulations and static timing analysis, to ensure that the design requirements are met and that clock signals are properly distributed from all sources.
  - t's common to go through several iterations of clock tree synthesis to achieve the desired performance, power efficiency, and timing closure. Fine-tune the clock tree as necessary based on the results of analysis and simulation.


**Various CTS checks**

- Skew check
- Latency check
- Pulse width check
- Duty cycle check
- Power check
- Crosstalk Quality check
- Delta Delay Quality check
- Glitch Quality check





 








      


</details>

<details>

 <summary>Labs</summary>

 - In ICC2 Compiler we give the command *check_clock_tree* , This command checks the clock trees of current design for posiible problems with netlist, timing constraints, or other tool configurations that can adversely impact clock tree synthesis.This is used to check for common problems that might impact CTS

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/37d2085ca9d207a3e1c606f0a942a786ffca396a/Day22/check_clock_tree.png">
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/37d2085ca9d207a3e1c606f0a942a786ffca396a/Day22/check_clock_tree2.png">

 When we man *CTS-904*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/37d2085ca9d207a3e1c606f0a942a786ffca396a/Day22/man_CTS-904_10.png">

 In this we can see that there is 1 warning which states that there are some clock cells that does not have LEQ cells for resizing. LEQ cells  are level Equivalence cells which are used to create logic gates or elements that have equivalent feature of different complexity. As a result the sizes of the cells can be easily resized by using a cell of differnt complexity.

 CTS-015 : It is a warning which comes up when we set_max_delay  or  set_min_delay  constraints are defined in the clock network.

 CTS-918 : It is a warning which comes up when Volatage  area  are  blocked for buffering through app option. It can be removed by resetting the  value  of  app  option  "opt.com-
       mon.blocked_vas" to empty string.

In our case we got only one warning that was of *CTS 904*.



- The next command is *check_legality* , This command checks the legality of the curreent_placement and output a report of violation statistics.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/37d2085ca9d207a3e1c606f0a942a786ffca396a/Day22/Checklocality_3.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/37d2085ca9d207a3e1c606f0a942a786ffca396a/Day22/Checklocality_4.png">

- Next In top.tcl we can see that there is a command called *clock_opt* , this is used to to perform clock tree synthesis and it optimizes the clock trees.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/add_now.png">

 **Reports**

- report_clock_timing -type summary
  	  
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/timing_summary_1.png">

**Explaination**

1. The above report displays the five worst setup and two worst hold skews in the  clock network of CLK, taking uncertainty into account.
2. This report  provides only a list of maxima and minima of the skew, latency, and transition time attributes over the  given  networks.
3. This report specifies a summary report which shows the worst instances of transition time , latency and skew over the clock network. It gives the maximum setup launch latency which is the worst            setup latency of a clock pin in this case it is for the pin *core1/CPU_imm_a2_reg[20]/CLK*. Similarly it gives minimum setup capture latency, minimum hold launch latency, maximum active                    transition , minimum     active transition , maximum and minimum hold skew.
4. In the report we can see that the design is working on func1 mode
5. The symbol representation is as follows

           r         Rising transition
   
           f         Falling transition
   
           p         Propagated clock to this pin
   
           i         Clock inversion to this pin
   
           -         Launching transition
   
           +         Capturing transition
   
           e         Exception on this pin

7. rp-+ -> rising transition of propagated clock in the clock pin from launch to capture.
 




     
- report_clock_timing -type skew

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/skew_5.png">

**Explaination**

- These repoprts specify a skew report ,For skew reports, each report entry  is a  pair  of  sink  pins and their relative skew.
- Skews reported by report_clock_timing are local skews only.  Local skew exists from one sink pin to another only if their associated sequential devices are connected via a data path in the appropriate     from-to sense.

		
- report_clock_timing -type latency

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/latency_6.png">

**Explaination**

- Specify a latency report of those  clock  paths that reach right trigger edge at endpoint.
  	
- report_clock_timing -type transition

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/transition_7.png">

When we give *report_clock_settings* it gves all the clock settings , configurtaions , spacing rules, route rules , max load cap on buffers and inverters.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/report_clock_settings_11.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/report_clock_settings_12.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/report_clock_settings_13.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/3e1455da6f8b58502410662dbb7e9d2fb5242aa4/Day22/report_clock_settings_14.png">



 
  

 
 

   
</details>

# Day-23 Clock Gating techniques

<details>

 <summary>Theory</summary>

 **Clock Tree Synthesis (Advanced H-Tree)**

 - A digital circuit having lot of clocks, so if designing a clock tree will be huge with many buffers etc
 - So the whole chip will section into smaller versions and then each section will have its own clock tree, and then finally a complete routed tree.

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/55b30390-571b-440c-8641-68055a254f4d)


**Clock Gating**

 

 ![image](https://github.com/AbhishekChinchani/Samsung_pd/assets/142480501/6bdd8cce-dfeb-4b3e-a93a-7d4140572184)


   
 - Beside area and timing, there is another important factor which is power -> Need power “aware” CTS
 - Clock gating is one of the techniques used to save the dynamic power of clock elements in the design
 - The principle behind clock gating is to stop the clock of those sequential elements whose data is not toggling
 - Clock gating technique using AND, OR Universal NAND gate
 - It has been found that 50% of the dynamic power originates from clock-related circuits
 - Clock gating is inserted during synthesis stage and optimized in the implementation stage (Physical Design stage)
 - Example scenario why required clock gating: If there is a block only need clock signal for 10 mins but the clock signal is running 1hr, so a lot of power is dissipating (due to switching activity), so we need clock gating which act 
   as switch.
 - Clock gating is a common technique used in Very Large Scale Integration (VLSI) design to reduce power consumption in digital circuits, particularly in synchronous systems. It involves selectively enabling or disabling the clock 
   signal to specific parts of the circuit, depending on the operational requirements, which can help save power when certain components of the circuit are not actively performing any useful work.

**Routing**

- The last step of physical design flow
- Making physical connections between signal pins using metal layers
- There is mainly 3 types of routing:

  	- P/G routing
  	- Clock routing
  	- Signal routing
  	  	- Global routing
  	  	- Detailed routing


- The command which performs the above routing is *route_opt*
</details>

<details>

 <summary>Labs</summary>
 
 - Three types of routing: P/G routing, Clock routing and Signal routing

	P/G routing:

  	This we can see in pns_example.tcl as shown in the below figure

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/31b137e4bee427cca24cd607ca9e45ceae265ec5/day23/pns_2.png">
    

**Clock Routing and signal routing**:

- place_opt: Place and optimize the current design
- clock_opt: Synthesize and route the clocks in the current design and then further optimize the design based on the propagated clock latencies
- route_auto: runs global routing, track assignment and detail routing in one step

top.tcl

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/31b137e4bee427cca24cd607ca9e45ceae265ec5/day23/top.tcl_1.png">

 - We need to add 3 lines between place_opt and clock_opt , to insert the clock buffers in the design.

 ```ruby
  
 set_lib_cell_purpose -include cts {sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_*}
 synthesize_clock_tree
 set_propagated_clock \[all_clocks]
 ```

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/8124a19f0bda887ab38c003fa9d3f45d8e50315b/day23/adding_in_top.tcl.png">

  -  *set_lib_cell_purpose -include cts {sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_*}* command specifies that the library cells in the  tech_lib library(sky130_fd_sc_hd__tt_025C_1v80)  whose names start with "buf" should be used for clock tree synthesis.
  -  *synthesize_clock_tree*  command synthesizes clock trees and updates  the  design  database with  the  compiled  clock  trees. The compilation of the clock tree is skew driven.  Optionally, this command can optimize compiled clock tree for slack metric.
  -  *set_propagated_clock \[all_clocks]* command Specifies that delays be propagated through the clock network to determine latency at register clock pins.Propagated  clock latency is used for post-layout, after final clock tree generation. If  the  set_propagated_clock  command  is applied to pins or ports, it affects all register clock pins in the transitive fanout of the pins or ports. *The above command specifies to use propagated clock latency for all clocks only in the current mode in the design* .
   
 - Before this we need to change the input voltage to 1.80V as we know that our tech file supports 1.8V , but the default used in this case was 1.1V.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/8124a19f0bda887ab38c003fa9d3f45d8e50315b/day23/change_voltage_1.8_3.png">

 - Then when we source this file we can see buffers in the design

 - The schematic is as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/4be7c65805345bf2f7d416a88729b23b7e89e99f/day23/schematic.png">
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/1a095f3223c553e87e06fd6f3f20156afab346b9/day23/The_buffers_in_gui.png">

  Here we can see that the buffers are added in the design
   

 - We can see that slack is reduced from -1.90 to -0.13

    Before
   
<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/8124a19f0bda887ab38c003fa9d3f45d8e50315b/day23/viol_after_mod_16.png">

   After

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/8124a19f0bda887ab38c003fa9d3f45d8e50315b/day23/slack_is_comparitively_reduced.png">

The clock buffers and ICG inserted in the circuit are as follows

```ruby

Buffer/Inverter reference list for clock tree synthesis:
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_12
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_6
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufbuf_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufbuf_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s15_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s15_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s18_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s18_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s25_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s25_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s50_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s50_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlygate4sd1_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlygate4sd2_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlygate4sd3_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlymetal6s2s_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlymetal6s4s_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlymetal6s6s_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__probe_p_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__probec_p_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufinv_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufinv_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinvlp_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinvlp_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_12
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_6
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_8

ICG reference list:
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlclkp_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlclkp_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlclkp_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__sdlclkp_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__sdlclkp_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__sdlclkp_4
```
		
</details>

# Day 24 ECO

<details>

 <summary>Labs</summary>

 - After performing CTS (with clock buffers) we can see that the slack is improved but it is not met.

  Setup
  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e0201bd2deefd16dd3d0a05e0c713fdef068dd8b/day24/max_violated_4.png">
  
  Hold
  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e0201bd2deefd16dd3d0a05e0c713fdef068dd8b/day24/min_violated_3.png">

  The slacks have significantly improved compared with the case without buffers.

- To meet the slack we upsize/downsize the cell depending on the requirement.
- To anlayze the path in GUI

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/before_worst_slack.png">

  The schematic of clock path  is as follows

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/clock_path_viol.png">

   
   
- Upsizing the cell will increase the drive strength of the cell which helps in reducing the delay.
- Upsizing the cell using the command *size_cell*
  ```ruby
  size_cell core1/U9 sky130_fd_sc_hd__inv_2
  size_cell core1/U471 sky130_fd_sc_hd__a22o_2
  size_cell core1/U471 sky130_fd_sc_hd__a22o_1
  size_cell core1/U3 sky130_fd_sc_hd__nand2_2
  ```
- Now we can see that the *report_timing -delay max* is met

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e0201bd2deefd16dd3d0a05e0c713fdef068dd8b/day24/slack_met.png">

- The worst met slack path in GUI is as follows

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/after_meeting.png">

- But the hold slack is not met. It is violating by a small margin of 4.9ps
- To meet the hold slack we need to downsize the cell
```ruby
size_cell core1/ZCTSBUF_23155_1984 sky130_fd_sc_hd__bufbuf_12
size_cell core1/ZCTSBUF_25196_1983 sky130_fd_sc_hd__buf_14
```
  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e0201bd2deefd16dd3d0a05e0c713fdef068dd8b/day24/slack_met_min_2.png">

- Giving *report_global_timing*

  <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/report_global_after.png">

  We see that there are no setup or hold violations.

**Comparing results before and after ECO**

*report_qor*

Before 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e0201bd2deefd16dd3d0a05e0c713fdef068dd8b/day24/bef_qor.png">

After

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/qor_5.png">

- We can see that the area is increased due to the upsizing of cell for meeting the slack.
- We can see that still its not clean it still has 4 trans and 6 cap violations.
- Fixing the trans violations

  When we give *report_constraints -max_transition -all_violators*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/trans_viol.png">

We see that there are 4 trans violation. The steps to meet these violation is first *report_timing -through <violating_net>* Then increasing the drive strength of that cell using *size_cell*.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/trans_proc_1.png">

Repeating this for different nets we can see that the trans violation is getting fixed

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/qor_after_trans.png">

- Now we can see that trans is fixed and there are two cap violations, These can be fixed by *report_timing -through <violating_net>* . Then increasing the drive strength of the cell using *size_cell*

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/cap_net_proc_1.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/cap_net_proc_2.png">

Now we can see that all the violations are fixed

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/final_qor_after_removing_all_1.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/49eae99114bba33d7402e739cb87bb99241db9d9/day24/day24a/eco/final_qor_after_removing_all_2.png">

*report_power*

Before

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e0201bd2deefd16dd3d0a05e0c713fdef068dd8b/day24/bef_power.png">

After

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e0201bd2deefd16dd3d0a05e0c713fdef068dd8b/day24/power_6.png">

- We can see that the power is increased due to high drive strength.

**Adding Decaps**

- Adding decaps 




  
    
</details>








 
   

 

















 
 



   

	
  
   	       
   
      
      
           

             
      

 


















