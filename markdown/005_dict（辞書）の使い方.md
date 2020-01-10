# dict（辞書）の使い方
dict（辞書）とは、Pythonのもつデータ型のうち、値と名前の組み合わせを要素とし、複数の要素をひとまとめとして扱えるものです。

## dictの使い方
要素の名前をキー、要素の値をバリューと呼び、キーとバリューのセットをひとつの要素として扱います。  
キーは基本的に文字列で、バリューは何でも扱うことができます。参照するときはキーを利用します。


```python
# {}で囲んで、キー:バリューをカンマ区切りにします。
x = {'key_1': 'value_1','キー2':2 }
print(x['key_1'])
print(x['キー2'])
```

    value_1
    2


※ キーが存在しない場合はエラーとなります。その場合は、get関数を利用して、デフォルトの値をセットしておくと回避できます。


```python
x = {'key_1': 'value_1','キー2':2 }
print(x['key_2'])
```


    

    KeyErrorTraceback (most recent call last)

    <ipython-input-3-e3b8b842a4a3> in <module>
          1 x = {'key_1': 'value_1','キー2':2 }
    ----> 2 print(x['key_2'])
    

    KeyError: 'key_2'



```python
print(x.get('key_2', 'default value')) ### デフォルトの値は第二引数に指定します。
```

    default value


## dictの操作
* ### 要素追加


```python
x = {'key_1': 'value'}
print(x)

x['key_2'] = 2
print(x)
```

    {'key_1': 'value'}
    {'key_1': 'value', 'key_2': 2}


* ### 要素削除


```python
x = {'key_1': 'value', 'key_2': 2}
print(x)

x.pop('key_1')
print(x)

del x['key_2']
print(x)
```

    {'key_1': 'value', 'key_2': 2}
    {'key_2': 2}
    {}


* ### 要素全て削除


```python
x = {'key_1': 'value', 'key_2': 2}
print(x)

x.clear()
print(x)
```

    {'key_1': 'value', 'key_2': 2}
    {}


* ### キーの存在確認
if文で出てきたinを利用することで調べることができます。


```python
x = {'key_1': 'value', 'key_2': 2}
print('key_1' in x) ### 存在する場合はTrue
print('key_3' in x) ### 存在しない場合はFalse

### keys関数を利用するとキーのリストを取得できる。
print('key_1' in x.keys())
print('key_3' in x.keys())
```

    True
    False
    True
    False


* ### 値の存在確認


```python
x = {'key_1': 'value', 'key_2': 2}

### values関数を利用すると値のリストを取得できる。
print('value' in x.values())
print(1 in x.values())
```

    True
    False


* ### キーとバリューの組み合わせ存在確認


```python
x = {'key_1': 'value', 'key_2': 2}

### items関数を利用するとキーとバリューの組み合わせのリストを取得できる。
print(('key_1', 'value') in x.items())
print(('key_2', 3) in x.items())
```

    True
    False


## dictの内包表記
dictもlistと同様、新たなDict型の変数を作成する際に、内包表記を利用することができます。


```python
x = {}
for i in ['a','b','c']:
    ### キーは文字列にする必要があるのでstr関数を利用している
    x[str(i)] = i

print(x)
```

    {'a': 'a', 'b': 'b', 'c': 'c'}



```python
x = {str(i): i for i in ['a','b','c']}
print(x)
```

    {'a': 'a', 'b': 'b', 'c': 'c'}


イテラブルオブジェクトがDictの場合はitems関数を組み合わせて書くことができます。


```python
x = {'name_1': '山田', 'age_1': 25,'name_2': '佐藤', 'age_2': 20}
y = {key: value for key, value in x.items()}
print(y)
```

    {'name_1': '山田', 'age_1': 25, 'name_2': '佐藤', 'age_2': 20}


Listと同様にif文を組み合わせて利用することも可能です。


```python
x = {'name_1': '山田', 'age_1': 25,'name_2': '佐藤', 'age_2': 20}
y = {key: value for key, value in x.items() if 'name' in key}
print(y)
```

    {'name_1': '山田', 'name_2': '佐藤'}

