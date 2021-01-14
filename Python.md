# Python

Python basic codes for practice

## 0 安装

直接到官网下载安装包，如果是Windows用户，建议下载3以上，3.7以下版本，便于之后安装numpy等模块。安装完毕之后点击File，创建一个脚本。

官网链接<https://www.python.org/>

## 1 基本操作

### 1）基本使用

+ print

  ```
  print("I am Erin.")
  print('I am Erin.')
  print("I'm Erin.")
  print('I\'m Erin.')#如果字符串中需要输出单引号，前面要加反斜杠
  print('Apple'+'10')
  print('Apple'+str(10))
  print(1+2)
  print('1+2')
  print(int('1')+2)
  print(float('1.2')+2)
  ```

+ 数学运算

  ```python
  2**3 #计算2的三次方
  8%3 #8除以3的余数
  9//4 #9除以4取整
  ```

+ variable

  ```
  a=3
  b,c,d=4,5,6
  e=a*3
  ```

+ while

  ```
  i=1
  while i<10:
      print(i)
      i=i+1
  ```

+ for

  ```
  example_list[1,2,5,7,9,134]
  for i in example_list:
      print(i)
  for j in range(1,10): #是从1到9
      print(i)
      
  for k in range(1,7,2): #2是步长
      print(k)
  ```

+ if

  ```
  x,y,z=1,2,3
  if x<y:
      print(x)
  if x<y<z:
      print('Yes')
  if x<y>z:
      print('y is the best')
  if x<=y:
      print('x is not better than y')
  if x==y:
      print('x is equal to y')
  if x!=y:
      print('x is not equal to y')
  ```

+ if else

  ```
  if x>y:
      print(x)
  else:
      print(y)
  ```

+ if  elif  else

  ```
  if x>y:      #会在满足第一个条件后跳出判断
      print(x)
  elif x>z:
      print(x)
  else:
      print(y)
  ```

+ def

  ```
  def function():#没有参数
  def fun(a,b):
      c=a*b
      print('the c is',c)
  def sale_car(price,color='red'):
      print('price:',price,'color:',color)
  sale_car(12300,color='bule')
  #可以修改默认参数，没有默认值的参数要放在有默认值的参数前面，可以不用输入默认值
  ```

+ 全局变量&局部变量

  ```
  def fun():
      a=10
      print(a)
      return a+100
  print(fun())#调用函数并输出函数的返回值
  ```

  ```
  APPLE=100 #全局变量一般用大写
  a=None
  def fun():
      global a
      a=20
      return a+20
  print(APPLE)
  print(a)#修改前a=None
  print(fun())#调用函数,并输出40
  print(a)#修改后a=20
  ```

+ file

  ```
  text='This is a line.\nThis is the next line.'
  print(text)
  
  myfile=open('myfile.txt','w')#如果没有这个文件，会自动创建
  myfile.write(text)
  myfile.close()
  
  myfile=open('myfile','a')#append
  
  file=open('myfile.txt','r')
  content=file.read()
  print(content)
  
  #读取后放到list列表里
  content=file.readline()#只读一行
  content=file.readlines()#全部读入
  ```

+ class

  ```
  class Calculator:  #一般把类的第一个字母大写
      name='Good Calculater'
      price=55
      def add(self,x,y):
          print(self.name)
          redult=x+y
          print(result)
      def minus(self,x,y)
          print(x-y)
      def times(self,x,y)
          print(x*y)
      def divide(self,x,y)
          print(x/y)
      
  #运行之后可以进行操作
  >>>calcul=Calculator()#calcul是个体，Calculator是类型
  >>>calcul.name
  >>>calcul.add(12,56)
  ```

  ```
  #init
  class Calculator:
      price=34#固有属性
      def_init_(self,name,price,hight)#自定义属性,如果在这里写hight=12,运行后就不用输入
      self.name=name
      self.price=price
      self.h=hight
  #运行后
  >>>c=Calculator('Good',23,12)
  ```

+ input

  ```
  a_input=input('Please give a number:')#把用户输入值存到a_input中，input的返回值是字符串
  print('This number is:',a_input)
  #以下用来检验你的代码是否正确
  if a_input=='1':
      print('This is a good one.')
  elif a_input==str(2):
      print('See you next time.')
  else:
      print('Good luck.')
  
  #也可以使用强制类型转换
  int(input('Please give a number:'))
  ```

+ 元组

  ```python
  a_tuple=(1,2,7,8,9)
  another_tuple=2,5,7,8
  ```

- 列表

  ```
  a_list=[1,2,4,5,5,6]#标号从0开始，同C语言数组
  for content in a_list:
      print(content)
      
  for index in range(len(a_list)):
      print('index=',index,'number=',a_list[index])
  ```

  ```
  #append
  a=[1,1,2,3,3]
  a.append(0)#插在队尾
  ```

  ```
  #insert
  a.insert(1,0)#第一个是位置，第二个是数值
  ```

  ```
  #remove
  a.remove(1)#把第一次出现的这个值删去
  ```

  ```
  #print
  print(a[0])
  print(a[-1])#打印最后一个数
  print(a[0:3])#打印a[0],a[1],a[2]
  print(a[:3])#从第一个开始，0可以省略
  print(a[-3:])#从倒数第三个开始到最后一个
  ```

  ```
  #index
  a.index(3)#输出第一次出现3的位置
  ```

  ```
  #count
  a.count[3]#计算出现了几次3
  ```

  ```
  #sort
  a.sort()#把列表从小到大排序，且覆盖原来的列表
  a.sort(reverse=Ture)#从大到小排序
  ```

  ```
  #多维列表
  multi_a[[1,2,3]
          [4,5,6]
          [7,8,9]]
  print(multi_a[0][1])#输出2
  ```

