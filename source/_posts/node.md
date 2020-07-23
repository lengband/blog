# Node 随笔

## 问题记录

#### node.js里面 buffer.readUInt16BE 是什么意思，下面的数字是如何得来的？
```javascript
var buffer2=Buffer.alloc(4);
buffer2[0]=0x3;
buffer2[1]=0x4;
buffer2[2]=0x23;
buffer2[3]=0x42;
console.log(buffer2.readUInt16BE(0)); // 772
console.log(buffer2.readUInt16LE(0)); // 1027
console.log(buffer2.readUInt16BE(1)); // 1059
console.log(buffer2.readUInt16LE(1)); // 8964
console.log(buffer2.readUInt16BE(2)); // 9026
console.log(buffer2.readUInt16LE(2)); // 16931
```

答：

> 注意 1byte(字节)=8bit(位/比特)

var buffer2=Buffer.alloc(4; //创建了4个byte的buffer
buffer2[0]=0x3; // 给第一个byte存入 16进制的3， 以下类似
buffer2[1]=0x4;
buffer2[2]=0x23;
buffer2[3]=0x42; // 此时存入之后， 在buffer里面就是 0x3, 0x4, 0x23, 0x42, 在内存里面以连续的4个byte存储， 在电脑里面就是一连串0和1 构成的数字 如0x3 就是 0000 0011, 而0x4 则是 0000 0100, 0x23 = 00100011, 0x42 = 01000010, 在内存里面连续方式存取就是00000011, 00000100, 00100011, 01000010
console.log(buffer2.readUInt16BE(0));  // 这个意思就是从左边开始第一个byte起读16位，然后转换为10进制正整数(unit), 也就是00000011,00000100（16进制就是0x0304）,
使用parseInt(‘0000001100000100’, 2) 就可以得到 772,  从第二个byte开始读就是00000100, 00100011， parseInt(‘0000010000100011’, 2) === 1059

console.log(buffer2.readUInt16LE(0)); //这个就是从右边开始读16位然后转换为10进制正整数(unit)， 也就是00000011,00000100, 00100011, 01000010中从0位开始先取16个数字， 00000011,00000100, 然后右边的一个byte当做数字的高位， 也就是parseInt(‘0000010000000011’, 2) === 1027

readUInt16BE(1) 其中的参数 1 表示offset(偏移量)，也就是说偏移1位，那么取的值就是 00000100, 00100011, 0000010000100011转换为二进制就是 1059, 其它同理

le 和be是指 little endian, big endian, 中文应该是大端小端， 搞出这种区别是因为cpu的设计者各自设计自己的，然后互相不屌对方， 没有统一起来，intel是小的， 摩托罗拉和IBM是大的，各自有自己的考虑和实现，放在nodejs这里大小端是为了方便和不同编码的数据交换。

#### centos7上面通过yum安装的node版本过低，怎么升级？
<!-- 1.  -->
**查看nodejs版本**

　　$ node -v

**清除nodejs缓存**

　　$ npm cache clean -f

**升级node**

　　1. 安装nodejs管理工具 n

　　$ npm install -g n

　　2. 切换已安装版本

　　$ n

　　3. 安装稳定官方版本

　　$ n stable

　　4. 安装指定版本

　　$ n 8.11.3

　　5. 安装最新的LTS官方版本

　　$ n lts