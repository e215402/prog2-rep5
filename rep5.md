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


### 参考文献[公式ドキュメント: JDK 17](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/NullPointerException.html)
### ステップ2: 例外処理を記述せよ。
実行結果
```
❯ java Step1.java
NullPointerExceptionが発生しました
Cannot invoke "String.length()" because "<local1>" is null
```
### ステップ3: APIリファレンスを参照してみよう。
#### (1) Integer.parseInt() メソッドの定義のコピペ。


#### (2) 上記コピペ文を読み、項目毎に分かることを解説せよ。


#### (3) NumberFormatExceptionクラスのスーパークラスの名称と、そのクラスの概要説明文（クラス名とConstructor Summaryの間にあるはず）をコピペし、分かる範囲で解説せよ。
