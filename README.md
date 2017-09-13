# STP 生成树 Spanning Tree Protocol
BID=桥ID 
大小  8字节   优先级占2字节  MAC地址占6字节
MAC地址比较    00:01:10:00:11:11 和 00:10:00:00:00:00   前者比后者要小

根交换机的选举(根桥)RB  
RB的选举根据桥的优先级+MAC地址大小   优先级默认32768  MAC则越小越优先 拥有最小BID的选举为根交换机

根端口选举(RP)
RP的选举在非根交换机上进行

BPDU报文包含12个字段

    Flags:标记域,包含TC（Topology Change，拓扑改变）比特位，TCA(Topology Change Acknowledgment,拓扑改变确认)比特位。
    Root ID:包含了根交换机的BID。
    Cost of path:到根交换机的路径花费。
    Bridge ID:转发BPDU的交换机的BID。
    Port ID:转发BPDU的交换机的PID，PID等于端口优先级(默认128)加端口号，后面会介绍到。
    Message age:BPDU已经存在的时间。
    Max age:BPDU最大存在时间。
    Hello time:根交换机发送配置信息的间隔时间，默认2秒。
    Forward Delay:转发延时，默认15秒。
