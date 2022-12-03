## 課題レポート5: 例外に慣れよう
### 学籍番号215402B 内藤一
****
### ステップ1: コードの準備。
### (a) [pushしたリポジトリURL](https://github.com/e215402/prog2-rep5)
### (b) java.lang.NullPointerExceptionについて教科書とAPIドキュメントで調べ、数行〜10行程度で説明せよ。
<br>
オブジェクトが必要な時に，アプリケーションがnullのフィールドを参照しようとした時にスロー
される．これには以下が挙げられる．<br>

* nullオブジェクトのインスタンスメソッドを呼び出す.
* nullオブジェクトのフィールドへのアクセス，変更する.
* nullの長さを配列の様に取得する.
* nullのスロットを配列の様にアクセス，変更する.
* Throwable値の様にnullをスローする.


### 参考文献:[公式ドキュメント: JDK 17](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/NullPointerException.html)
### ステップ2: 例外処理を記述せよ。
実行結果
```
❯ java Step1.java
NullPointerExceptionが発生しました
Cannot invoke "String.length()" because "<local1>" is null
```
### ステップ3: APIリファレンスを参照してみよう。
### (1) Integer.parseInt() メソッドの定義のコピペ。
```
public static int parseInt(String s)
                    throws NumberFormatException
Parses the string argument as a signed decimal integer. The characters in the string must all be decimal digits, except that the first character may be an ASCII minus sign '-' ('\u002D') to indicate a negative value or an ASCII plus sign '+' ('\u002B') to indicate a positive value. The resulting integer value is returned, exactly as if the argument and the radix 10 were given as arguments to the parseInt(java.lang.String, int) method.

Parameters:
s - a String containing the int representation to be parsed

Returns:
the integer value represented by the argument in decimal.

Throws:
NumberFormatException - if the string does not contain a parsable integer.
```
### 参考文献:[公式ドキュメント: JDK 17](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Integer.html#parseInt(java.lang.CharSequence,int,int,int))
### (2) 上記コピペ文を読み、項目毎に分かることを解説せよ。
*本文<br>
文字列の引数を符号付きの10進数として解析する．最初の文字が'+'か'-'であるかを除いて，文字列の文字は全て10進数でなければならない．

<br>
*Parameters<br>
解析されるint表現を含む文字列．
<br>
*Returns<br>
引数で指定された10進数の整数値．
<br>
*Throws<br>
文字列が解析可能な整数値を含まない場合．

### (3) NumberFormatExceptionクラスのスーパークラスの名称と、そのクラスの概要説明文（クラス名とConstructor Summaryの間にあるはず）をコピペし、分かる範囲で解説せよ。
[リンク](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/IllegalArgumentException.html)
```
Module java.base
Package java.lang
Class IllegalArgumentException

java.lang.Object
    java.lang.Throwable
        java.lang.Exception
            java.lang.RuntimeException
                java.lang.IllegalArgumentException

All Implemented Interfaces:
Serializable

Direct Known Subclasses:
IllegalChannelGroupException, IllegalCharsetNameException, IllegalFormatException, IllegalSelectorException, IllegalThreadStateException, InvalidKeyException, InvalidOpenTypeException, InvalidParameterException, InvalidPathException, InvalidStreamException, KeyAlreadyExistsException, NumberFormatException, PatternSyntaxException, ProviderMismatchException, UnresolvedAddressException, 
UnsupportedAddressTypeException, UnsupportedCharsetException
--------------------------------------------------------------------------------
public class IllegalArgumentException
extends RuntimeException

Thrown to indicate that a method has been passed an illegal or inappropriate argument.

Since:
1.0

See Also:

Serialized Form
```
メソッドに不正または不適な引数が渡されたことを示すためにスローされる．

