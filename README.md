# STP 生成树 Spanning Tree Protocol
BID=桥ID 
大小  8字节   优先级占2字节  MAC地址占6字节

根交换机的选举(根桥)RB  
RB的选举根据桥的优先级+MAC地址大小   优先级默认32768  MAC则越小越优先 拥有最小BID的选举为根交换机
根端口选举(RP)
RP的选举在非根交换机上进行
