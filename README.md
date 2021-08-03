# elevatorScroll

---

[]()

---

* [デモページ]()

* [導入例]()

* [FAQ]()

---

elevatorScrollはシンプル且つデザイン性の高いWEBサイトを作成できるプラグインです。

左右に2分割で表示し、左右非対称にスクロールするアニメーションは、
よりスタイリッシュな見た目を実現できます。

左右のセクションは高さに制限なく、デバイスの画面サイズを超えても違和感なく表示できたり、
フルスクリーンで見せたいセクションにも対応できたりなど、
より柔軟に自身の想像を可能にできます。

---

* [導入方法]()

* [HTML構造]()

* [elevatorScroll初期設定]()

* [オプション]()

<br>

## 導入方法

### Install
elevatorScrollのファイルをインストールして使用する場合、
__elevator_scroll.js__, __elevator_scroll.css__ の2つのファイルをインストールした後、
以下のように読み込みします。

```html
<link rel = "stylesheet" type = "text/css" href = "elevator_scroll.css">
<script type = "text/javascript" src = "elevator_scroll.js">
```

### CDN
CDNを使用してファイルのロードを行う場合

<br>

## HTML構造

elevatorScrollには独自のクラスがあり、
es-left, es-rightは画面を左右に分けるクラスで
その子要素にes-sectionというクラスを付与します。
es-sectionの中にhtmlを記述していく事で左右にその中身が表示されていきます。

以下がサンプルコードになります。

```html
<div id="elevator_scroll">
	<div class="es-left">
		<div class="es-section"><p>セクション1_left</p></div>
		<div class="es-section"><p>セクション2_left</p></div>
		<div class="es-section"><p>セクション3_left</p></div>
	</div>
	<div class="es-right">
		<div class="es-section"><p>セクション1_right</p></div>
		<div class="es-section"><p>セクション2_right</p></div>
		<div class="es-section"><p>セクション3_right</p></div>
	</div>
</div>
```

<br>

## elevatorScroll初期設定

<details>

<summary>初期設定は必須でありscriptタグ内に記述していきます</summary>

以下がサンプルコードです。

```javascript
<script>
	var obj = new elevator_scroll('#elevator_scroll', {
		sectionsName: ['section1', 'section2', 'section3']
	});
</script>
```

インスタンスを生成、elevatorScrollの要素を引数に渡し、
sectionsNameにセクション数と同じ数のセクション名を設定します。

</details>

<br>

## オプション

各種オプションの設定方法

### sectionsColor
<details>

<summary>各セクションごとに背景色を設定</summary>

```javascript
var obj = new elevator_scroll('#elevator_scroll', {
	sectionsColor: ['#ffdd79', '#ffffff', '#f2f2f2']
});
```

</details>

### menu
<details>

<summary>ヘッダーナビゲーションにリンク機能追加</summary>
html

```html
<header>
    <ul id="nav">
        <li><a href="#section1">セクション1</a></li>
        <li><a href="#section2">セクション2</a></li>
        <li><a href="#section3">セクション3</a></li>
    </ul>
</header>
```

javascript

```javascript
var obj = new elevator_scroll('#elevator_scroll', {
	menu:'#nav'
});
```

</details>

### activeMenu
<details>
<summary>現在のセクション位置のナビゲーションliタグにactiveクラスを付与</summary>

```javascript
var obj = new elevator_scroll('#elevator_scroll', {
	sectionsName: ['about', 'service1', 'service2', 'contact'],
	activeMenu: ['about', ['service1', 'service2'], 'contact',]
});

```
</details>

### animateSpeed
<details>

<summary>スクロールアニメーションの速度を設定</summary>

```javascript
var obj = new elevator_scroll('#elevator_scroll', {
	animateSpeed: 2
});
```
(デフォルト値:1)

</details>

### wheelDelta
<details>
<summary>スクロールに必要なマウスホイールの回転量を設定</summary>

```javascript
var obj = new elevator_scroll('#elevator_scroll', {
	wheelDelta: 200
});
```

(デフォルト値:100)

</details>

### touchMove
<details>
<summary>スクロールに必要なスマートフォンのスワイプ量を設定</summary>

```javascript
var obj = new elevator_scroll('#elevator_scroll', {
	touchMove: 200
});
```

(デフォルト値:100)

</details>
