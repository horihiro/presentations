---
theme : "black"
transition: "zoom"
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
    \# この会社の技術顧問て、、、

---

## 早速いいわけ

--

※5/24 の IoTLT で喋る筈だった LT を<br>いろいろワケあって ここでします

<img src="./assets/iotltvol51.png" style="width:60%">
https://iotlt.connpass.com/event/128933/

皆様お誘い合わせの上、ぜひご参加ください

--

# 全力で<br>コーディング<br>しました<br>🙇‍🙇‍🙇‍

--

# LT ツール／スタイル、<br>という点をお楽しみください

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

# 新元号発表ガチャ<br>ツールを作った

--

# できること

--

## 元号発表ごっこ
<img src="./assets/design.png" style="width:50%; height:50%; border:0;">

--

## 作った元号の出典

<section>
<p class="fragment fade-in"> ↓ これは InfoMotion で作成</p>
</section>
<iframe src="https://create-japan-newera.herokuapp.com/era-meta" style="background: white; width: 80%; height: 400px;"/>

--

## つまり
- 漢字二文字をランダムに生成
- 元号発表<font style="color: #ff7777; font-width: bold">ぽい</font>に筆文字で描画
- 出典も確認可能

---

## 材料

<section>
<ul>
  <li><p class="fragment fade-in"><img src="https://enebular.com/favicon.ico" style="border: none; margin: 0px 4px -5px 0px;background: rgba(255,255,255,0)">enebular</p></li>
  <li><p class="fragment fade-in"><img src="https://www.gstatic.com/devrel-devsite/v0c74e6a7a755f75df39dc9a7dc5197ded60c6c2abf3c8fbd17a4917b5c78a143/firebase/images/favicon.png" style="border: none; margin: 0px 4px -5px 0px;background: rgba(255,255,255,0)">Firebase</p></li>
  <li><p class="fragment fade-in">️️️️<img src="https://images.emojiterra.com/google/android-pie/128px/1f58c.png"  style="width: 32px;border: none; margin: 0px 4px -5px 0px;background: rgba(255,255,255,0)">Web書道.com</p></li>
  <li><p class="fragment fade-in">️️️️<img src="https://images.vexels.com/media/users/3/128862/isolated/preview/5b021d17fb3643d144434b4cc6c3a74c-tablet-flat-icon-by-vexels.png"  style="width: 32px;border: none; margin: 0px 4px -5px 0px;background: rgba(255,255,255,0)">タブレット (今回は iPad)</p></li>
  <li><p class="fragment fade-in">💪やる気＆ゴリッゴリのコーディング</p>
      <p class="fragment fade-in" style="color: gray"># あれ、Azureがない</p></li>
</ul>
</section>

---

# 頑張った<br>ポイント

--

## 出典元
- きちんと万葉集から引用<br>
  -> 歌の抽出<br>
  -> 漢字の抽出

--

## 徹底的な enebular 縛り
<section>
<ul>
  <li><p class="fragment fade-in">ロジック</p>
    <ul>
      <li>
        <p class="fragment fade-in">enebular の function で実装</p>
      </li>
    </ul>
  </li>
  <li><p class="fragment fade-in">UI</p>
    <ul>
      <li>
        <p class="fragment fade-in">enebular の infomotion で実装</p>
        <p class="fragment fade-in">-> enebular の function で HTML を配信<br>
        <img src="./assets/flow-httpserve.png" style="width:50%;position:absolute;bottom:-200px"></p>
      </li>
    </ul>
  </li>
</ul>
</section>

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
