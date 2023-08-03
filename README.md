# summary on projects
创新创业实践课project汇总报告
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
# Project7: Try to Implement this scheme
# Project8: AES impl with ARM instruction
# Project9: AES / SM4 software implementation
# Project10: report on the application of this deduce technique in Ethereum with ECDSA
# Project11: impl sm2 with RFC6979
# Project12: verify the above pitfalls with proof-of-concept code
# Project13: Implement the above ECMH scheme
# Project14: Implement a PGP scheme with SM2
# Project15: implement sm2 2P sign with real network communication
# Project16: implement sm2 2P decrypt with real network communication
# Project17：比较Firefox和谷歌的记住密码插件的实现区别
# Project18: send a tx on Bitcoin testnet, and parse the tx data down to every bit, better write script yourself
# Project19: forge a signature to pretend that you are Satoshi
# Project20: ECMH PoC
# Project21: Schnorr Bacth
# Project22: research report on MPT
