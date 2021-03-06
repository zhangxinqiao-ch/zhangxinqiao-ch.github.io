## Project: Clock Tree Optimization using Useful Skew (ECO)

In this project, we optimize clock tree to improve the performance of a design using useful skew. The objective is to minimize absolute total and worst negative slack values. The optimized results will be evaluated according to the optimization approach, total and worst negative slack values, and the number of violating endpoints.

### 1. Background
<img src="images/p02t1.jpg?raw=true"/>

In this project, netlist, spef and sdc file for each design are provided. We need to implement an optimization flow for clock tree using useful skew to improve the timing of given designs. The initial designs have negative slack values. We are allowed to optimize / modify only clock tree, not data paths. There is one clock for each design.

Initial data of the design is shown below:

| Benchmark     | Cell count | FF count | Clock period (ns) | Initial WNS (ns) | Initial TNS  (ns) | # of violating endpoints      |
|:------------- |:-----------|:---------|:------------------|:-----------------| :-----------------|:------------------------------|
| usb_phy       | 503        | 98       | 0.42              | -0.061           |-0.547             |  39                           | 
| aes_cipher_top| 17261      | 530      | 1.3               | -0.383           |-13.450            | 262                           | 

### 2. Methods
The method we use is applying differnt cells to meet the requirement. If the requirement does not meet, we will go back to the previous state until all the cells have been tried 5 times.


### 3. Results

Our post-ECO results and ideal results are shown below

| Benchmark                  |  WNS (ns)          |  TNS (ns)       | # of violating endpoints |
|:---------------------------|:-------------------|:----------------|:-------------------------|
| usb_phy (Post-ECO)         | -0.048508          |-0.150393        | 10                       | 
| usb_phy (Ideal)            | -0.041             |-0.154           | 11                       | 
| aes_cipher_top (Post-ECO)  | -0.0276346         |-1.066625        | 14                       | 
| aes_cipher_top (Ideal)     | -0.0273            |-0.467           | 18                       | 


### 4. Conclusion:
The result shows a very good post-ECO result and this project gets 99.2/100 points in ECE260B