- 字典

  ```
  #定义
  d1={'apple':1,'pear':2}
  d2={1:'a',2:'b'}
  print(d1['apple'])#输出1
  ```

  ```
  #删除
  del d1['pear']
  ```

  ```
  #增加
  d1['b']=20
  ```

  ```
  #字典是无序的，且可以嵌套
  d={'apple':[1,2,3],'pear':{1:3,3:'a'},'banana':2}
  print(d['pear'][3])#输出a
  ```

---



### 2）模块

- import模块

  ```
  import time
  print(time.localtime())
  ```

  ```
  import time is t
  print(t.localtime())
  ```

  ```
  #只要time和localtime这两个功能
  from time import time,localtime
  print(localtime())
  print(time())
  ```

  ```
  #调出time的全部功能
  from time import *
  print(localtime())
  print(time())
  ```

- 自己的模块

  把m1和p1放到同一个文件夹下

  ```
  #m1中
  def printdata(data):
      print('I am m1.')
      print(data)
  ```

  ```python
  #p1中
  import m1
  m1.printdata('I am p1.')
  ```

---



### 3）其他

- continue&break

  ```
  #break
  while True:
      b=input('type sth:')
      if b=='1':
          break
      else:
          pass
      print('still in while')
  print('finish run')
  ```

  ```
  #continue
  while True:
      b=input('type sth:')
      if b=='1':
          continue
      else:
          pass
      print('still in while')
  print('finish run')
  ```

- zip,lambda,map

  ```
  #zip
  a=[1,2,3]
  b=[4,5,6]
  list(zip(a,b))#可视化
  
  for i,j in zip(a,b):
      print(i/2,j*2)
  #可以zip多个列表
  ```

  ```
  #lambda 就是简单的def
  fun2=lambda x,y:x+y
  fun2(3,4)#可以输出7
  ```

  ```
  #map
  def fun1(x,y):
      return(x+y)
  map(fun1,[1],[2])#输入数据要是列表的形式
  list(map(fun1,[1,3],[2,5]))#输出[3,8]
  ```

- copy&deepcopy

  ```
  import copy
  a=[1,2,[3,4]]
  b=a  #id(a)==id(b)
  c=copy.copy(a)  #id(a)!=id(c),id(a[2])==id(c[2]),浅复刻
  d=copy.deepcopy(a)  #id(a)!=id(d),id(a[2])!=id(d[2]),深层复刻
  ```

- pickle存放数据

  ```
  import pickle
  a_dict={'da':111,2:[23,1,4],'23':{1:2,'d':'happy'}}
  file=open('pickle_example.pickle','wb')#用二进制存储
  pickle.dump(a_dict,file)
  file.close()
  
  file=open('pickle_example.pickle','rb')
  a_dict1=pickle.load(file)
  file.close
  ```

  ```
  #用with可以自动关闭文件
  with open('pickle_example.pickle','rb') as file:
      a_dict2=pickle.load(file)
  ```

- set

  ```
  char_list=['a','a','b','c','c','d','d','d']
  print(set(char_list))#输出删去重复字符后的结果，无序，是set类型
  sentence='Welcome back to this tutorial'
  print(set(sentence))
  unique_list=set(char_list)
  unique_list.add('x')#添加字符x，不能添加list
  unique_list.clear()#清除
  unique_list.remove('x')
  
  set1=unique_list
  set2={'a','e','i'}
  print(set1.difference(set2))#set1-set2
  print(set1.intersection(set2))#set1∩set2
  ```

