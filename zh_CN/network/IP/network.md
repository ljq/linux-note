# network 网段分类

## IP地址分类

### IP地址分类 / IP地址10开头和172开头和192开头的区别 / 判断是否同一网段

简单来说在公司或企业内部看到的就基本都是内网IP，ABC三类IP地址里的常见IP段。

每个IP地址都包含两部分，即网络号和主机号。 


### InterNIC将IP地址分为五类:
    A类保留给ZF或大型企业;

    B类分配给中等规模的公司;

    C类分配给小公司或个人;

    D类用于组播;

    E类用于实验;

    注：各类可容纳的地址数目不同。


### A、B、C三类IP地址的特征：
当将IP地址写成二进制形式时

A类地址的第一位总是O，如，10.0.0.1==00001010-00000000-00000000-00000001
==》1.0.0.0-127.255.255.255，默认子网掩码为255.0.0.0，最多可容纳16777215台计算机

B类地址的前两位总是10，如，172.16.0.1==10101100-00010000-00000000-00000001
==》128.0.0.0-191.255.255.255，默认子网掩码为255.255.0.0，最多可容纳65535台计算机

C类地址的前三位总是110。如，192.168.0.1==11000000-10101000-00000000-00000001
==》192.0.0.0-223.255.255.255，默认子网掩码是255.255.255.0，最多可容纳254台计算机


### IP地址中保留地址：
    主机部分全为0的IP地址保留用于网络地址，主机部分全为1的IP地址保留为广播地址，224--255部分保留作为组播和实验目的。 同时注意IP地址分配时不能使用最末位为0和255的地址，因为这是广播地址，普通计算机上不能使用，但可用于网关和路由器上。


### 专用IP地址： 
    就是我们在3类地址中常见到内网的IP段。

    10.0.0.0--10.255.255.255

    172.16.0.0--172.31.255.255 

    192.168.0.0--192.168.255.255 

    内网的计算机以NAT（网络地址转换）协议，通过一个公共的网关访问Internet。内网的计算机可向Internet上的其他计算机发送连接请求，但Internet上其他的计算机无法向内网的计算机发送连接请求。


### 主机地址种类

概述
　　通过IP地址的引导位(最高位)来区分不同类别的IP地址：

　　注：n为网络编号位，h为主机编号位


A类地址
　　A类地址：0nnnnnnn.hhhhhhhh.hhhhhhhh.hhhhhhhh

    A类地址具有7位网络编号，因此可定义126个A类网络{2^7－2(网络编号不能是全0或全1 注1)-1(127为环回地址 注2)}每个网络可以拥有的主机数为16777214{2^24-2(主机位不能是全0或全1)}

　　十进制表示范围：1.0.0.1-126.255.255.254,任何一个0到127间的网络地址均是一个A类地址。


B类地址
　　B类地址：10nnnnnn.nnnnnnnn.hhhhhhhh.hhhhhhhh

　　B类地址具有14位网络编号，因此可定义16382个B类网络{2^14-2}

　　每个网络可以拥有的主机数为65534{2^16-2}

　　十进制表示范围：129.0.0.1-191.255.255.254,任何一个128到191间的网络地址是一个B类地址。


C类地址
　　C类地址：110nnnnn.nnnnnnnn.nnnnnnnn.hhhhhhhh

　　C类地址具有21位网络编号，因此可定义2097152个C类地址{2^21-2}

　　每个网络可以拥有的主机数为254{2^8-2}

　　十进制表示范围：192.0.0.1-223.255.255.254,任何一个192到223间的网络地址是一个C类地址。


D类地址
　　D类地址：1110xxxx.xxxxxxxx.xxxxxxxx.xxxxxxxx

　　D类地址用于组播，前面4位1110引导，后面28位为组播地址ID。

　　十进制表示范围：224.0.0.0-239.255.255.255


E类地址
　　E类地址：总是以1111四位引导

　　E类地址用于研究用

　　十进制表示范围：240-

　　IP地址由InterNIC(因特网信息中心)统一分配，以保证IP地址的唯一性，但有一类IP地址是不用申请可直接用于企业内部网的，这就是Private Address，Private Address不会被INTERNET上的任何路由器转发，欲接入INTERNET必须要通过NAT/PAT转换，以公有IP的形式接入。

