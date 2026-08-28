## 
Implement a tree based order book 

- implement networking feature 
- logging feature 
- write tests 
- add optimization 
    - dsa and architecture optimization 
- profiling code 
- look into other implementations 
- adopt optimizations to make exchange fast 
- can different matching strategies be adopted in on hot and cold restart by changing configs 
- can I add message routing with order blazing MQ 
- can I compare with Aeron message routing 
- can I route using Lmax disruptor 

### Optimization 

add orders to a custom allocator memory allocator. 
Having all orders in sequential memory ordering significantly 
improves memory access and avoids calling of kernel allocator 
- optimize cache alignment of the orders 

What are the performance comparisons between the three systems is there a performance hit in any one of them ? 
Which is the best message system and for which scenario ? 

Can I implement a plugin system so that I can directly plug in each messaging system both hot plug in and cold pulgin 




Create Raylib based UI system to visualize market data in the orderbook. 
- this should include volume in the system 
- buy orders, sell orders 
- statistics for buying and selling 
- have admin, user, system admin pages 

## Interesting features 
- can I add a dark pool 
- add a brokerage system. The broker offers as good prices as the exchange and executes the orders 

- system admin 
- should be able to view, hot path statictics, throughput over time 
- 


- Connect it to FPGA project 
- Write a paper with benchmarks information 
- ask prof at Ulm for improvements and publishing 
- compare the paper to the one written on HFT 
- 