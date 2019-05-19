---
theme : "black"
transition : "default"
---

# 夢を叶える<br> <font color="gray">~~IoT~~</font> enebular
<font color="gray">~~IoTLT vol.51 @ 日本オラクル~~<br>
~~enebular meetup vol.11~~<br></font>
ノンコーディングで IoT する LT 会 @ ウフル
<style>
  .slides {
    width: 100% !important;
  }
  .reveal pre {
    display: -webkit-flex;
    display: flex;
    -webkit-justify-content: center;
    justify-content: center;
    -webkit-align-items: stretch;
    align-items: stretch;
  }
</style>


<div style="position:fixed; right:0; bottom:0; font-size: large; margin: 15px;"> powered by reveal.js/vscode-reveal</div>

---

## 自己紹介
- 名前:ほりひろ<br><img src="./assets/main_avatar.jpg">
- 職業
  - Azure (PaaS製品)のサポートエンジニア
  - 『dotstudio 技術顧問』<br>
    \# なお実績

---

# 早速いいわけ

--

※5/24 の IoTLT で喋る筈だった LT を<br>いろいろワケあって ここでします

<img src="./assets/iotltvol51.png" style="width:60%">
https://iotlt.connpass.com/event/128933/

皆様お誘い合わせの上、ぜひご参加ください

--

# 全力で<br>コーディング<br>しました<br>🙇‍🙇‍🙇‍


---

# 本題

--

# 夢<br>叶えていますか？

--

# 日本<img src="./assets/flag-for-japan.png" style="border: none; margin: 0px -8px -40px 0px;background: rgba(255,255,255,0)">に住むなら<br>一度はやってみたい

--

# それは、、、

--

# 元号発表！
<div style="display:flex; width:100%">
  <img src="./assets/japanera-heisei.jpg" style="width:50%; height:50%; border:0;">
  <img src="./assets/japanera-reiwa.jpg" style="width:50%; height:50%; border:0;">
</div>

--

# やったことある人🖐

---

# 新元号発表会見<br>ツールを作った

--

# できること

--

# 元号発表ごっこ

--

# つまり
- 漢字二文字をランダムに生成
- 元号発表<font style="color: #ff7777">ぽい</font>に筆文字で描画
- 出典も確認可能

---

# 材料

- enebular
- Web書道.com 
- 適度なサイズのタブレット (今回は iPad)
- 全力コーディングのやる気

--

# 出典情報
<iframe src="https://create-japan-newera.herokuapp.com/era-meta" style="background: white; width: 100%; height: 400px;"/>

---

# 頑張った<br>ポイント

--

## 出典元
- きちんと万葉集から引用<br>
  -> 歌の抽出<br>
  -> 漢字の抽出

--

## 徹底的な enebular 縛り (その1)
- ロジック
  - enebular の function で実装

--

## 徹底的な enebular 縛り (その1)
- UI
  - enebular の infomotion で実装<br>
    -> enebular の function で HTML を配信

--

## 徹底的な enebular 縛り (その1)

<div style="text-align:center"><img src="./assets/flow-httpserve.png" style="width:80%"></div>    

---

# 頑張らなかった<br>ポイント

--

## 頭文字チェック
- MTSHR と重複する可能性あり

--

## フォントチェック
- たまに描画できない文字<br>
  -> 目視で確認
- 失敗例
  <div style="text-align:center"><img src="./assets/failed_undrawable.jpg"></div>

--

## 重複文字、熟語チェック
- 同じ文字が抽出
- 既に使われている単語
  <div style="text-align:center"><img src="./assets/failed_samechars.jpg"><img src="./assets/failed_notmatch.jpg"></div>

---

# 機会がありましたら<br>是非ご活用ください
