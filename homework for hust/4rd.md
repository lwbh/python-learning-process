
##简述list和tuple两种数据类型的共同点和差异

#共同点
    二者都可以存放多个或多组数据
##差异
    list中的数据可以进行编辑处理，TUPLE中的元素是不可变的


```python
# -*- coding: utf-8 -*-
#第四次作业 by lwb
print(dir([list]))
```

    ['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
    

<br/>append:对list中的元素进行扩充
<br/>insert：在list中插入元素
<br/>pop:删除提取list中的元素
<br/>reverse:反转list中元素的顺序
<br/>count：显示list中元素的个数
<br/>list.remove(x):移除list中第一个值为x的元素



```python
# -*- coding: utf-8 -*-
#第四次作业bylwb
#L1和L2共有的元素
L1=[1,4,5,7,9,12]
L2=[4,6,8,9,11]
C=[]
for i in range(6):
    for j in range(5):
        if L1[i]==L2[j]:
            C.append(L1[i])
print(C)
#L1独有的元素
for h in range(len(C)):
    L1.remove(C[h])
print(L1)
#L1中元素在L2中的位置
pos=[]
for h in range(len(C)):
    
   pos.append(L2.index(C[h]))
print("L1中元素在L2中的位置",pos)
```

    [4, 9]
    [1, 5, 7, 12]
    L1中元素在L2中的位置 [0, 3]
    


```python
# -*- coding: utf-8 -*-
#第四次作业bylwb
#压缩L
L=[1,1,2,3,4,4,4,7,7,7,7,9,10,10,10]
P=[1]
Z=[]
j=0
for i in range(len(L)-1):
    if L[i]==L[i+1]:
        
        P[j]=P[j]+1
        i=i+1
    else:
        Z.append(L[i])
        Z.append(P[j])
        P.append(1)
        i=i+1
        j=j+1
print(Z)
a=len(L)
b=len(Z)
if a==b:
    print('压缩前后长度不变,',"L1's length is:",a,";L2's length is:",b)
elif a<b:
    print('压缩后长度增加,',"L1's length is:",a,";L2's length is:",b)
elif a>b:
    print('压缩后长度减小,',"L1's length is:",a,";L2's length is:",b)
```

    [1, 2, 2, 1, 3, 1, 4, 3, 7, 4, 9, 1]
    压缩后长度减小, L1's length is: 15 ;L2's length is: 12
    


```python
#解压缩Y
Y=[1,2,2,1,3,1,4,3,7,4,9,1,10,3]
P=[]
d=len(Y)

i=0
while i<d:
    c=Y[i+1]
    j=0 
    while j<c:
        P.append(Y[i])
        j=j+1
    i=i+2
print(P)
```

    [1, 1, 2, 3, 4, 4, 4, 7, 7, 7, 7, 9, 10, 10, 10]
    


```python

```
