---
theme: "sky"
transition: "slide"
highlightTheme: "monokai"
slidenumber: true
title: "HTML勉強会"
---

# HTML勉強会

2回目

---

## 前回行ったこと

- 2-3 HTMLファイルの骨組み
- 2-4 HTMLの基本的な書き方
- 2-5~11 代表的なタグ
  - 2-5 h1~h6
  - 2-6 p
  - 2-7 img
  - 2-8 a

---

## 本日のお題目

- 2-5~11 代表的なタグ {.fragment .fade-right}
  - 2-9 ul, ol, li
  - 2-10 table
  - 2-11 form
  - 2-11 input

---

## 2-9 ul, ol, li（リスト）

Webサイトで使用される黒丸リストや数字リストを作成するためのタグです。  
  
↓こんなやつ  
【黒丸】
<div>
  <ul>
    <li>リスト1</li>
    <li>リスト2</li>
    <li>リスト3</li>
  </ul>
</div>
<br/>
【数字】
<div>
  <ol>
    <li>リスト1</li>
    <li>リスト2</li>
    <li>リスト3</li>
  </ol>
</div>

---

### ul(箇条書きリスト)

箇条書きリストは`<ul>`タグで囲みます。  
`<li>`タグでリストの項目を記述します。  
※ulはunordered listの略、順序がないリストの意味です。  
※liはlist itemの略、リストの項目の意味です。  


```html
<ul>
  <li>リスト1</li>
  <li>リスト2</li>
  <li>リスト3</li>
</ul>
```
---

### ol(順序リスト)

順序リストは`<ol>`タグで囲みます。  
`<li>`タグでリストの項目を記述します。
※olはordered listの略、順序があるリストの意味です。

```html
<ol>
  <li>リスト1</li>
  <li>リスト2</li>
  <li>リスト3</li>
</ol>
```

---

## 2-10 table（表）

表を作成するためのタグです。  
`<table>`タグで表全体を囲み、`<tr>`タグで行を、`<td>`タグでセルを作成します。  

タグ|目的
---|---
table|表を示すタグ。表全体を囲む
tr|表の１行を囲む。table rowの略
th|表の見出しとなるセルを作成。table headerの略
td|表のデータを示すセルを作成。table dataの略


---

### 実装例

```html
<table border="1">
  <tr>
    <th>プラン名</th>
    <th>料金</th>
  </tr>
  <tr>
    <td>わくわくプラン</td>
    <td>月額2000円</td>
  </tr>
  <tr>
    <td>にこにこプラン</td>
    <td>月額1900円</td>
  </tr>
</table>
```

<table border="1">
  <tr>
    <th>プラン名</th>
    <th>料金</th>
  </tr>
  <tr>
    <td>わくわくプラン</td>
    <td>月額2000円</td>
  </tr>
  <tr>
    <td>にこにこプラン</td>
    <td>月額1900円</td>
  </tr>
</table>

---

### 横方向にセルを繋げる

横方向にセルを繋げる場合は`colspan`属性を使用します。

```html
<table border="1">
  <tr>
    <th colspan="2">セル１＋２ ←ここ！！
    <!-- <th>セル２</th> -->
  </tr>
  <tr>
    <td>セル３</td
    <td>セル４</td>
  </tr>
  <tr>
    <td>セル５</td>
    <td>セル６</td>
  </tr>
</table>
```

---

### 縦方向にセルを繋げる

縦方向にセルを繋げる場合は`rowspan`属性を使用します。

```html
<table border="1">
  <tr>
    <th rowspan="2">セル１＋３ ←ここ！！
    <!-- <th>セル２</th> -->
  </tr>
  <tr>
    <td>セル２</td>
  </tr>
  <tr>
    <td>セル４</td>
    <td>セル５</td>
  </tr>
</table>
```

---

## 2-11 form（フォーム）

