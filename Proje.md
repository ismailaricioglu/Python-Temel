1- Bir listeyi düzleştiren (flatten) fonksiyon yazın. Elemanları birden çok katmanlı listelerden ([[3],2] gibi) oluşabileceği gibi, non-scalar verilerden de oluşabilir. Örnek olarak:

input: [[1,'a',['cat'],2],[[[3]],'dog'],4,5]

output: [1,'a','cat',2,3,'dog',4,5]

Çözüm:

```python
l = [[1,'a',['cat'],2],[[[3]],'dog'],4,5]

flattenList = []
def flatten(listX):    
    x = listX.copy()
    for e in x:
        if (type(e) == list):
            flatten(e)
        else:
            flattenList.append(e)
    return flattenList

l = flatten(l)
print(l)
```
---

2- Verilen listenin içindeki elemanları tersine döndüren bir fonksiyon yazın. Eğer listenin içindeki elemanlar da liste içeriyorsa onların elemanlarını da tersine döndürün. Örnek olarak:

input: [[1, 2], [3, 4], [5, 6, 7]]

output: [[[7, 6, 5], [4, 3], [2, 1]]

Çözüm:

```python
# isim[::-1]
ll = [[1, 2], [3, 4], [5, 6, 7]]

def ters(listX):  
    x = listX.copy()
    # print("")
    # print(x)
    tersList = []
    for e in range((len(x)-1),-1,-1):
        if (type(x[e]) == list):
            tersList.append(ters(x[e]))
            # print(f"ters list = {tersList}")
        else:
            tersList.append(x[e])
            # print(f"eleman = {x[e]}")
    # print(f"ters list = {tersList}")
    # print("")
    return tersList

ll = ters(ll)
print(ll)
```
