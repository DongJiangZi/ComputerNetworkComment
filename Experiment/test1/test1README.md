# Test1

## Step

多组计算机连接同一交换机，由于交换机相连，各计算机必须处于同一网段之下，给各个计算机分配`IP`地址`192.168.1.xx`

![](images\Photo1.png)

首先，计算机之间互相发送PDU包，使得交换机保存各个计算机的MAC地址，例如PC1向PC4发送PDU

![Photo2](images\Photo2.png)

然后删除PC4，新建一个PC5，让交换机与PC5相连（端口是否与原端口相同结果一致），将PC5的IP地址设置为PC4的IP地址

## Conclusion

PC1缓存了PC4的MAC地址，向PC5转发PDU时，认为知道MAC地址，不发送ARP广播包，而是直接发送ICMP，交换机接收后，由于交换机相应端口被拔掉又重新接上，交换机未保存新接入设备的MAC地址，由于不知道目标MAC在哪个端口，交换机会直接广播ICMP包

![Photo3](images\Photo3.png)

