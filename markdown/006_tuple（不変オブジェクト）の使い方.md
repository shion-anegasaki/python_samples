# tuple（不変オブジェクト）の使い方
tupleとは、Pythonが持つ不変（イミュータブル）オブジェクトのひとつです。  
listやdictのように要素の追加、変更や削除などの操作が行えません。

公式ドキュメント:  
https://docs.python.org/ja/3/tutorial/datastructures.html#tuples-and-sequences  

## 扱い方


```python
# 要素を()で囲んで、カンマで区切る
x = (0, 1, 2)

# 同じ型じゃなくてもいい
y = (0, 1, 'ni') 

# tupleにtupleを含めることもできる
z = ((0, 1, 2), (3, 4, 5), (6, 7, 8)) 
```

一見不便そうに思えるtupleですが、以下のような特徴があります。
- 要素の追加、変更、削除ができない
- listに比べて省メモリで扱える
- listに比べて処理が早い
- tupleとlistは相互に変換可能

要素の変更を行えないので、例えば


```python
x = (0, 1, 2)
x[0] = 10
```


    

    TypeErrorTraceback (most recent call last)

    <ipython-input-3-90db26ba069f> in <module>
          1 x = (0, 1, 2)
    ----> 2 x[0] = 10
    

    TypeError: 'tuple' object does not support item assignment


変更を試みると上記のようなエラーが発生してしまいます。

## tupleの操作
tupleが持つ関数は **count関数** と **index関数** のみです。

### 要素の出現回数を取得


```python
x = (1, 1, 1, 2)
# 引数に出現回数を調べたい要素を渡す
print(x.count(1))
```

    3


### 最初に出現する要素番号を取得


```python
x = (1, 1, 2, 1)
print(x.index(2))
```

    2


### tupleからlistへ変換


```python
# type関数は型を調べるのに利用します。
x = (1, 1, 2, 1)
print(type(x))

x = list(x)
print(type(x))
```

    <class 'tuple'>
    <class 'list'>


### listからtupleへ変換


```python
x = [0, 1, 2, 3]
print(type(x))

x = tuple(x)
print(type(x))
```

    <class 'list'>
    <class 'tuple'>


### 要素の操作
listに変換してしまえば要素の追加、変更や削除などの操作を行うことができます。  
また再度tupleに変換してしまえば、イミュータブルオブジェクトとなります。  
  
操作についてはlistの項目を参考にしてみてください！  
また、tuple同士であれば加算が可能なので


```python
x = (1, 2, 3)
print(x)

x = (0, ) + x
print(x)

x = x + (4,)
print(x)
```

    (1, 2, 3)
    (0, 1, 2, 3)
    (0, 1, 2, 3, 4)


のような操作も可能です。

### その他の操作
tupleはイテラブルオブジェクトでもあるので、for文 で回すことができます。  
  
<p style="color:red">※ 厳密に言うとlistがイテレータを利用しているのに対して、tupleはジェネレータを利用している違いはありますが、どちらもイテラブルオブジェクトと呼びます。</p>


```python
for i in (1, 2, 3, 4):
    print(i)
```

    1
    2
    3
    4

