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

- 2-5~11 代表的なタグ
  - 2-9 ul, ol, li
  - 2-10 table
  - 2-11 form
  - 2-11 input
- 2-12 フォームのラベルを作る
- 2-13 ブロック要素でグループ分けを行う
- 3-1 CSSとは
- 3-2 CSSを適用させる方法
- 3-3 CSSファイルを作ろう
- 3-4 CSSの基本的な書き方

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

実装結果
<ul>
  <li>リスト1</li>
  <li>リスト2</li>
  <li>リスト3</li>
</ul>
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

実装結果
<div>
  <ol>
    <li>リスト1</li>
    <li>リスト2</li>
    <li>リスト3</li>
  </ol>
</div>

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

実装結果

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

<p>実装結果</p>
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

<p>実装結果</p>
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

---

### 複数行の入力欄を作る

textareaタグを使用すれば複数行にわたるテキストを入力できます
テキストタグで文字を囲むと囲んだ文字が初期表示で表示されます
  
```html
<textarea name="message">メッセージ入力</textarea>
```

<textarea name="message">メッセージ入力</textarea>

記入例などを入れたい場合はplaceholder属性を使用します

```html
<textarea name="message" placeholder="メッセージ入力"></textarea>
```

<textarea name="message" placeholder="メッセージ入力"></textarea>

---

## 2-12 フォームのラベルを作る

ラベルは`<label>`タグで作成します。
`for`属性に対象のinputタグのidを指定することで、ラベルをクリックすると入力欄にフォーカスが当たります。

```html
  <form action="example.php" method="post" name="contact-form">
      <input type="checkbox" name="travel" value="日本国内" id="japan"> <label for="japan">日本国内</label>
      <input type="checkbox" name="travel" value="ヨーロッパ" id="europe"> <label for="europe">ヨーロッパ</label>
      <input type="checkbox" name="travel" value="東南アジア" id="asia"> <label for="asia">東南アジア</label>
  </form>
```
実装結果
<form action="example.php" method="post" name="contact-form">
    <input type="checkbox" name="travel" value="日本国内" id="japan"> <label for="japan">日本国内</label>
    <input type="checkbox" name="travel" value="ヨーロッパ" id="europe"> <label for="europe">ヨーロッパ</label>
    <input type="checkbox" name="travel" value="東南アジア" id="asia"> <label for="asia">東南アジア</label>
</form>

---

## 2-13 ブロック要素でグループ分けを行う

Webサイトは様々な構成要素を組み合わせて作られています。
例えばナビゲーションメニュー、本文、関連記事の一覧など。
これらを１つの塊として囲みグループ化していきます。

```html
<body>
    <h1>明日の天気</h1>
    <p>明日は曇のち晴れでしょう。</p>
    <h2>おすすめの着こなし</h2>
    <p>この時期は暖かい気温が続きますが、一枚羽織る服があるといいでしょう。</p>
</body>
```
↓
```html
<body>
    <article>
        <h1>明日の天気</h1>
        <p>明日は曇のち晴れでしょう。</p>
    </article>
    <section>
        <h2>おすすめの着こなし</h2>
        <p>この時期は温かい気温が続きますが、一枚羽織る服があるといいでしょう。</p>
    </section>
</body>
```

---

ブロックごとに背景色を変えることが可能
<article style="background-color:tomato">
    <h1 style="font-size:3rem">明日の天気</h1>
    <p>明日は曇のち晴れでしょう。</p>
</article>
<section  style="background-color:white">
    <h2 style="font-size:3rem">おすすめの着こなし</h2>
    <p>この時期は温かい気温が続きますが、一枚羽織る服があるといいでしょう。</p>
</section>

---

#### よく使うブロック要素

要素|用途
---|---
header|ページ上部のヘッダー部分を作るタグ
nav|ナビゲーションメニューを作るタグ
article|読み物、記事の部分をタグ
section|テーマを持ったグループを作るタグ
main|メインコンテンツ部分を作るタグ
aside|メインコンテンツではない、補足情報を作るタグ
footer|ページ下部のフッター部分を作るタグ
div|意味を持たないブロック要素を作る

---

## 3-1 CSSとは

### 文書を飾り付けるのがCSS

CSSはCascading Style Sheetsの略で、HTML文書を装飾するための言語です。
CSSファイルを保存する場合は拡張子を`.css`とします。

---

## 3-2 CSSを適用させる方法

- CSSを読み込んで適用させる
- HTMLの`<head>`タグ内に`<style>`タグで指定する
- HTMLの`<style>`属性で指定する

<p style="text-align:left">
※同時に指定した場合、下の方が優先度が高くなります
</p>

---

#### CSSを読み込んで適用させる

```html
<head>
    <meta charset="UTF-8">
    <title>猫の実態</title>
    <meta name="description" content="猫の好きなもの、日々の生活をご紹介">
    <link rel="stylesheet" href="style.css">
</head>
```

#### HTMLの`<head>`タグ内に`<style>`タグで指定する

```html
<head>
    <meta charset="UTF-8">
    <title>猫の実態</title>
    <meta name="description" content="猫の好きなもの、日々の生活をご紹介">
    <style>
        h1 { color: #f00; }
        p { font-size: 18px; }
    </style>
</head>
```

#### HTMLの`<style>`属性で指定する

```html
<h1 style="color: #f00;">猫の一日</h1>
<p style="font-size: 18px;">ひたすら寝ています。</p>
```

