

```python
# -*- coding: utf-8 -*-
# 第三次作业by lwb
'''1.（1）分数及格的判断'''
score=59
if score>=90:
    print('A')
elif score>=80:
    print('B')
elif score>=70:
    print('C')
elif score>=60:
    print('D')
elif score<60:
    print('E')
    
```

    E
    


```python
'''(2)GPA calculating'''
try:
    score2=int(input('Please input your score:'))
except ValueError:
    print('Opps!Invalid!')
if score2>=90:
    print('Your GPA is 4.0!')
elif score2>=80:
    print('Your GPA is 3.0!')
elif score2>=70:
    print('Your GPA is 2.0!')
elif score2>=60:
    print('Your GPA is 1.0!')
elif score2<60:
    print('Your GPA is 0!')
          
```

    Please input your score:61
    Your GPA is 1.0!
    


```python
'''阶乘方法1'''
import time
start_time=time.time()
multi=1
o=int(input('please input the end '))
for n in range(1,o):
    multi=multi*n
    n=n+1
print(multi)


end_time=time.time()
run_time=end_time-start_time
print(run_time)

```

    please input the end 10
    362880
    8.592111587524414
    


```python
'''阶乘方法2'''
import time
start_time=time.time()
multi=1
n=1
o=int(input('please input the end '))
while n in range(1,o):
    multi=multi*n
    n=n+1
print(multi)


end_time=time.time()
run_time=end_time-start_time
print(run_time)

```

    please input the end 10
    362880
    4.150153636932373
    


```python
'''用户登陆界面'''
Username='LiuWenbo'
Password='asdfghjk'
num=1
for num in range(1,5):
    u1=input('Username:')
    u2=input('Password')
    if u1==Username:
        if u2==Password:
            print('Congratulations!')
            break
        else:
            print('Wrong!')
            num=num+1
    else:
        print('Wrong!')
        num=num+1

```

    Username:LiuWenbo
    Passwordasdfghjk
    Congratulations!
    


```python
'''乘法口诀表'''
for i in range(1, 10):
    print()
    for j in range(1, i+1):
        print("%d * %d = %d" % (i, j, i * j))
```

    
    1 * 1 = 1
    
    2 * 1 = 2
    2 * 2 = 4
    
    3 * 1 = 3
    3 * 2 = 6
    3 * 3 = 9
    
    4 * 1 = 4
    4 * 2 = 8
    4 * 3 = 12
    4 * 4 = 16
    
    5 * 1 = 5
    5 * 2 = 10
    5 * 3 = 15
    5 * 4 = 20
    5 * 5 = 25
    
    6 * 1 = 6
    6 * 2 = 12
    6 * 3 = 18
    6 * 4 = 24
    6 * 5 = 30
    6 * 6 = 36
    
    7 * 1 = 7
    7 * 2 = 14
    7 * 3 = 21
    7 * 4 = 28
    7 * 5 = 35
    7 * 6 = 42
    7 * 7 = 49
    
    8 * 1 = 8
    8 * 2 = 16
    8 * 3 = 24
    8 * 4 = 32
    8 * 5 = 40
    8 * 6 = 48
    8 * 7 = 56
    8 * 8 = 64
    
    9 * 1 = 9
    9 * 2 = 18
    9 * 3 = 27
    9 * 4 = 36
    9 * 5 = 45
    9 * 6 = 54
    9 * 7 = 63
    9 * 8 = 72
    9 * 9 = 81
    


```python
'''输入一行字符，统计该字符中含有的英文字母、空格、数字和其他字符的个数'''
a=input('Please input something!')
alphaNum=0
numbers=0
spaceNum=0
otherNum=0
for i in a:
    if i.isalpha():
        alphaNum +=1
    elif i.isnumeric():
        numbers +=1
    elif i.isspace():
        spaceNum +=1
    else:
        otherNum +=1
print('字母=%d'%alphaNum)
print('数字=%d'%numbers)
print('空格=%d'%spaceNum)
print('其他=%d'%otherNum)
```

    Please input something!There are 25 pigs in your room!
    字母=22
    数字=2
    空格=6
    其他=1
    


```python

```
