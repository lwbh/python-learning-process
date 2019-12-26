

```python
# -*- coding: utf-8 -*-
#第五次作业 by lwb
print(dir(dict))
```

    ['__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'clear', 'copy', 'fromkeys', 'get', 'items', 'keys', 'pop', 'popitem', 'setdefault', 'update', 'values']
    

<br/>**clear** *用于删除字典内所有元素。*
<br/>**copy** *返回一个字典的浅复制*
<br/>**get** *函数返回指定键的值。*
<br/>**keys** *以列表返回一个字典所有的键。*
<br/>**keys** *删除字典给定键 key 及对应的值,返回值为被删除的值。*
<br/>**values** *以列表形式,返回字典中所有的值*


```python
#小组信息
info_dict={'U201610052':'刘文博，信息与计算科学1601班 ','U201610053':'郜英涵，信息与计算科学1601班'}
print(info_dict)
```

    {'U201610052': '刘文博，信息与计算科学1601班 ', 'U201610053': '郜英涵，信息与计算科学1601班'}
    


```python
print(dir(set))
```

    ['__and__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__iand__', '__init__', '__init_subclass__', '__ior__', '__isub__', '__iter__', '__ixor__', '__le__', '__len__', '__lt__', '__ne__', '__new__', '__or__', '__rand__', '__reduce__', '__reduce_ex__', '__repr__', '__ror__', '__rsub__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__xor__', 'add', 'clear', 'copy', 'difference', 'difference_update', 'discard', 'intersection', 'intersection_update', 'isdisjoint', 'issubset', 'issuperset', 'pop', 'remove', 'symmetric_difference', 'symmetric_difference_update', 'union', 'update']
    

<br/>**clear** *用于删除集合内所有元素。*
<br/>**copy** *返回一个集合的浅复制*
<br/>**pop** *删除集合指定的值,返回值为被删除的值。*
<br/>**discard** *用于移除指定的集合元素*


```python
# -*- coding: utf-8 -*-
#第五次作业 by lwb

str1='CCACATCACTTACTACCCGGTCTCAATGGCCAACATGGAAATTAAGGCTTAACCGGCATTCAACGGCTTCCCACCGGATCTTACATGGATAACACTCGGTACCAACATGGTTTACCTCCGGCCACTCCTCGGAACAATACAGGTTATTACCCGGCATTTCCTTGGTAATATCCTGGCTTATTCAAGGCCTTCTCACGGTACCTAAATGGCTTTATTCCGGTTCTCAATTGGCCAATTCCAGGAATTCTCCCGGTAATCTAAAGGCACTTATTCGGTTCCTCCATGGTCCTTTACTGGCCTCCCCACGGTCCACATCTGGTTACTTATCGGCTCCTCCAAGGTATCTTATCGGACCACTCTCGGTCTCCCCTTGGCACAACACTGGTATACCAACGGCACTTTCTCGGATCACTCAAGGAACATAAAAGGTTCCCACTTGGTTCCTAACAGGATAATCATAGGCAACCCACAGGCCAAATTAAGGTCACCCAACGGAATTATCAAGGACATATCTTGGATAACCTTAGGTTCCTATACGGCCTTATCTTGGCTCATCTCTGGCATACTCCAGGCAATCATCCGGCTATAACCTGGTCCTAAATTGGTCAAACTTAGGATAATAAATGGCCTCTTAACGGATCCAAATAGGAACCCTCATGGACCCTTACTGGACCTAACACGGTTCCTCACAGGCTCTCATAAGGATCACCACTGGATCACTCATGGTATACCCTAGGTCAAATCTAGGCTTATATTAGGTAACAACCAGGTAATTCATCGGCCCTAAACCGGAATCATCCCGGACCACACACGGACTCATAATGGCAATTTACCGGTCTCCATAAGGCTCACTATAGGCCTCCCATCGGCATCTTCATGGAACCTCTTAGGACAAACCCAGGACACTCACAGGTCTTCTATTGGACCTTCATTGGAACCTTTCTGGAATCATACGGATCATATGGTAAACTAGGATCCCTAGGTATCACAACTACCTCACAAAAAAAAAA'
#字符串中长度为3的motify
l=[]
times=[]
for i in range(len(str1)-2):
    l.append(str1[i:i+3])
print(l) #把所有长度为3的碱基分离出来
id_set=set()
for j in range(len(l)):
    id_set.add(l[j])
print('降重后的集合为',id_set)#通过集合进行降重
id_list=list(id_set)
print('集合转为列表为',id_list)

i=j=0
for i in range(len(id_list)-1):
    k=0
    for j in range(len(l)):
        if l[j]==id_list[i]:
            k=k+1
    times.append(k)
print(times)
DNA3_dict={}
for key,value in zip(id_list,times):
    DNA3_dict[key]=value
print('字符串中长度为3motif以及出现次数为',DNA3_dict)
```

    ['CCA', 'CAC', 'ACA', 'CAT', 'ATC', 'TCA', 'CAC', 'ACT', 'CTT', 'TTA', 'TAC', 'ACT', 'CTA', 'TAC', 'ACC', 'CCC', 'CCG', 'CGG', 'GGT', 'GTC', 'TCT', 'CTC', 'TCA', 'CAA', 'AAT', 'ATG', 'TGG', 'GGC', 'GCC', 'CCA', 'CAA', 'AAC', 'ACA', 'CAT', 'ATG', 'TGG', 'GGA', 'GAA', 'AAA', 'AAT', 'ATT', 'TTA', 'TAA', 'AAG', 'AGG', 'GGC', 'GCT', 'CTT', 'TTA', 'TAA', 'AAC', 'ACC', 'CCG', 'CGG', 'GGC', 'GCA', 'CAT', 'ATT', 'TTC', 'TCA', 'CAA', 'AAC', 'ACG', 'CGG', 'GGC', 'GCT', 'CTT', 'TTC', 'TCC', 'CCC', 'CCA', 'CAC', 'ACC', 'CCG', 'CGG', 'GGA', 'GAT', 'ATC', 'TCT', 'CTT', 'TTA', 'TAC', 'ACA', 'CAT', 'ATG', 'TGG', 'GGA', 'GAT', 'ATA', 'TAA', 'AAC', 'ACA', 'CAC', 'ACT', 'CTC', 'TCG', 'CGG', 'GGT', 'GTA', 'TAC', 'ACC', 'CCA', 'CAA', 'AAC', 'ACA', 'CAT', 'ATG', 'TGG', 'GGT', 'GTT', 'TTT', 'TTA', 'TAC', 'ACC', 'CCT', 'CTC', 'TCC', 'CCG', 'CGG', 'GGC', 'GCC', 'CCA', 'CAC', 'ACT', 'CTC', 'TCC', 'CCT', 'CTC', 'TCG', 'CGG', 'GGA', 'GAA', 'AAC', 'ACA', 'CAA', 'AAT', 'ATA', 'TAC', 'ACA', 'CAG', 'AGG', 'GGT', 'GTT', 'TTA', 'TAT', 'ATT', 'TTA', 'TAC', 'ACC', 'CCC', 'CCG', 'CGG', 'GGC', 'GCA', 'CAT', 'ATT', 'TTT', 'TTC', 'TCC', 'CCT', 'CTT', 'TTG', 'TGG', 'GGT', 'GTA', 'TAA', 'AAT', 'ATA', 'TAT', 'ATC', 'TCC', 'CCT', 'CTG', 'TGG', 'GGC', 'GCT', 'CTT', 'TTA', 'TAT', 'ATT', 'TTC', 'TCA', 'CAA', 'AAG', 'AGG', 'GGC', 'GCC', 'CCT', 'CTT', 'TTC', 'TCT', 'CTC', 'TCA', 'CAC', 'ACG', 'CGG', 'GGT', 'GTA', 'TAC', 'ACC', 'CCT', 'CTA', 'TAA', 'AAA', 'AAT', 'ATG', 'TGG', 'GGC', 'GCT', 'CTT', 'TTT', 'TTA', 'TAT', 'ATT', 'TTC', 'TCC', 'CCG', 'CGG', 'GGT', 'GTT', 'TTC', 'TCT', 'CTC', 'TCA', 'CAA', 'AAT', 'ATT', 'TTG', 'TGG', 'GGC', 'GCC', 'CCA', 'CAA', 'AAT', 'ATT', 'TTC', 'TCC', 'CCA', 'CAG', 'AGG', 'GGA', 'GAA', 'AAT', 'ATT', 'TTC', 'TCT', 'CTC', 'TCC', 'CCC', 'CCG', 'CGG', 'GGT', 'GTA', 'TAA', 'AAT', 'ATC', 'TCT', 'CTA', 'TAA', 'AAA', 'AAG', 'AGG', 'GGC', 'GCA', 'CAC', 'ACT', 'CTT', 'TTA', 'TAT', 'ATT', 'TTC', 'TCG', 'CGG', 'GGT', 'GTT', 'TTC', 'TCC', 'CCT', 'CTC', 'TCC', 'CCA', 'CAT', 'ATG', 'TGG', 'GGT', 'GTC', 'TCC', 'CCT', 'CTT', 'TTT', 'TTA', 'TAC', 'ACT', 'CTG', 'TGG', 'GGC', 'GCC', 'CCT', 'CTC', 'TCC', 'CCC', 'CCC', 'CCA', 'CAC', 'ACG', 'CGG', 'GGT', 'GTC', 'TCC', 'CCA', 'CAC', 'ACA', 'CAT', 'ATC', 'TCT', 'CTG', 'TGG', 'GGT', 'GTT', 'TTA', 'TAC', 'ACT', 'CTT', 'TTA', 'TAT', 'ATC', 'TCG', 'CGG', 'GGC', 'GCT', 'CTC', 'TCC', 'CCT', 'CTC', 'TCC', 'CCA', 'CAA', 'AAG', 'AGG', 'GGT', 'GTA', 'TAT', 'ATC', 'TCT', 'CTT', 'TTA', 'TAT', 'ATC', 'TCG', 'CGG', 'GGA', 'GAC', 'ACC', 'CCA', 'CAC', 'ACT', 'CTC', 'TCT', 'CTC', 'TCG', 'CGG', 'GGT', 'GTC', 'TCT', 'CTC', 'TCC', 'CCC', 'CCC', 'CCT', 'CTT', 'TTG', 'TGG', 'GGC', 'GCA', 'CAC', 'ACA', 'CAA', 'AAC', 'ACA', 'CAC', 'ACT', 'CTG', 'TGG', 'GGT', 'GTA', 'TAT', 'ATA', 'TAC', 'ACC', 'CCA', 'CAA', 'AAC', 'ACG', 'CGG', 'GGC', 'GCA', 'CAC', 'ACT', 'CTT', 'TTT', 'TTC', 'TCT', 'CTC', 'TCG', 'CGG', 'GGA', 'GAT', 'ATC', 'TCA', 'CAC', 'ACT', 'CTC', 'TCA', 'CAA', 'AAG', 'AGG', 'GGA', 'GAA', 'AAC', 'ACA', 'CAT', 'ATA', 'TAA', 'AAA', 'AAA', 'AAG', 'AGG', 'GGT', 'GTT', 'TTC', 'TCC', 'CCC', 'CCA', 'CAC', 'ACT', 'CTT', 'TTG', 'TGG', 'GGT', 'GTT', 'TTC', 'TCC', 'CCT', 'CTA', 'TAA', 'AAC', 'ACA', 'CAG', 'AGG', 'GGA', 'GAT', 'ATA', 'TAA', 'AAT', 'ATC', 'TCA', 'CAT', 'ATA', 'TAG', 'AGG', 'GGC', 'GCA', 'CAA', 'AAC', 'ACC', 'CCC', 'CCA', 'CAC', 'ACA', 'CAG', 'AGG', 'GGC', 'GCC', 'CCA', 'CAA', 'AAA', 'AAT', 'ATT', 'TTA', 'TAA', 'AAG', 'AGG', 'GGT', 'GTC', 'TCA', 'CAC', 'ACC', 'CCC', 'CCA', 'CAA', 'AAC', 'ACG', 'CGG', 'GGA', 'GAA', 'AAT', 'ATT', 'TTA', 'TAT', 'ATC', 'TCA', 'CAA', 'AAG', 'AGG', 'GGA', 'GAC', 'ACA', 'CAT', 'ATA', 'TAT', 'ATC', 'TCT', 'CTT', 'TTG', 'TGG', 'GGA', 'GAT', 'ATA', 'TAA', 'AAC', 'ACC', 'CCT', 'CTT', 'TTA', 'TAG', 'AGG', 'GGT', 'GTT', 'TTC', 'TCC', 'CCT', 'CTA', 'TAT', 'ATA', 'TAC', 'ACG', 'CGG', 'GGC', 'GCC', 'CCT', 'CTT', 'TTA', 'TAT', 'ATC', 'TCT', 'CTT', 'TTG', 'TGG', 'GGC', 'GCT', 'CTC', 'TCA', 'CAT', 'ATC', 'TCT', 'CTC', 'TCT', 'CTG', 'TGG', 'GGC', 'GCA', 'CAT', 'ATA', 'TAC', 'ACT', 'CTC', 'TCC', 'CCA', 'CAG', 'AGG', 'GGC', 'GCA', 'CAA', 'AAT', 'ATC', 'TCA', 'CAT', 'ATC', 'TCC', 'CCG', 'CGG', 'GGC', 'GCT', 'CTA', 'TAT', 'ATA', 'TAA', 'AAC', 'ACC', 'CCT', 'CTG', 'TGG', 'GGT', 'GTC', 'TCC', 'CCT', 'CTA', 'TAA', 'AAA', 'AAT', 'ATT', 'TTG', 'TGG', 'GGT', 'GTC', 'TCA', 'CAA', 'AAA', 'AAC', 'ACT', 'CTT', 'TTA', 'TAG', 'AGG', 'GGA', 'GAT', 'ATA', 'TAA', 'AAT', 'ATA', 'TAA', 'AAA', 'AAT', 'ATG', 'TGG', 'GGC', 'GCC', 'CCT', 'CTC', 'TCT', 'CTT', 'TTA', 'TAA', 'AAC', 'ACG', 'CGG', 'GGA', 'GAT', 'ATC', 'TCC', 'CCA', 'CAA', 'AAA', 'AAT', 'ATA', 'TAG', 'AGG', 'GGA', 'GAA', 'AAC', 'ACC', 'CCC', 'CCT', 'CTC', 'TCA', 'CAT', 'ATG', 'TGG', 'GGA', 'GAC', 'ACC', 'CCC', 'CCT', 'CTT', 'TTA', 'TAC', 'ACT', 'CTG', 'TGG', 'GGA', 'GAC', 'ACC', 'CCT', 'CTA', 'TAA', 'AAC', 'ACA', 'CAC', 'ACG', 'CGG', 'GGT', 'GTT', 'TTC', 'TCC', 'CCT', 'CTC', 'TCA', 'CAC', 'ACA', 'CAG', 'AGG', 'GGC', 'GCT', 'CTC', 'TCT', 'CTC', 'TCA', 'CAT', 'ATA', 'TAA', 'AAG', 'AGG', 'GGA', 'GAT', 'ATC', 'TCA', 'CAC', 'ACC', 'CCA', 'CAC', 'ACT', 'CTG', 'TGG', 'GGA', 'GAT', 'ATC', 'TCA', 'CAC', 'ACT', 'CTC', 'TCA', 'CAT', 'ATG', 'TGG', 'GGT', 'GTA', 'TAT', 'ATA', 'TAC', 'ACC', 'CCC', 'CCT', 'CTA', 'TAG', 'AGG', 'GGT', 'GTC', 'TCA', 'CAA', 'AAA', 'AAT', 'ATC', 'TCT', 'CTA', 'TAG', 'AGG', 'GGC', 'GCT', 'CTT', 'TTA', 'TAT', 'ATA', 'TAT', 'ATT', 'TTA', 'TAG', 'AGG', 'GGT', 'GTA', 'TAA', 'AAC', 'ACA', 'CAA', 'AAC', 'ACC', 'CCA', 'CAG', 'AGG', 'GGT', 'GTA', 'TAA', 'AAT', 'ATT', 'TTC', 'TCA', 'CAT', 'ATC', 'TCG', 'CGG', 'GGC', 'GCC', 'CCC', 'CCT', 'CTA', 'TAA', 'AAA', 'AAC', 'ACC', 'CCG', 'CGG', 'GGA', 'GAA', 'AAT', 'ATC', 'TCA', 'CAT', 'ATC', 'TCC', 'CCC', 'CCG', 'CGG', 'GGA', 'GAC', 'ACC', 'CCA', 'CAC', 'ACA', 'CAC', 'ACA', 'CAC', 'ACG', 'CGG', 'GGA', 'GAC', 'ACT', 'CTC', 'TCA', 'CAT', 'ATA', 'TAA', 'AAT', 'ATG', 'TGG', 'GGC', 'GCA', 'CAA', 'AAT', 'ATT', 'TTT', 'TTA', 'TAC', 'ACC', 'CCG', 'CGG', 'GGT', 'GTC', 'TCT', 'CTC', 'TCC', 'CCA', 'CAT', 'ATA', 'TAA', 'AAG', 'AGG', 'GGC', 'GCT', 'CTC', 'TCA', 'CAC', 'ACT', 'CTA', 'TAT', 'ATA', 'TAG', 'AGG', 'GGC', 'GCC', 'CCT', 'CTC', 'TCC', 'CCC', 'CCA', 'CAT', 'ATC', 'TCG', 'CGG', 'GGC', 'GCA', 'CAT', 'ATC', 'TCT', 'CTT', 'TTC', 'TCA', 'CAT', 'ATG', 'TGG', 'GGA', 'GAA', 'AAC', 'ACC', 'CCT', 'CTC', 'TCT', 'CTT', 'TTA', 'TAG', 'AGG', 'GGA', 'GAC', 'ACA', 'CAA', 'AAA', 'AAC', 'ACC', 'CCC', 'CCA', 'CAG', 'AGG', 'GGA', 'GAC', 'ACA', 'CAC', 'ACT', 'CTC', 'TCA', 'CAC', 'ACA', 'CAG', 'AGG', 'GGT', 'GTC', 'TCT', 'CTT', 'TTC', 'TCT', 'CTA', 'TAT', 'ATT', 'TTG', 'TGG', 'GGA', 'GAC', 'ACC', 'CCT', 'CTT', 'TTC', 'TCA', 'CAT', 'ATT', 'TTG', 'TGG', 'GGA', 'GAA', 'AAC', 'ACC', 'CCT', 'CTT', 'TTT', 'TTC', 'TCT', 'CTG', 'TGG', 'GGA', 'GAA', 'AAT', 'ATC', 'TCA', 'CAT', 'ATA', 'TAC', 'ACG', 'CGG', 'GGA', 'GAT', 'ATC', 'TCA', 'CAT', 'ATA', 'TAT', 'ATG', 'TGG', 'GGT', 'GTA', 'TAA', 'AAA', 'AAC', 'ACT', 'CTA', 'TAG', 'AGG', 'GGA', 'GAT', 'ATC', 'TCC', 'CCC', 'CCT', 'CTA', 'TAG', 'AGG', 'GGT', 'GTA', 'TAT', 'ATC', 'TCA', 'CAC', 'ACA', 'CAA', 'AAC', 'ACT', 'CTA', 'TAC', 'ACC', 'CCT', 'CTC', 'TCA', 'CAC', 'ACA', 'CAA', 'AAA', 'AAA', 'AAA', 'AAA', 'AAA', 'AAA', 'AAA', 'AAA']
    降重后的集合为 {'ATG', 'GTA', 'ATC', 'AAA', 'TGG', 'AGG', 'GAC', 'CAA', 'AAT', 'GAT', 'CTG', 'ACA', 'TCG', 'TCC', 'AAC', 'ATT', 'AAG', 'TTC', 'TAT', 'GGC', 'CTT', 'CAT', 'GGA', 'GTC', 'TTG', 'TCA', 'TTA', 'TAC', 'GCT', 'TCT', 'ATA', 'GCA', 'ACG', 'GCC', 'GGT', 'CCG', 'CTC', 'GAA', 'TAG', 'ACT', 'GTT', 'ACC', 'CAG', 'CCA', 'CCC', 'TAA', 'TTT', 'CCT', 'CTA', 'CGG', 'CAC'}
    集合转为列表为 ['ATG', 'GTA', 'ATC', 'AAA', 'TGG', 'AGG', 'GAC', 'CAA', 'AAT', 'GAT', 'CTG', 'ACA', 'TCG', 'TCC', 'AAC', 'ATT', 'AAG', 'TTC', 'TAT', 'GGC', 'CTT', 'CAT', 'GGA', 'GTC', 'TTG', 'TCA', 'TTA', 'TAC', 'GCT', 'TCT', 'ATA', 'GCA', 'ACG', 'GCC', 'GGT', 'CCG', 'CTC', 'GAA', 'TAG', 'ACT', 'GTT', 'ACC', 'CAG', 'CCA', 'CCC', 'TAA', 'TTT', 'CCT', 'CTA', 'CGG', 'CAC']
    [12, 11, 29, 22, 30, 30, 9, 25, 23, 11, 9, 24, 9, 28, 26, 18, 10, 21, 21, 30, 28, 27, 30, 10, 9, 32, 25, 18, 10, 24, 23, 10, 10, 10, 30, 11, 33, 10, 11, 22, 9, 27, 9, 25, 19, 25, 7, 30, 16, 30]
    字符串中长度为3motif以及出现次数为 {'ATG': 12, 'GTA': 11, 'ATC': 29, 'AAA': 22, 'TGG': 30, 'AGG': 30, 'GAC': 9, 'CAA': 25, 'AAT': 23, 'GAT': 11, 'CTG': 9, 'ACA': 24, 'TCG': 9, 'TCC': 28, 'AAC': 26, 'ATT': 18, 'AAG': 10, 'TTC': 21, 'TAT': 21, 'GGC': 30, 'CTT': 28, 'CAT': 27, 'GGA': 30, 'GTC': 10, 'TTG': 9, 'TCA': 32, 'TTA': 25, 'TAC': 18, 'GCT': 10, 'TCT': 24, 'ATA': 23, 'GCA': 10, 'ACG': 10, 'GCC': 10, 'GGT': 30, 'CCG': 11, 'CTC': 33, 'GAA': 10, 'TAG': 11, 'ACT': 22, 'GTT': 9, 'ACC': 27, 'CAG': 9, 'CCA': 25, 'CCC': 19, 'TAA': 25, 'TTT': 7, 'CCT': 30, 'CTA': 16, 'CGG': 30}
    


```python

```