---

## 3-3 CSSファイルを作ろう

CSSファイル作成の手順

- CSSファイルを作成する
- CSSコードを書く
- HTMLファイルにCSSファイルを読み込む

---

### CSSファイルを作成する

拡張子を`.css`として保存します。  
命名規約以下の通りです。  

1. 半角英数字のみを使用する
1. 記号は「-」（ハイフン）、「_」（アンダースコア）のみ使用する
1. 機種依存文字は使用しない
1. 全角スペース、半角スペース(Space)は使用しない
1. 必ずアルファベットから開始する
1. ファイル名は全て小文字で統一する

---

### CSSコードを書く

```css
@charset "UTF-8";
body {
    background-color: #fffeee;
}
 h1 {
    color: #0bd;
} p{
    font-size: 20px;
}
```

1行目には@charset "UTF-8";を記述することで文字コードを指定します。  
これを書くことで文字化けを防ぐことができます。  
新規で作成する際は必ず記述しましょう。

---

### HTMLファイルにCSSファイルを読み込む

```html
<head>
    <meta charset="UTF-8">
    <title>猫の実態</title>
    <meta name="description" content="猫の好きなもの、日々の生活をご紹介">
    <link rel="stylesheet" href="style.css">
</head>
```
headタグに<link rel="stylesheet" href="style.css">を記述することでCSSファイルを読み込むことができます。

href属性にはCSSファイルのパスを指定します。

---

## 3-4 CSSの基本的な書き方

CSSはセレクタとプロパティ、値の組み合わせて「どの部分の、どれを、どうするか」を指定します。

![](img\CSS書き方.png)

内容|説明
---|---
セレクタ|どの部分を装飾するかを指定
プロパティ|何を変更するかを指定
値|見た目をどのように変えるかを指定

---

### 複数のセレクタを指定する


セレクタをカンマで区切ることで複数のセレクタを指定することができます。

```css 
h1, h2 {
    color: #f00;
}
```

---

### クラス・IDで要素を指定する

クラスを指定する場合は「.」（ドット）を、IDを指定する場合は「#」（シャープ）を使用します。

HTML
```html
<p class="red">赤い文字</p>
<p id="blue">青い文字</p>
```

CSS
```css
/* クラスを指定 */
.red {
    color: #f00;
}
/* IDを指定 */
#blue {
    color: #00f;
}
```

---

### クラスとIDの違い

IDはページ内で一意である必要があります。  
クラスは複数の要素に適用できます。

補足：
IDを使用してページ内リンクを作成することができます

HTML
```html
<a href="#contents">コンテンツを見る</a>
・・・そのほかのコンテンツ・・・
<div id="contents">
  <p>ここまでジャンプします</p>
</div>
```

---

### 複数のクラスを指定する

複数のクラスを指定する場合は、スペースで区切ります。

```html
<p class="red bold">赤くて太字</p>
```

```css
.red {
    color: #f00;
}
.bold {
    font-weight: bold;
}
```

---

### タグとクラスを組み合わせて指定する

タグとクラスを組み合わせて指定する場合は、  
「タグ名.クラス名」で記述します。  
IDの場合は「タグ名#ID名」で記述します。

HTML

```html
<h1 class="red">赤い文字</p>
<p class="red">赤い文字</p>
```

CSS

```css  
p.red {
    color: #f00;
}
```

↑の例だとPタグだけが赤くなります

---

### 子孫セレクタ

親とその子孫という形で指定するセレクタです。親と子孫は半角スペースで区切ります。子孫はいくつでも指定できます。子孫セレクタは、idセレクタ、classセレクタ、要素セレクタなど他のセレクタと組み合わせて指定します。

---

下記の場合はclass名「sec」内のすべてのpタグが対象になります。

HTML

```html
<div class="sec">
  <p>子の段落です</p>
  <div>
    <p>子孫の段落です</p>
    <div>
      <p>子孫の段落です</p>
    </div>
  </div>
</div>
```

CSS

```css
.sec p{
  color: #00ffff;
}
```

---

### 直接の子セレクタ

親と直下の要素で指定するセレクタです。親と子は「>」で区切ります。子は、いくつでも指定ができます。子孫セレクタと同じくidセレクタ、classセレクタ、要素セレクタなど他のセレクタと組み合わせて指定します。子孫セレクタとの違いは、親の直下の要素のみが対象となります。

---

HTML

```html
<div class="sec">
  <p>子の段落です</p>
  <div>
    <p>子孫の段落です</p>
    <div>
      <p>子孫の段落です</p>
    </div>
  </div>
</div>
```

CSS

```css
.sec > p{
  color: #00ffff;
}
```

---

### 全称セレクタ（ユニバーサルセレクタ）

*（アスタリスク）をセレクタにすると、すべての要素が対象になります。主にCSSのリセットや初期設定に使用します。下記は、すべてのタグの「外余白」「内余白」をなしにします。

CSS

```css
*{
  margin: 0;
  padding: 0;
}
```

---

子孫セレクタ、子セレクタに使用すると親要素内の子孫または子すべての要素が対象になります。記の場合はclass名「sec」内のdivタグ、pタグが対象になります。

```html
<div class="sec">
  <p>子の段落です</p>
  <div>
    <p>子孫の段落です</p>
    <div>
      <p>子孫の段落です</p>
    </div>
  </div>
</div>
```

CSS

```css
.sec *{
  color: #00ffff;
}
```
