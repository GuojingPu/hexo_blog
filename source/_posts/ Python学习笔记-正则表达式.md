---
title: Python学习笔记-正则表达式
date: 2018-7-20 18:53:48
tags: [Python,正则表达式]
categories: python
copyright:
top: 99
---
&#8195;&#8195;
## 正则表达式
### 1.常用正则表达式符号和语法

1、'.' 匹配所有字符串，除\n以外
2、‘-’ 表示范围[0-9]
3、'\*' 匹配前面的子表达式零次或多次。要匹配 * 字符，请使用 \\\*。
4、'+' 匹配前面的子表达式一次或多次。要匹配 + 字符，请使用 \+
5、'\^' 匹配字符串开头
6、‘$’ 匹配字符串结尾 re
7、'\' 转义字符， 使后一个字符改变原来的意思，如果字符串中有字符 ' \* ' 需要匹配，可以使用' \\\* '或者字符集[ \*] , re.findall(r'3\*','3\*ds')结果['3*']
8、'\*' 匹配前面的字符0次或多次re.findall("ab\*","cabc3abcbbac")结果：['ab', 'ab', 'a']
9、‘?’ 匹配前一个字符串0次或1次 re.findall('ab?','abcabcabcadf')结果['ab', 'ab', 'ab', 'a']
10、'{m}' 匹配前一个字符m次 re.findall('cb{1}','bchbchcbfbcbb')结果['cb', 'cb']
11、'{n,m}' 匹配前一个字符n到m次 re.findall('cb{2,3}','bchbchcbfbcbb')结果['cbb']
12、'\d' 匹配数字，等于[0-9] re.findall('\d','电话:10086')结果['1', '0', '0', '8', '6']
13、'\D' 匹配非数字，等于[^0-9] re.findall('\D','电话:10086')结果['电', '话', ':']
14、'\w' 匹配字母和数字，等于[A-Za-z0-9] re.findall('\w','alex123,./;;;')结果['a', 'l', 'e', 'x', '1', '2', '3']
15、'\W' 匹配非英文字母和数字,等于[^A-Za-z0-9] re.findall('\W','alex123,./;;;')结果[',', '.', '/', ';', ';', ';']
16、'\s' 匹配空白字符 re.findall('\s','3\*ds \t\n')结果[' ', '\t', '\n']
17、'\S' 匹配非空白字符 re.findall('\s','3\*ds \t\n')结果['3', '\*', 'd', 's']
18、'\A' 匹配字符串开头
19、'\Z' 匹配字符串结尾
20、'\b' 匹配单词的词首和词尾，单词被定义为一个字母数字序列，因此词尾是用空白符或非字母数字符来表示的
21、'\B' 与\b相反，只在当前位置不在单词边界时匹配
22、'( ?P\<name\>... )' 分组，除了原有编号外再指定一个额外的别名。 re.search("(?P\<province>[0-9]{4})(?P\<city>[0-9]{2})(?P\<birthday\>[0-9{8})","371481199306143242").groupdict("city") 结果{'province': '3714', 'city': '81', 'birthday': '19930614'}
23、[ ] 是定义匹配的字符范围。比如 [a-zA-Z0-9] 表示相应位置的字符要匹配英文字符和数字。[\s\*]表示空格或者*号。

### 2.常用的re函数
re.match(pattern,string,flags=0)&#8195;&#8195;从字符串的起始位置匹配，如果起始位置匹配不成功的话，match()就返回none

re.search(pattern,string,flags=0)&#8195;&#8195;扫描整个字符串并返回第一个成功的匹配

re.findall(pattern,string,flags=0)&#8195;&#8195;找到RE匹配的所有字符串，并把他们作为一个列表返回

re.finditer(pattern, string, flags=0)&#8195;&#8195;找到RE匹配的所有字符串，并把他们作为一个迭代器返回

re.sub(pattern, repl, string, count=0, flags=0)#8195;&#8195;替换匹配到的字符串

re.subn(pattern, repl, string, count=0, flags=0)#8195;&#8195;替换匹配到的字符串,并返回替换数量



>>>>>未完待续...








