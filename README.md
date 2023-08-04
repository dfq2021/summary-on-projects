# summary on projects
创新创业实践课project汇总报告

组号：22（共一人）

组员：戴方奇202100460092

下面的汇总报告中说明了每个project的方式、创新等，展示了部分实验结果，具体实验报告在每个project的readme文件中展示。
# Project1: implement the naïve birthday attack of reduced SM3
github地址：https://github.com/dfq2021/project

运行时间：100.61658000946045 s

project1用python语言实现一个reduced sm3算法，并且生成多个元素，然后通过reduced sm3算法加密后对比hash值，hash值相同，则找到了一对碰撞。

运行方式：直接在pycharm平台运行该py文件即可。

运行结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/5d1be250-4ab0-40d7-a16d-7f8d379dd9bf)


# Project2: implement the Rho method of reduced SM3
github地址：https://github.com/dfq2021/project-2

运行时间：0.788s

运行结果：
![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/08bc39e9-b5de-425a-a721-8c46af06fb4b)


与project1不同，project2选择用c++实现reduced sm3算法，再进行rho碰撞攻击，选择两个不同的随机输入，并用哈希函数进行迭代压缩。第一个输入每次迭代一次，第二个每次迭代两次，然后比较每次的hash输出，找到碰撞，这种方法减少了存储空间。

运行方式：直接运行其中的sm3.h、sm3.cpp、及rho_attack.cpp文件即可。

# Project3: implement length extension attack for SM3, SHA256, etc.

github地址：https://github.com/dfq2021/project-3

我们在知晓hash的信息长度前提之下，在信息之后填充一定数量的零，直达信息长度为分组长度的整数倍，然后再添加自定义的信息，根据MD结构，这样操作之后的信息的hash值可以由以原先信息的hash值作为IV，新自定义信息作为待hash信息得到。我们将这样操作之后得到的hash值与plaintext||000...000||data_append的hash值做对比，若相同，则说明正确。

运行时间：0.003s

运行结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/bc6d913f-005a-4a9b-a91a-b1ba4c1f7128)


运行方式：直接运行文件目录下的.cpp文件即可。

# Project4: do your best to optimize SM3 implementation (software)
github地址：https://github.com/dfq2021/project-4

采用了多种优化方式，优化后的sm3的运算时间几乎是和消息大小成正比的，消息越大，优化效果越明显，即缩短的运算时间就越多，效果越显著性价比越高。

实验结果：加密前时间：0.0083ms，加密后时间：0.001ms，调高了近8倍

运行方式：直接在vs2022平台运行即可，两个是、cpp文件，分别是优化前的sm3和优化后的sm3。
# Project5: Impl Merkle Tree following RFC6962

github地址：https://github.com/dfq2021/project-5

采用多种函数实现了Merkle Tree从生成到各种操作的函数，如创建、检查、验证等等。

实验结果：
![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/c538f19e-e911-43d4-a5cd-d280a3bae613)


其中生成一个100k数据的merkle tree 用时0.4s，给出节点的存在性证据用时0.001s，验证的时间可以忽略不计，很小。

运行方式： 直接在pycharm运行目录文件夹下的.py文件即可。

# Project6: impl this protocol with actual network communication

github地址：https://github.com/dfq2021/project-6

本次实验模拟了真实网络中该协议的实现，成Issuer、Alice、Bob三个角色实现各自的操作。

实验结果：（以Issuer为例）

![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/f6e1d994-0e5b-4e21-9502-de254d441e3c)


运行方式：分别运行目录文件夹中Issuer、Alice、Bob三个角色的py文件即可。

# Project7: Try to Implement this scheme
github地址：https://github.com/dfq2021/project-7

在本次实验中据线性同余法编写自己的KDF，同时实现shuffle()函数：根据一个shuffle种子，然后初始化随机数生成器，再使用random.shuffle()对哈希值列表进行shuffle。

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/9b464803-032e-46f2-8ee1-8133fdcc657d)

