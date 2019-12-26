

```python
#小说中出现频率前二十的单词
fid = open('ONEDAY.txt', 'r')
str_1 = fid.read()
str_2 = str_1.replace(',', '')
str_3 = str_2.replace('.', '')
str_4 = str_3.replace('\n', ' ')
str_5 = str_4.replace('--', ' ')
word_list = str_5.split(' ')

word_dict = {}
m = len(word_list)
for i in range(0, m):
    s = word_list[i]
    if s in word_dict.keys():
        word_dict[s] = word_dict[s] + 1
    else:
        word_dict[s] = 1
'''print(word_dict)'''

word_list_2 = sorted(word_dict.items(), key = lambda x: x[1], reverse = True)
'''print(word_list_2)'''

for i in range(20):
    print(word_list_2[i][0], end = '\t')
```

    	the	and	a	to	of	her	in	he	you	his	that	she	I	it	on	was	is	with	at	


```python
def filemaker(num):
    for i in range(num):
        fa=open(r'files%s.txt'%(i),mode='w')
        print('diary of No.%s'%(i), file = fa)
        fa.close()
filemaker(1000)
```


```python
#对给出的数据进行处理
def my_dna_search(string,num):
    dnadic={}
    M=len(string)
    for i in range(M-num+1):
        s=string[i:i+num]
        if s in dnadic.keys():
            dnadic[s]=dnadic[s]+1
        else:
            dnadic[s]=1
    return str(dnadic)

fid=open('ref.fasta','r')
f=fid.readlines()
n=len(f)
q=open('motif times.txt','w')
for i in range(n):
    s=f[i].strip() 
    if i%2==0:
         q.write(s+'\n')
    else:
        m=my_dna_search(s,3)
        q.write(m+'\n')
        
q1=open('motif times.txt','r')
q2=q1.readlines()
print(q2)

```

    ['>Gmod1\n', "{'TCA': 29, 'CAA': 24, 'AAA': 25, 'AAT': 24, 'ATC': 32, 'TCT': 28, 'CTA': 35, 'TAC': 34, 'ACA': 20, 'CAC': 26, 'ACT': 30, 'CTG': 11, 'TGA': 10, 'GAT': 10, 'ACC': 30, 'CCA': 31, 'AAG': 10, 'AGT': 10, 'GTT': 11, 'TTT': 16, 'TTA': 28, 'TAA': 22, 'AAC': 21, 'CAT': 28, 'ATG': 10, 'TGC': 10, 'GCC': 12, 'ACG': 11, 'CGC': 10, 'ATT': 28, 'TTC': 27, 'TCG': 10, 'CGT': 11, 'CTC': 26, 'GCT': 9, 'CGA': 10, 'GAA': 10, 'TCC': 29, 'AGC': 10, 'CCC': 26, 'CCT': 30, 'TAT': 34, 'CTT': 25, 'CCG': 10, 'GTA': 10, 'ATA': 26, 'CAG': 11, 'TTG': 9, 'TGT': 10, 'GTC': 10, 'TAG': 9, 'AGA': 10, 'GAC': 10, 'GCA': 9}\n", '>Gmod2\n', "{'CCA': 25, 'CAC': 30, 'ACA': 24, 'CAT': 27, 'ATC': 29, 'TCA': 32, 'ACT': 22, 'CTT': 28, 'TTA': 25, 'TAC': 18, 'CTA': 16, 'ACC': 27, 'CCC': 19, 'CCG': 11, 'CGG': 30, 'GGT': 30, 'GTC': 10, 'TCT': 24, 'CTC': 33, 'CAA': 25, 'AAT': 23, 'ATG': 12, 'TGG': 30, 'GGC': 30, 'GCC': 10, 'AAC': 26, 'GGA': 30, 'GAA': 10, 'AAA': 22, 'ATT': 18, 'TAA': 25, 'AAG': 10, 'AGG': 30, 'GCT': 10, 'GCA': 10, 'TTC': 21, 'ACG': 10, 'TCC': 28, 'GAT': 11, 'ATA': 23, 'TCG': 9, 'GTA': 11, 'GTT': 9, 'TTT': 7, 'CCT': 30, 'CAG': 9, 'TAT': 21, 'TTG': 9, 'CTG': 9, 'GAC': 9, 'TAG': 11}\n", '>Gmod3\n', "{'AAC': 19, 'ACC': 20, 'CCA': 14, 'CAC': 17, 'ACT': 22, 'CTT': 18, 'TTA': 15, 'TAT': 25, 'ATA': 25, 'TAC': 26, 'CTC': 22, 'TCT': 26, 'TCA': 23, 'ACG': 9, 'CGG': 12, 'GGA': 12, 'GAC': 13, 'CTA': 33, 'ATC': 15, 'TTG': 8, 'TGG': 12, 'GGC': 12, 'GCC': 9, 'CCC': 14, 'CCT': 22, 'CCG': 12, 'GCT': 10, 'TAA': 18, 'AAT': 25, 'ACA': 24, 'CAG': 11, 'AGG': 12, 'GCA': 11, 'CAT': 24, 'ATT': 26, 'ATG': 15, 'GGT': 12, 'GTA': 11, 'GTT': 6, 'TTT': 13, 'TTC': 27, 'GTC': 13, 'CGC': 12, 'GCG': 18, 'CGT': 12, 'AGA': 12, 'GAG': 18, 'AGC': 12, 'GTG': 18, 'TGT': 12, 'AAA': 24, 'CAA': 20, 'AAG': 4, 'AGT': 12, 'TCG': 9, 'CGA': 12, 'GAA': 10, 'TGC': 12, 'GAT': 7, 'TAG': 15, 'TGA': 12, 'TCC': 19, 'CTG': 7, 'GGG': 18}\n", '>Gmod4\n', "{'ACA': 28, 'CAT': 24, 'ATC': 29, 'TCC': 25, 'CCT': 26, 'CTC': 28, 'TCA': 32, 'CAA': 29, 'AAT': 21, 'CCA': 17, 'CCC': 15, 'CTG': 9, 'TGG': 27, 'GGG': 81, 'GGT': 27, 'GTC': 9, 'ATT': 20, 'TTC': 21, 'TCT': 21, 'GGC': 27, 'GCA': 9, 'TTA': 19, 'TAG': 9, 'AGG': 27, 'GTA': 9, 'TAC': 24, 'AAC': 22, 'AAA': 20, 'AAG': 9, 'CTT': 20, 'TTT': 6, 'TTG': 9, 'GGA': 27, 'GAC': 9, 'ACT': 25, 'ACC': 18, 'TCG': 9, 'CGG': 27, 'GTT': 9, 'GAT': 9, 'CAC': 24, 'ACG': 9, 'TAT': 27, 'ATA': 23, 'TAA': 15, 'GCC': 9, 'CTA': 24, 'ATG': 9, 'GCT': 9, 'CAG': 9, 'CCG': 9, 'GAA': 9}\n", '>Gmod5\n', "{'CAA': 20, 'AAC': 21, 'ACA': 19, 'CAC': 25, 'ACT': 25, 'CTT': 22, 'TTA': 25, 'TAT': 26, 'ATA': 23, 'TAA': 19, 'AAT': 22, 'ATG': 21, 'TGC': 10, 'GCT': 14, 'CTG': 13, 'TGA': 13, 'GAC': 16, 'CAT': 25, 'TAC': 25, 'ACC': 25, 'CCC': 10, 'CCG': 7, 'CGC': 8, 'GCA': 13, 'CAG': 14, 'AGA': 10, 'GAA': 16, 'ATC': 29, 'TCC': 21, 'CCT': 22, 'CTA': 23, 'TGT': 10, 'GTA': 14, 'TAG': 15, 'AGC': 9, 'CTC': 19, 'CCA': 28, 'ATT': 15, 'TTG': 13, 'TGG': 14, 'GGG': 39, 'GGC': 11, 'GCC': 11, 'TTC': 11, 'TCA': 23, 'AGT': 9, 'AGG': 12, 'GGT': 14, 'GTC': 14, 'ACG': 18, 'CGA': 10, 'GAT': 15, 'TCT': 16, 'GTT': 12, 'TCG': 13, 'AAG': 11, 'CGT': 7, 'GGA': 14, 'AAA': 14, 'CGG': 13, 'TTT': 1}\n", '>Gmod6\n', "{'ATC': 21, 'TCT': 16, 'CTA': 14, 'TAC': 12, 'ACA': 17, 'CAC': 20, 'ACT': 15, 'CTC': 18, 'TAG': 13, 'AGG': 17, 'GGT': 13, 'GTT': 9, 'TTG': 15, 'TGA': 15, 'GAA': 15, 'AAA': 27, 'AAC': 13, 'ACG': 14, 'CGT': 13, 'TTA': 10, 'AGA': 19, 'GAC': 14, 'CAA': 23, 'AAT': 19, 'TCG': 14, 'CGA': 15, 'GAG': 16, 'GTA': 13, 'ACC': 13, 'CCA': 19, 'CAG': 18, 'GTG': 22, 'TGG': 19, 'GGG': 5, 'GGA': 19, 'GAT': 23, 'TCA': 19, 'CGG': 12, 'TGC': 22, 'GCT': 17, 'GGC': 16, 'GCG': 18, 'CAT': 13, 'ATG': 16, 'GCA': 19, 'ATA': 12, 'CTG': 18, 'CTT': 15, 'TTT': 16, 'AGC': 14, 'AAG': 19, 'CGC': 15, 'GCC': 13, 'CCT': 17, 'TAA': 14, 'TTC': 16, 'TCC': 19, 'CCC': 9, 'AGT': 16, 'GTC': 13, 'TAT': 10, 'ATT': 17, 'CCG': 9, 'TGT': 15}\n", '>Gmod7\n', "{'CCA': 17, 'CAT': 14, 'ATA': 28, 'TAC': 27, 'ACT': 24, 'CTA': 25, 'TAT': 23, 'ATT': 17, 'TTC': 16, 'TCA': 16, 'CAC': 13, 'ACG': 15, 'CGA': 18, 'GAT': 15, 'ATG': 10, 'TGT': 17, 'GTC': 17, 'CAA': 15, 'AAA': 19, 'AAG': 13, 'AGC': 20, 'GCT': 17, 'TAG': 18, 'CTT': 13, 'TTT': 12, 'TCG': 19, 'CGG': 19, 'GGG': 4, 'GGA': 15, 'GAG': 15, 'AGA': 22, 'GAA': 12, 'AAT': 17, 'TTA': 15, 'ATC': 14, 'TCT': 15, 'CTG': 18, 'TGC': 11, 'GCC': 17, 'CCT': 16, 'CTC': 16, 'GAC': 22, 'ACC': 19, 'CCG': 17, 'CAG': 20, 'AGG': 10, 'GGT': 13, 'GTG': 10, 'TCC': 13, 'CCC': 8, 'TGA': 9, 'ACA': 19, 'TTG': 10, 'GTT': 11, 'CGC': 15, 'GCG': 14, 'AAC': 15, 'AGT': 14, 'TGG': 11, 'GGC': 12, 'CGT': 13, 'GTA': 19, 'TAA': 19, 'GCA': 10}\n", '>Gmod9\n', "{'ACT': 28, 'CTT': 25, 'TTA': 24, 'TAA': 30, 'AAC': 20, 'TTC': 23, 'TCC': 22, 'CCA': 25, 'CAC': 25, 'ACG': 12, 'CGA': 4, 'GAA': 11, 'AAA': 26, 'AAT': 34, 'ATA': 28, 'ATG': 11, 'TGA': 17, 'ACA': 23, 'CAA': 27, 'ATC': 27, 'TCA': 23, 'CAG': 9, 'AGC': 18, 'GCA': 12, 'ATT': 28, 'TCT': 23, 'TTG': 14, 'TGC': 10, 'TAT': 27, 'GCC': 17, 'CTA': 30, 'TTT': 16, 'CCT': 28, 'CTC': 25, 'GCT': 13, 'TAC': 28, 'TCG': 13, 'CGT': 14, 'GTA': 21, 'CCC': 22, 'CCG': 7, 'CGC': 14, 'TAG': 18, 'AAG': 13, 'AGA': 11, 'CTG': 12, 'GAT': 11, 'CAT': 22, 'GAC': 10, 'ACC': 21, 'AGT': 11, 'TGT': 10, 'GTC': 6, 'GTT': 8}\n", '>Gmod10\n', "{'CAT': 20, 'ATA': 34, 'TAC': 28, 'ACA': 26, 'CAA': 26, 'AAC': 26, 'ACC': 30, 'CCA': 17, 'AAT': 34, 'ATT': 26, 'TTG': 9, 'TGA': 11, 'GAC': 15, 'ACT': 25, 'CTC': 17, 'TCC': 17, 'CCT': 28, 'CTA': 30, 'ACG': 10, 'CGT': 10, 'GTA': 14, 'TAT': 28, 'CAG': 10, 'AGC': 11, 'GCT': 9, 'TAA': 36, 'ATC': 19, 'CCC': 21, 'CCG': 12, 'CGC': 5, 'TCT': 18, 'CTT': 23, 'TTC': 21, 'TCA': 26, 'ATG': 16, 'GAT': 13, 'TTT': 18, 'TTA': 33, 'TAG': 19, 'AGA': 20, 'GCA': 8, 'CTG': 10, 'TGT': 13, 'GTT': 14, 'TCG': 6, 'CGA': 13, 'AAA': 31, 'AAG': 17, 'GAA': 16, 'AGT': 15, 'GCC': 10, 'GTC': 10, 'CAC': 22, 'TGC': 11}\n", '>Gmod11\n', "{'CCT': 31, 'CTA': 28, 'TAA': 32, 'AAC': 25, 'ACT': 20, 'TAT': 21, 'ATT': 16, 'TTA': 20, 'AAT': 26, 'ATC': 17, 'TCG': 7, 'CGG': 28, 'GGA': 33, 'GAA': 10, 'ATA': 38, 'ACA': 23, 'CAT': 25, 'ATG': 17, 'TGG': 34, 'GGT': 28, 'GTC': 10, 'TCC': 19, 'CCC': 18, 'CTT': 20, 'TTT': 8, 'TTG': 5, 'GTA': 9, 'TAC': 29, 'ACC': 19, 'CCA': 17, 'CAA': 22, 'AAA': 28, 'ACG': 14, 'TTC': 20, 'CAC': 15, 'CCG': 7, 'GAT': 16, 'TCT': 27, 'GTT': 9, 'CTC': 29, 'TCA': 23, 'CAG': 11, 'AGG': 36, 'GGC': 37, 'GCA': 10, 'AAG': 12, 'CTG': 12, 'TAG': 13, 'GCT': 11, 'GCC': 16, 'GAC': 7}\n", '>Gmod12\n', "{'ACT': 25, 'CTC': 22, 'TCC': 23, 'CCA': 31, 'CAC': 37, 'ACA': 25, 'TCA': 28, 'CAA': 24, 'AAC': 16, 'ACG': 13, 'CGG': 40, 'GGC': 35, 'GCT': 13, 'CTT': 20, 'TTT': 10, 'TTC': 24, 'CAT': 24, 'ATT': 22, 'TTG': 6, 'TGG': 26, 'GGT': 27, 'GTC': 11, 'TCT': 19, 'ACC': 30, 'CCG': 14, 'GCC': 12, 'CCT': 20, 'CTA': 26, 'TAT': 17, 'ATG': 11, 'GGA': 36, 'GAA': 9, 'AAT': 25, 'CCC': 21, 'CAG': 9, 'AGG': 32, 'GAC': 17, 'TTA': 20, 'TAG': 12, 'GTA': 8, 'TAA': 20, 'ATC': 26, 'GCA': 10, 'AAA': 22, 'AAG': 11, 'GAT': 10, 'TAC': 22, 'GTT': 8, 'TCG': 13, 'ATA': 17, 'CTG': 9}\n", '>Gmod13\n', "{'ATC': 19, 'TCT': 24, 'CTA': 21, 'TAC': 26, 'ACT': 26, 'CTT': 27, 'TTC': 29, 'TCC': 22, 'CCA': 20, 'CAC': 23, 'ACA': 26, 'CAT': 20, 'ATG': 11, 'TGG': 30, 'GGC': 31, 'GCA': 14, 'TAT': 20, 'TCG': 18, 'CGG': 35, 'GGA': 39, 'GAT': 14, 'ATA': 23, 'TAA': 23, 'AAT': 24, 'ATT': 26, 'TTT': 18, 'GAA': 11, 'AAC': 20, 'ACC': 24, 'ACG': 7, 'GAC': 14, 'CCC': 15, 'CCT': 21, 'TTG': 10, 'GGT': 28, 'GTC': 7, 'CAA': 23, 'AAA': 26, 'GCC': 5, 'GCT': 12, 'CTC': 26, 'AAG': 12, 'AGG': 33, 'GTT': 13, 'CCG': 10, 'TTA': 27, 'CTG': 9, 'TAG': 10, 'TCA': 17, 'CAG': 11, 'GTA': 8}\n", '>Gmod14\n', "{'AAT': 23, 'ATC': 23, 'TCA': 19, 'CAT': 16, 'ATA': 20, 'TAT': 19, 'ATT': 16, 'TTC': 25, 'TCC': 24, 'CCT': 25, 'CTT': 29, 'TCG': 13, 'CGG': 35, 'GGA': 35, 'GAA': 8, 'AAA': 26, 'TTT': 27, 'TTA': 22, 'TAC': 15, 'ACG': 9, 'GGC': 27, 'GCT': 8, 'CTC': 22, 'TCT': 25, 'ACC': 24, 'CCG': 13, 'GGT': 36, 'GTA': 13, 'TAA': 29, 'AAC': 27, 'ACA': 26, 'CAA': 25, 'GCA': 8, 'ACT': 23, 'TTG': 10, 'TGG': 30, 'GAC': 17, 'GTC': 11, 'CAC': 23, 'CCC': 23, 'CTA': 19, 'TAG': 11, 'AGG': 33, 'GCC': 11, 'CCA': 21, 'CTG': 11, 'ATG': 9, 'AAG': 12, 'CAG': 10, 'GAT': 10, 'GTT': 12}\n", '>Gmod15\n', "{'ACT': 18, 'CTC': 25, 'TCC': 28, 'CCA': 26, 'CAC': 18, 'ACA': 29, 'CAA': 29, 'AAT': 21, 'ATC': 25, 'CCT': 21, 'CTT': 26, 'TTG': 14, 'TGG': 30, 'GGC': 33, 'GCC': 14, 'TCA': 19, 'AAA': 26, 'AAG': 11, 'AGG': 33, 'GGT': 36, 'GTC': 13, 'GTT': 10, 'TTA': 23, 'TAC': 22, 'ACC': 15, 'CTG': 5, 'GCT': 13, 'TAT': 23, 'ATT': 22, 'TTT': 26, 'GTA': 13, 'TCT': 23, 'CTA': 19, 'CCG': 10, 'CGG': 35, 'GGA': 29, 'GAT': 13, 'ACG': 11, 'GCA': 6, 'CAT': 24, 'ATA': 23, 'TAA': 20, 'AAC': 26, 'TCG': 14, 'ATG': 11, 'TTC': 21, 'CAG': 9, 'GAA': 10, 'CCC': 18, 'TAG': 13, 'GAC': 6}\n"]
    


```python

```
