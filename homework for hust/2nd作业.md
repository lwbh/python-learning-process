

```python
# -*- coding: utf-8 -*-
# 第二次作业by lwb
```


```python
'''只含c参数的传递'''
def fuc1(x,y):
    s=x+y
    return s

z=fuc1(1,2)
print(z)
```

    3
    


```python
'''位置和关键词的传递'''
def fuc2(loc,name,*,x1,y1):
    print(loc)
    print(name)
    print(x1+y1)
    return
z1=fuc2(12,13,x1=2,y1=2)
```

    12
    13
    4
    


```python
'''默认关键词的传递'''
def fuc3(*,x2,y2):
  
    print(x2+y2)
    return
z1=fuc3(x2=2,y2=5)
```

    7
    


```python
"定义不定长参数函数，计算----"
import math
def numFun(*numbers):
    if numbers:
        firstList = numbers[0]
        sumnum = sum(firstList)
        maxnum = max(firstList)
        minnum = min(firstList)
        avernum = sum(firstList)/len(firstList)
       
        total = 0
        for value in numbers[0]:
           total += (value - avernum) ** 2
        stddev = math.sqrt(total/len(firstList))
        print(stddev)
 
        print("输入数据：", firstList)
        print('和为：', sumnum, '平均值', avernum, '最大值', maxnum, '最小值', minnum )
        print("方差为",stddev)
 
if __name__ == '__main__':
    numbers = input("请输入一串数字")
    numbers = numbers.split(',')
    for x in range(len(numbers)):
        numbers[x] = int(numbers[x])
    print(numbers)
    numFun(numbers)

```

    请输入一串数字12,13,14
    [12, 13, 14]
    0.816496580927726
    输入数据： [12, 13, 14]
    和为： 39 平均值 13.0 最大值 14 最小值 12
    方差为 0.816496580927726
    


```python
'''recording information'''
def student(**kwargs):
    for key,items in kwargs.items():
        print(key,':',items)
        
student(hobby='playing games',name='LWB',cardNumber='U201610052')
```

    hobby : playing games
    name : LWB
    cardNumber : U201610052
    


```python

```