运行时间: 1.0006427764892578 ms

运行方式：直接运行文件中python文件可得到该hashwire的Root： b'\xb8\xb8( s\xad>)\n#\x1b[-\xad\x1cX9u2t\x89Z\xed.\x91\xed\x03J"\x1f\x94\xd6'
# Project9: AES / SM4 software implementation

github地址：https://github.com/dfq2021/project-9

按照1.字节处理、2.轮密钥扩展、3.字节代换、4.行位移、5.列混合、6.轮密钥异或六个步骤实现AES的各个部件，同时在各个部件完成了一定普适性优化，方便各种情况的应用。

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/b558eca9-84c3-4e74-a1c8-0214a0a96476)

运行方式：在vs平台直接运行文件中cpp文件即可。
# Project10: report on the application of this deduce technique in Ethereum with ECDSA

github地址：https://github.com/dfq2021/project-10

本次实验不仅按照算法原理、算法概述、算法与区块链关系描述了ECDSA，同时通过python实现了该算法的签名与验证。

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/4d24205a-4e11-45dc-a0c4-7ad8f08ce170)

1.签名算法用时： 0.0508275032043457 s

2.验证算法用时： 0.09291815757751465 s

运行方式：在pycharm平台直接运行文件中.py文件即可。

# Project11: impl sm2 with RFC6979

githu地址：https://github.com/dfq2021/project-11

本次实验先用Python语言实现了SM2算法，再令k=hash（随机数||ID||"算法类型"），符合RFC 6979的确定性随机数生成算法，以在不依赖真正随机数的情况下根据消息和私钥生成一系列伪随机数。

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/4d35791a-533b-43a4-8fbb-9ce95ed051fd)

运行时间：0.05s

运行方式：在pycharm平台直接运行文件中.py文件即可。

# Project12: verify the above pitfalls with proof-of-concept code

github地址：https://github.com/dfq2021/project-12

本次实验中分别验证了1.ECDSA、2.SM2、3.Schnorr三种算法体系中的pitfalls

每个算法验证的内容有：

1.泄露随机数k从而导致d泄露。

2.对不同的消息重用随机数k从而导致d泄露。

3.两个不同的用户使用同一个k，则其中一个人可以推出另一个人的私钥d。

4.可以(r,s) and (r,-s)均为有效签名，这可能会导致区块网络分裂。

5.使用相同的d和随机数k签发SM2和ECDSA或Schnorr和ECDSA，会导致d泄露。

实验结果： 由于验证的算法太多，在此就不再一一展示。

运行方式：在pycharm平台直接运行文件中各个.py文件即可验证对应算法的各种pitfalls。
# Project13: Implement the above ECMH scheme

github地址：https://github.com/dfq2021/project-13

ECMH通过把哈希映射成椭圆曲线上的点，然后利用ECC进行运算，可以把多个数据的 hash 合并到一个 hash 中，并且支持删除。这样节点维护一个 UTXO 的根 hash 的成本就很低了，每次只需做增量修改。然后只需要把 UTXO 根 hash 记录到区块上，其他节点同步 UTXO 集合之后，就可以验证该集合是否被篡改了。

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/3db4b7bb-57a7-4356-8597-e7007e0218c2)

运行时间：0.0010013580322265625 s

运行方式：在pycharm平台直接运行文件中.py文件即可。
# Project14: Implement a PGP scheme with SM2

github地址：https://github.com/dfq2021/project-14

本次实验中模拟了真实网络情况下发送方和接收方通过电子邮件发送信息时，PGP和公钥体系是如何为电子邮件提供保密性（Privacy)和认证性(Authentication）。

实验结果：

发送方：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/07415fd8-d23d-4476-b6cf-b98c43ca00f9)

接收方：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/234aa4dd-a297-452d-9a31-c5f0b1059ea1)

