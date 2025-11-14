1. Use reg when u assign ( the thing that is being assinged should only be reg) inside an always or initial block ( assing here means the value being changed )
2. assign statement => wire 
3. .clk(clkd) connect clk port of the uut to clkd of testbench
4. For circuits with memory use reg and assign inside an always block 
5. Non-Blocking assignment

``	1. the arrow one is the source
``