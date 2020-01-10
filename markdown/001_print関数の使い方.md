# print関数の使い方
print関数とは、プログラムからコンソールや画面に文字列を出力する関数です。  
高頻度で利用するのでしっかり覚えておきましょう。

## 基礎文法


```python
print('Hello World.')

# 第２引数はデフォルトで改行文字になっているので、
# 空文字に置き換えると改行されなくなります。
print('Hello ', end='')
print('World.')
```

    Hello World.
    Hello World.



```python
### 変数の中身を確認する際にも利用できます。
something = '何らかの文字列'
print(something)

### 変数が数値でも出力できます。
somedigit = 12345
print(somedigit)
```

    何らかの文字列
    12345


## format関数
テンプレート化した文字列の途中で変数を展開する "format関数" もprint関数と一緒によく利用されます。


```python
### 指定部分に変数を展開
print('Hello {}.'.format('World'))
print('Hello {}.'.format('Python'))

### 次のような使い方もできます。
template = 'Hello {}.'
something = 'World'
print(template.format(something))
something = 'Python'
print(template.format(something))
```

    Hello World.
    Hello Python.
    Hello World.
    Hello Python.


## f記法
format関数と同様の処理を行いますが、python3.6以降からは、よりスッキリと記述できる "f記法" という書き方があります。


```python
### 注意： format関数と違って、先に変数を用意しておく必要があります。
something = 'World'
### 展開したい部分に変数を指定します。
print(f'Hello {something}.')
```

    Hello World.