运行时间：从建立链接到接收并完成验证花费 0.1033620834350586 s

运行方式：直接在pycharm平台直接运行文件中两方的.py文件即可模拟。
# Project15: implement sm2 2P sign with real network communication

github地址：https://github.com/dfq2021/project-15

同时使用python中的网络链接代码库来模拟真实的网络连接中，客户端和服务器双方的签名和认证过程，完成基于SM2的两方协同签名方案在真实网络中实现。

实验结果：

客户端：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/1c8b48df-f00f-43da-8ce5-7bcb2121c4e1)


服务器：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/640f44ab-01cf-4678-95ab-bce5fe315397)

运行时间：运行速度：0.15194916725158691 s

运行方式：直接在pycharm平台直接运行文件中两方的.py文件即可模拟。
# Project16: implement sm2 2P decrypt with real network communication

github地址：https://github.com/dfq2021/project-16

同时使用python中的网络链接代码库socket库来模拟真实的网络连接中，客户端和服务器双方的传递参数，使得客户端与服务器在保存有各自的私钥分量的情况下，通过交换利用各自私钥得到的参数T1、T2，完成最终解密。

实验结果：

客户端：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/2809656e-4bf3-4797-83f6-32242b821576)

服务器：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/90672eb3-6a0f-4265-af89-11ccc400c53a)

运行时间：从建立链接到解密成功用时 0.07593750953674316 s

运行方式：直接在pycharm平台直接运行文件中两方的.py文件即可模拟。
# Project17：比较Firefox和谷歌的记住密码插件的实现区别

github地址：https://github.com/dfq2021/project-17

本次实验中不仅探讨Google和Firefox浏览器中的记住密码插件实现方式，并比较它们之间的区别，还用JavaScript分别具体实现了Google和Firefox的插件内容。

# Project18: send a tx on Bitcoin testnet, and parse the tx data down to every bit, better write script yourself
github地址：https://github.com/dfq2021/project-18

首先对比特币测试网交易信息中的一个交易进行分析，通过python脚本可以得到该交易的区块头、难度、时间戳、Merkle根输入、"preference"、"confirmed"、"received"、 等参数信息，然后将tx信息发送到指定网站，通过python脚本打印回复信息。

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/6db4a19d-fb24-4247-a63e-f6e86505cb9a)

运行方式：在pycharm平台直接运行文件中.py文件即可。

# Project19: forge a signature to pretend that you are Satoshi
github地址：https://github.com/dfq2021/project-19

通过理解Ecdsa验证原理：(eG+rP) = (x',y')=R',r'=x' mod n == r

为了伪造，我们可以选择u,v,计算R'=(x',y')=uG+vP，之后选择r'=x' mod n，计算：e'=r'uv' mod n以及s'=r'v' mod n，伪造即可完成

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/6fe546e7-b128-46af-bbe5-7f3823e6adb2)

运行时间：小于0.01s

运行方式：在pycharm平台直接运行文件中.py文件即可。
# Project21: Schnorr Bacth
github地址：https://github.com/dfq2021/project-21

本次实验中首先实现了实现离散对数的求解，素数和素因子的生成以及计算生成元，之后按照Schnorr签名算法方式，就可以在Schnorr.py文件实现该算法。

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/115515c0-8624-4e5d-bb5e-af5cb5a6cdf3)

运行时间：0.9977817535400391 ms

运行方式：直接用pycharm平台运行文件目录下的.py文件即可。

# Project22: research report on MPT
github地址：https://github.com/dfq2021/project-22

本次实验中从MPT的原理、MPT的优势、MPT的工作方式三个方面阐述了MPT的内容，同时通过c语言实现了MPT的创建、节点证明等

实验结果：![image](https://github.com/dfq2021/summary-on-projects/assets/129512207/e8abefee-342c-47e4-b719-3ff1b3a37603)

运行方式：直接用vs平台运行文件目录下的.cpp文件即可。
