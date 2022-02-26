# 8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter <br/>
This repository presents the design of 8 bit Carry Select Adder with Binary to Excess one Converter. It is implemented on Synopsys Custom Compiler in 28nm technology node.<br/>
# Table Of Content <br/>
* [Abstract](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#abstract-)<br/>
* [Detailed Explanation with reference Block diagram](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#detailed-explanation-with-reference-block-diagram)<br/>
* [Tool used](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#tool-used)<br/>
* [Inverter](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#inverter)<br/>
* [AND](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#and-)<br/>
* [XOR implementation using Transmission logic](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#xor-implementation-using-transmission-logic-)<br/>
* [Full adder implementation using Transmission logic](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#full-adder-implementation-using-transmission-logic-)<br/>
* [4 bit Ripple Carry Adder](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#4-bit-ripple-carry-adder)<br/>
* [ 2:1 MUX implementation using Transmission logic](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#21-mux-implementation-using-transmission-logic)<br/>
* [Array of 5 2:1 MUX](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#array-of-5-21-mux)<br/>
* [4bit_BtoE1converter](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#4bit_btoe1converter)<br/>
* [ 8 bit Carry Select Adder](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#8-bit-carry-select-adder)<br/>
* [Testbench schematics of 8 bit Carry Select Adder with Binary to Excess one converter](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#testbench-schematics-of-8-bit-carry-select-adder-with-binary-to-excess-one-converter)<br/>
* [Simulation result](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#simulation-result)<br/>
* [Transistor count for easc block](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/blob/main/README.md#transistor-count-for-each-block)<br/>
* [Total transistor count for 8 bit CSA with binary to excess one converter]()<br/>
* [Netlist](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#netlist)<br/>
* [Author](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#author)<br/>
* [Acknowledgements](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#acknowledgements-)<br/>
* [Reference](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#reference-)<br/>
# Abstract <br/>
Addition is a back bone of arithmetic unit and computer arithmetic. Addition in arithmetic is often the work house of computational unit. There are different type of adder present in vlsi design, they are ripple carry adder, carry look ahead adder, carry select adder. This paper presents idea about the design of 8 bit carry select adder with binary to excess one converter. The design is implemented using Synopsys tool using 28 nm technology node. This design consist of 3 different block they are array of 2:1 multiplexer, 4 bit binary to excess one converter and 4 bit ripple carry adder. The presented design decreases the computational time and increases the speed when compared to ripple carry adder.<br/>
# Detailed Explanation with reference block diagram<br/>
![CSA (1)](https://user-images.githubusercontent.com/88282645/155842219-7aa47b1e-9c51-4073-b3c5-e7934c563833.jpg)<br/>
In 8-bit carry select adder the adder is split into two blocks they are upper bits addition and lower bits addition. Lower bits addition block will do 4 bit addition using 4-bit ripple carry adder. Four full adders present inside the 4 bit Ripple Carry Adder block,it is implemented using transmission gate logic. The upper bits addition are done in two form, one is with carry in as 0 and the other is with carry is as 1. The upper bits addition with carry is equal to 0 is done using 4 bit ripple carry adder and the output is given as input to 2:1 mux where is input propagate to output  when selection signal is zero. Upper bits addition with carry is equal to 1 is done using Binary to Excess one converter. The input for binary to excess one converter is taken from the output bits of 4 bit upper bit adder block and the output of binary to excess one converter block is given as  input to 2:1 mux when selection signal is 1 one this input will appear at output. The selection signal for the block with array of mux is the C1 signal, it is a carry out signal from 4-bits lower bit adder block. Mux is designed using Transmission gate logic.<br/>
# Tool used<br/>
/*Synopsys Custom Compiler*/:  The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.<br/>
/*Synopsys Primewave*/:  PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.<br/>
/*Synopsys 28nm PDK*/:  The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.<br/>
# Inverter<br/>
Inverter schematics<br/>
![inverter_schematics](https://user-images.githubusercontent.com/88282645/155843016-757bf8be-9596-479e-802b-8be4e05b59f1.png)<br/>
Inverter Symbol<br/>
![inverter_symbol](https://user-images.githubusercontent.com/88282645/155843017-c7a22c0d-cdfe-4c47-aa97-90db354f8534.png)<br/> 
# AND <br/>
AND_Schematics<br/>
![AND_Schematics](https://user-images.githubusercontent.com/88282645/155843164-880c67c4-7375-4c1a-ac7a-8e0a8e85d417.png)<br/>
AND_Symbol<br/>
![AND_Symbol](https://user-images.githubusercontent.com/88282645/155843165-88554318-3bdf-4a25-9c30-f8cc871c025e.png)<br/>
# XOR implementation using Transmission logic <br/>
XOR_schematics<br/>
![XOR_schematics (1)](https://user-images.githubusercontent.com/88282645/155843320-fef492f4-77cd-4f00-9dc0-60f12671a441.png)<br/>
XOR_Symbol<br/>
![XOR_Symbol](https://user-images.githubusercontent.com/88282645/155843321-400167f9-a914-45b0-aa3e-85b550540c07.png)<br/>
# Full adder implementation using Transmission logic <br/>
FA_Schematics<br/>
![FA_Schematics](https://user-images.githubusercontent.com/88282645/155843412-c6b9d881-4df1-4882-b2ed-0995cc03e5e8.png)<br/>
FA_Symbol<br/>
![FA_Symbol](https://user-images.githubusercontent.com/88282645/155843416-c57017f4-8a39-4667-97e7-5c16dbe04b31.png)<br/>
# 4 bit Ripple Carry Adder<br/>
4bit_RCA_Schematics<br/>
![4bit_RCA_Schematics](https://user-images.githubusercontent.com/88282645/155843470-21377329-9ee1-409c-8e8d-30196329c7e2.png)<br/>
4bit_RCA_Symbol<br/>
![4bit_RCA_Symbol](https://user-images.githubusercontent.com/88282645/155843471-de82c5e5-d7e1-473a-8b84-3ed04e832154.png)<br/>
# 2:1 MUX implementation using Transmission logic<br/>
2:1 MUX Schematics<br/>
![MUX_Schematics](https://user-images.githubusercontent.com/88282645/155843502-10246794-2857-4024-b44c-35e7a92f55b8.png)<br/>
2:1 MUX Symbol<br/>
![MUX_Symbol](https://user-images.githubusercontent.com/88282645/155843504-4285302e-81af-4b8a-9747-8f0ed4d06915.png)<br/>
# Array of 5 2:1 MUX<br/>
MUX_Array_Schematics<br/>
![MUX_Array_Schematics](https://user-images.githubusercontent.com/88282645/155843550-580e33d7-cbf5-4a4c-9a9a-03ffb4fee8e8.png)<br/>
MUX_Array_Symbol<br/>
![MUX_Array_Symbol](https://user-images.githubusercontent.com/88282645/155843551-12495b10-8994-46fe-ba91-92906d842538.png)<br/>
# 4bit_BtoE1converter<br/>
4bit_BtoE1converter_Schematics<br/>
![4bit_BtoE1converter_Schematics](https://user-images.githubusercontent.com/88282645/155843640-f4a50072-02eb-4921-93d3-0543fc8fd11a.png)<br/>
4bit_BtoE1converter_Symbol<br/>
![4bit_BtoE1converter_Symbol](https://user-images.githubusercontent.com/88282645/155843641-9cb3bb1a-652e-4df2-8112-d268f5a19dc8.png)<br/>
# 8 bit Carry Select Adder<br/>
8 Bit CSA Schematics<br/>
![CSA_Schematics](https://user-images.githubusercontent.com/88282645/155843738-930f61ca-8e86-4877-aae1-5e543e105e77.png)<br/>
8 bit Carry Select Adder<br/>
![CSA_Symbol](https://user-images.githubusercontent.com/88282645/155843740-fd6a5398-eef5-4e22-ae3f-4108853f611e.png)<br/>
# Testbench schematics of 8 bit Carry Select Adder with Binary to Excess one converter<br/>
![Test_8bit_CSA](https://user-images.githubusercontent.com/88282645/155844102-114a6a32-ad96-4ed9-abb1-b91475d32492.png)<br/>
# Simulation result<br/>
8 bit input A<br/>
![8bit_csa(Ain)](https://user-images.githubusercontent.com/88282645/155845741-418740b2-d62a-4987-95d4-56ccf0be681e.png)<br/>
8 bit input B<br/>
![8bit_csa(Bin)](https://user-images.githubusercontent.com/88282645/155845754-3e8f63c0-198a-4e2e-a2a9-3f694773addf.png)<br/>
8 bit Sum and 1 bit Cout<br/>
![8bit_csa(result)](https://user-images.githubusercontent.com/88282645/155845755-388a555d-b946-4bca-91c8-63faa82b545b.png)<br/>
# Transistor Count for each block<br/>
Block name                              -  Transistor Count<br/>
[Inverter](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#inverter)                            -  2<br/>
[And](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#and-)                                 -  4<br/>
[Xor](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#xor-implementation-using-transmission-logic-)                                 -  8<br/>
[2:1 MUX](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#21-mux-implementation-using-transmission-logic)                             -  6<br/>
[Array of 5 2:1 MUX](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#array-of-5-21-mux)                  -  30<br/>
[Full adder](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#full-adder-implementation-using-transmission-logic-)                          -  20<br/>
[4 bit RCA](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#4-bit-ripple-carry-adder)                           -  80<br/>
[4bit Binary to excess one Converter](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/edit/main/README.md#4bit_btoe1converter) -  38<br/>
# Total transistor count for 8 bit CSA with binary to excess one converter<br/>
Block name - Number of BLock - Tansistor count - Transistor count for N block<br/>
4_bit RCA   - 2 - 80 - 160<br/>
4bit_BtoE1  - 1 - 38 -  38<br/>
Array of 5 2:1 MUX - 5 - 6 - 30<br/>
/* Total transisitor count*/ : 160+38+30=228<br/>
# Netlist<br/>
You can view the circuit netlists [here](https://github.com/MahishaBM/8-bit-Carry-Select-Adder-with-Binary-to-Excess-One-Converter/tree/main/Netlist)<br/>
# Author<br/>
Mahisha B M, BE in Electronic and Communication Engineering at R. M. K. Engineering College, Thiruvallur-601206<br/>
# Acknowledgements <br/>
[Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836/)<br/>
[Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)<br/>
[Synopsys India](https://www.synopsys.com/)<br/>
# Reference <br/>
http://www.ijeert.org/pdf/v2-i6/25.pdf <br/>






