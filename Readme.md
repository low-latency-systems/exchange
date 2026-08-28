# Implementation of a real time Exchange

The repo contains the implementation of a simulation exchange meant to handle trading in an organisation. 
The system is designed for parallel processing of trades while offering reliability and robustness. 


## Achieving reliability 
The matching engine, core of the system, can be rebuilt by replaying the state logs. Resulting in recovery of the system state within seconds after outage. 

## NB: The system is in development 

## Description of Units

Units are the subsystems that work harmoniously to support real time trade execution. 

1. Matching engine - core of the system bids and asks are matched. Supports Limit and Market Order
                   - Contains a set of orderbooks 
                   - maintains a registry of users to track institution and individual traders 

2. Orderbook       - Tracks orders across each symbol. i.e. APPL has an orderbook and GOOGL has an orderbook 
                   - Contains the bids and asks for its assigned symbol 

3. Order           - Basic unit detailing the status of a trade, quantity, side and amount. e.t.c. 

4. User            - Unit tracking the users data .i.e. amount in their account, profits and losses and trades conducted. 

5. Snapstore       - a unit tracking activities of the matching engine. The information is logged to disk and preloaded for replay 


## Development Features and tools to be supported
1. Raft - consensus protocol to be supported for electing the matching engine 
2. Apache Iceberg - for Columnar storage of Trades executed in disks 
3. Parquet - Default file storage format of Trades exceuted. 
4. DuckDB - database storage engine for parquet file format 
5. Trino - Distributed SQL Query engine  
6. To compress data either during batch processing or storage, deflate and LZ4 compression algos are utilized 
7. DPDK through pcapplusplus for kernel bypass to reduce overhead of the packet from the NIC to the ME. 
8. Messaging queues decision not yet made. Evaluation between blazingMQ and libkafka are underway. 

## Contributing

Not yet defined 

Much inspiration has been drawn from designing a trading system by Jane Street Talk on Youtube. 