- RegEx正则表达

  ```
  import re
  ```

  ```
  #matching string 简单匹配
  pattern1="cat"
  pattern2="bird"
  string="dog runs to cat"
  print(re.search(pattern1,string))#输出Ture
  print(re.search(pattern2,string))#输出False
  ```

  *<re.Match object; span=(12, 15), match='cat'>*
  *None*

  ```
  #multiple patterns("run"or"ran")
  ptn=r"r[au]n"
  print(re.search(ptn,"dog runs to cat"))
  ```

  *<re.Match object; span=(4, 7), match='run'>*

  ```
  #多种匹配
  print(re.search(r"r[A-Z]n","dog runs to cat"))
  print(re.search(r"r[a-z]n","dog runs to cat"))
  print(re.search(r"r[0-9]n","dog r1ns to cat"))
  print(re.search(r"r[0-9 a-z]n","dog runs to cat"))
  ```

  *None*
  *<re.Match object; span=(4, 7), match='run'>*
  *<re.Match object; span=(4, 7), match='r1n'>*
  *<re.Match object; span=(4, 7), match='run'>*

  ```
  #\d:decimal digit 全部数字
  print(re.search(r"r\dn","run r4n"))
  #\D:any non-decimal digit
  print(re.search(r"r\Dn","run r4n"))
  ```

  *<re.Match object; span=(4, 7), match='r4n'>*
  *<re.Match object; span=(0, 3), match='run'>*

  ```
  #\s:any white space [\t\n\r\f\v]
  print(re.search(r"r\sn","r\nn r4n"))
  #\S:opposite to \s,any non-white space
  print(re.search(r"r\Sn","r\nn r4n"))
  ```

  *<re.Match object; span=(0, 3), match='r\nn'>*
  *<re.Match object; span=(4, 7), match='r4n'>*

  ```
  #\w:[a-zA-Z0-9]
  print(re.search(r"r\wn","r\nn r4n"))
  #\W:opposite to \w
  print(re.search(r"r\Wn","r\nn r4n"))
  ```

  *<re.Match object; span=(4, 7), match='r4n'>*
  *<re.Match object; span=(0, 3), match='r\nn'>*

  ```
  #\b:empty string(only at the start or end of the word)
  print(re.search(r"\bruns\b","dog runs to cat"))
  #\B:empty string(but not at the start or end of the word)
  print(re.search(r"\B runs \B","dog   runs  to cat"))
  ```

  *<re.Match object; span=(4, 8), match='runs'>*
  *<re.Match object; span=(5, 11), match=' runs '>*

  ```
  #\\:match \
  print(re.search(r"runs\\","runs\ to cat"))
  #.:match anything except \n
  print(re.search(r"r.n","r[n to me"))
  ```

  *<re.Match object; span=(0, 5), match='runs\\'>*
  *<re.Match object; span=(0, 3), match='r[n'>*

  ```
  #^:match line beginning
  print(re.search(r"^dog","dog runs to cat"))
  #$:match line ending
  print(re.search(r"cat$","dog runs to cat"))
  ```

  *<re.Match object; span=(0, 3), match='dog'>*
  *<re.Match object; span=(12, 15), match='cat'>*

  ```
  #?:may or may not occur
  print(re.search(r"Mon(day)?","Monday"))
  print(re.search(r"Mon(day)?","Mon"))
  ```

  *<re.Match object; span=(0, 6), match='Monday'>*
  *<re.Match object; span=(0, 3), match='Mon'>*

  ```
  #multi-line 多行匹配
  string="""
  dog runs to cat
  I run to dog.
  """
  print(re.search(r"^I",string))
  print(re.search(r"^I",string,flags=re.M))
  ```

  *None*
  *<re.Match object; span=(17, 18), match='I'>*

  ```
  #*:occur 0 or more times 出现0次或多次
  print(re.search(r"ab*","a"))#b出现0次
  print(re.search(r"ab*","abbbbbb"))#b出现多次
  ```

  *<re.Match object; span=(0, 1), match='a'>*
  *<re.Match object; span=(0, 7), match='abbbbbb'>*

  ```
  #+:occur 1 or more times 出现1次或多次
  print(re.search(r"ab+","a"))
  print(re.search(r"ab+","abbbbbb"))
  ```

  *None*
  *<re.Match object; span=(0, 7), match='abbbbbb'>*

  ```
  #{n,m}:occur n to m times  出现次数可选
  print(re.search(r"ab{2,10}","a"))
  print(re.search(r"ab{2,10}","abbbbb"))
  ```

  *None*
  *<re.Match object; span=(0, 6), match='abbbbb'>*

  ```
  #group
  match=re.search(r"(\d+),Date:(.+)","ID:021523,Date:Feb/01/2021")
  print(match.group())
  print(match.group(1))
  print(match.group(2))
  ```

  *021523,Date:Feb/01/2021*
  *021523*
  *Feb/01/2021*

  ```
  #将group中的每一个括号命名
  match=re.search(r"(?P<id>\d+),Date:(?P<date>.+)","ID:021523,Date:Feb/01/2021")
  print(match.group('id'))
  print(match.group('date'))
  ```

  *021523*
  *Feb/01/2021*

  ```
  #findall  寻找所有匹配，全部输出
  print(re.findall(r"r[ua]n","run ran ren"))
  ```

  *['run', 'ran']*

  ```
  #|:or
  print(re.findall(r"(run|ran)","run ran ren"))#匹配的是括号里的内容
  ```

  *['run', 'ran']*

  ```
  #re.sub() replace 替换
  print(re.sub(r"r[au]ns","catches","dog runs to cat"))
  ```

  *dog catches to cat*

  ```
  #re.split() 分裂
  print(re.split(r"[,;\.]","a;b,c.d;e"))
  ```

  *['a', 'b', 'c', 'd', 'e']*

  ```
  #compile 先编译
  compiled_re=re.compile(r"r[ua]n")
  print(compiled_re.search("dog ran to cat"))
  ```

  *<re.Match object; span=(4, 7), match='ran'>*

---

### 4）最后

如果想要查看完整讲解视频，请点击<https://mofanpy.com/tutorials/python-basic/basic/>
