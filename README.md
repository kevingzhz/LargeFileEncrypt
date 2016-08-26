# LargeFileEncrypt
实现大文件的加密解密功能，可以为任何二进制文件加密解密。

加密原理是一个二进制数与另一个二进制数与或一次后就是另一个数，与或两次后就是它本身。

步骤：
先定义一个共用的key
加密步骤：
先读取文件的前100个字符，与key进行与或操作，这个文件就加密了，为了标记该文件为加密状态，把key补文件的末尾。
解密步骤：
从文件中读取末位一个长度为key的长度字符串，然后与key进行对比，如果相同则为加密文件，否则为未加密文件，就不需要解密。
与key进行与或运算后，然后截取末尾长度未key的字符串后，所产生的新字符串就是未加密的源文件。