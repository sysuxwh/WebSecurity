# WebSecurity-DES
Implementation of Data Encryption Standard (DES) in C

## 算法原理概述

### 1. 什么是对称加密算法

> 对称密码算法有时又叫传统密码算法、秘密密钥算法或单密钥算法。对称密码算法的加密密钥能够从解密密钥中推算出来，反过来也成立。在大多数对称算法中，加密解密密钥是相同的。它要求发送者和接收者在安全通信之前，商定一个密钥。对称算法的安全性依赖于密钥，泄漏密钥就意味着任何人都能对消息进行加密解密。只要通信需要保密，密钥就必须保密。

### 2. 对称密码常用的数学运算
对称密码当中有几种常用到的数学运算。这些运算的共同目的就是把被加密的明文数码尽可能深地打乱，从而加大破译的难度。

>   ◆移位和循环移位  
　　移位就是将一段数码按照规定的位数整体性地左移或右移。循环右移就是当右移时，把数码的最后的位移到数码的最前头，循环左移正相反。例如，对十进制数码12345678循环右移1位（十进制位）的结果为81234567，而循环左移1位的结果则为23456781。    
◆置换  
　　就是将数码中的某一位的值根据置换表的规定，用另一位代替。它不像移位操作那样整齐有序，看上去杂乱无章。这正是加密所需,被经常应用。    
◆扩展  
　　就是将一段数码扩展成比原来位数更长的数码。扩展方法有多种,例如,可以用置换的方法，以扩展置换表来规定扩展后的数码每一位的替代值。    
◆压缩  
　　就是将一段数码压缩成比原来位数更短的数码。压缩方法有多种，例如，也可以用置换的方法，以表来规定压缩后的数码每一位的替代值。    
◆异或  
　　这是一种二进制布尔代数运算。异或的数学符号为⊕ ，可以简单地理解为，参与异或运算的两数位如相等，则结果为0，不等则为1。    
◆迭代  
　　迭代就是多次重复相同的运算，这在密码算法中经常使用，以使得形成的密文更加难以破解。


### 3.DES算法简介
DES是Data Encryption Standard（数据加密标准）的缩写。它是由IBM公司研制的一种对称密码算法，美国国家标准局于1977年公布把它作为非机要部门使用的数据加密标准，三十年来，它一直活跃在国际保密通信的舞台上，扮演了十分重要的角色。

DES是一个分组加密算法，典型的DES以64位为分组对数据加密，加密和解密用的是同一个算法。它的密钥长度是56位（因为每个第8 位都用作奇偶校验），密钥可以是任意的56位的数，而且可以任意时候改变。其中有极少数被认为是易破解的弱密钥，但是很容易避开它们不用。所以保密性依赖于密钥。

DES加密的算法框架如下：
　

> 首先要生成一套加密密钥，从用户处取得一个64位长的密码口令，然后通过等分、移位、选取和迭代形成一套16个加密密钥，分别供每一轮运算中使用。
> 
> DES对64位(bit)的明文分组M进行操作，M经过一个初始置换IP，置换成m0。将m0明文分成左半部分和右半部分m0 = (L0，R0)，各32位长。然后进行16轮完全相同的运算（迭代），这些运算被称为函数f，在每一轮运算过程中数据与相应的密钥结合。
> 
> 在每一轮中，密钥位移位，然后再从密钥的56位中选出48位。通过一个扩展置换将数据的右半部分扩展成48位，并通过一个异或操作替代成新的48位数据，再将其压缩置换成32位。这四步运算构成了函数f。然后，通过另一个异或运算，函数f的输出与左半部分结合，其结果成为新的右半部分，原来的右半部分成为新的左半部分。将该操作重复16次。
> 
> 经过16轮迭代后，左，右半部分合在一起经过一个末置换（数据整理），这样就完成了加密过程。

加密流程图：

DES有一个非常有用的性质：加密和解密使用相同的算法！DES加密和解密唯一的不同是密钥的次序相反。如果各轮加密密钥分别是K1，K2，K3…K16，那么解密密钥就是K16，K15，K14…K1。这也就是DES被称为对称算法的理由。

---

## 总体结构

---

## 模块分解

---

## 数据结构 

---

## C语言源代码

--- 

## 编译运行结果


---
参考链接：https://www.jianshu.com/p/c44a8a1b7c38


