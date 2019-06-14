ASCII：单字节
GB2312：双字节
Unicode：通常双字节
utf-8：Unicode可变长度编码，英文、数字单字节，汉字3字节(生僻字4-6字节)

ord():获取字符的整数表示
	ord('A') =>65
chr():把编码转换为对应的字符
	chr(65) =>A

用中文字符16进制表示
	'\u4e2d\u6587' => 中文



Python的字符串类型是str，在内存中以Unicode表示，一个字符对应若干个字节。如果要在网络上传输，或者保存到磁盘上，就需要把str变为以字节为单位的bytes。
以Unicode表示的str通过encode()方法可以编码为指定的bytes
	'中文'.encode('utf-8')  => b'\xe4\xb8\xad\xe6\x96\x87'
	(汉字无法使用ASCII码)
从网络或磁盘上读取了字节流，那么读到的数据就是bytes。要把bytes变为str，就需要用decode()方法
	b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')  => 中文

	(如果bytes中包含无法解码的字节，decode()会报错，可以使用errors='ignore'忽略错误的字节)
	b'\xe4\xb8\xad\xff'.decode('utf-8', errors='ignore')  => '中'

字符串长度
len('')

bytes字节数
len(b'\xe4\xb8\xad\xe6\x96\x87')
6


.py文件标注使用utf-8
'#!/usr/bin/env python3'
'# -*- coding: utf-8 -*-'