お問い合わせや検索ボックス、会員登録などで様々な入力を行うためのタグです。  
`<form>`タグでフォーム全体を囲み、`<input>`タグで入力欄を作成します。

↓こんなやつ  
<form>
  <input type="text" name="name" placeholder="名前"><br>
  <input type="email" name="email" placeholder="メールアドレス"><br>
  <input type="submit" value="送信">
</form>

---

### formタグの書き方

属性|用途
---|---
action|フォームデータを送信する先のURLを指定
method|フォームデータを送信する際のHTTPメソッドを指定（get or post）
name|フォームの名前を指定  
<br>

```html
<form action="送信先のURL" method="post" name="フォーム名">
  ここにフォーム情報を入力
</form>
```

---

### inputタグの書き方

inputタグはフォームに入力欄を作成するためのタグです。
type属性で入力欄の種類を指定します。

属性値|用途
---|---
text|1行のテキスト入力欄
search|検索ボックス
email|メールアドレス入力欄
tel|電話番号入力欄
url|URL入力欄
password|パスワード入力欄

```html
<input type="text" name="name" placeholder="名前"><br>
<input type="search" name="search" placeholder="検索"><br>
<input type="email" name="email" placeholder="メールアドレス"><br>
<input type="tel" name="tel" placeholder="電話番号"><br>
<input type="url" name="url" placeholder="URL"><br>
<input type="password" name="password" placeholder="パスワード"><br>
```

---

### ラジオボタンを作る

ラジオボタンは`type="radio"`を指定します。

属性|用途
---|---
name|ラジオボタンのグループ名
value|ラジオボタンの値
checked|初期状態で選択されている状態にする

```html
<input type="radio" name="gender" value="男" checked>男
<input type="radio" name="gender" value="女" >女
<input type="radio" name="gender" value="その他" >その他
```

<input type="radio" name="gender" value="男" checked>男
<input type="radio" name="gender" value="女" >女
<input type="radio" name="gender" value="その他" >その他

---

### チェックボックスを作る

チェックボックスは`type="checkbox"`を指定します。
属性|用途
---|---
name|チェックボックスのグループ名
value|チェックボックスの値
checked|初期状態で選択されている状態にする

```html
<input type="checkbox" name="hobby" value="赤" checked>赤
<input type="checkbox" name="hobby" value="青">青
<input type="checkbox" name="hobby" value="黄">黄
<input type="checkbox" name="hobby" value="緑">緑
```

<input type="checkbox" name="hobby" value="赤" checked>赤
<input type="checkbox" name="hobby" value="青">青
<input type="checkbox" name="hobby" value="黄">黄
<input type="checkbox" name="hobby" value="緑">緑

---

### 送信ボタンを作る

フォームに入力した情報を送信するためのボタンは`type="submit"`を指定します。

属性|用途
---|---
name|ボタンの名前
value|ボタンに表示されるテキスト

```html
<input type="submit" name="submit" value="送信">
```

<input type="submit" name="submit" value="送信">

---

### ボタンに画像を使いたい場合

属性|用途
---|---
name|ボタンの名前
src|ボタンに表示される画像のURL
alt|画像が表示されない場合の代替テキスト

```html
<input type="image" src="images/button.png" alt="送信する">
```

<input type="image" src="img/button.png" alt="送信する">

---

### セレクトボックスを作る

selectタグ
属性|用途
---|---
name|セレクトボックスの名前
multiple|複数選択可能にする

optionタグ
属性|用途
---|---
value|選択肢の値
selected|初期状態で選択されている状態にする

---

```html
血液型
<select name="bloodtype">
  <option value="A">A</option>
  <option value="B">B</option>
  <option value="O" selected>O</option>
  <option value="AB">AB</option>
  <option value="不明">不明</option>
</select>
```

<select name="bloodtype">
  <option value="A">A</option>
  <option value="B">B</option>
  <option value="O" selected>O</option>
  <option value="AB">AB</option>
  <option value="不明">不明</option>
</select>

