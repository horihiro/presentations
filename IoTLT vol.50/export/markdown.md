
# Moddableで<br>Javascript IoT
🎉 IoTLT vol.50 🎉
<br>@ DEJIMA
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
- 名前
  - ほりひろ<br><img src="./assets/main_avatar.jpg">
- 職業
  - Azure (PaaS製品)のサポートエンジニア
  - 『dotstudio 技術顧問』(を名乗っていいんですよね？)<br>
    \# なお実績

---

## ちなみに
今回は vscode-reveal でスライド作って<br>
Visuals Studio Code で発表します

---

# Moddable SDK
- ECMAScript(Javascript) で<br>esp 系のマイコン実装ができる
- 多分マイナー

--

## IoTLT でも何度か登場
- わみさん @ IoTLT 名古屋 vol.9 
- 小坂さん @ SIer IoTLT vol.14

--

## dotstudio でブログ書いた
https://dotstud.io/blog/developed-iot-using-moddable/ <br>
<img style="width: 50%" src="./assets/moddable_at_dotstudio.png"><br>
<span style="font-size: smaller; color: darkgray">\# 最初で最新の技術顧問業</span>

---

# 何か作って<br>使い勝手を見てみる

--

## 🙇‍昔のネタの焼き直し🙇‍
<div style="position:relative; width:60%; margin-left: 20%">
  <img style="width: 100%" src="./assets/kanaianzen_system.png"/>
  <img style="width: 20%; position: absolute; top: 0; right: 20px" src="./assets/kanaianzen.png"/>
</div>
コレを Moddable SDK で再実装してみた

---

# Arduino SDK での実装

--

## いっぱい書いてた思ひ出
<img style="width: 80%" src="./assets/arduino_ide.png">

--

## Wi-Fi と BLE の同時利用に<br>手こずった思ひ出
<img style="object-fit: cover; object-position: top center; width: 800px; height: 400px" src="./assets/arduino_exception.png">

---

# 一方<br>Moddable SDK での実装

--

## BLE スキャン処理

```
const bleAddrList = {};
class Scanner extends BLEClient {
  onReady() {
    scanner.startScanning();
  }
  onDiscovered(d) {
    const hexString = Array.prototype.map.call(
      new Uint8Array(d.address), x => `00${x.toString(16)}`.slice(-2)
    ).join('');
    bleAddrList[hexString] = Date.now();
  }
}
const scanner = new Scanner;
```

--

## BLE アドレスの POST 処理

```
const postBleAddress = () => {
  setTimeout(() => {
    const body = JSON.stringify(bleAddrList);
    // HTTP POST request
    fetch(URL, {method: 'POST', body, ...})
      .then(/* onSucceeded */).catch(/* onFailed */)
      .then(postBleAddress);
  }, INTERVAL);
};
postBleAddress();
```

--

## この２つをくっつけて完成
Wi-Fi と BLE の同時利用も気にしない

--

# 簡単🤗

---


## でも注意点も結構ある

---

# 注意点<br>その１

--

## 環境構築がめんどい

基本は手順通りで出来るけど、、、

<img style="object-fit: cover; object-position: top center; width: 800px; height: 200px" src="./assets/moddable_setup.png">

<img style="object-fit: cover; object-position: top center; width: 800px; height: 200px" src="./assets/moddable_setup_esp32.png">

--

## 必要なツールのパスが決め打ち

変えることはできるけど、<br>
変え方は書いていないので、自己責任で。

---

# 注意点<br>その２

--

## 最初のビルドがクソおっそい🐢

--

## ⏳⏳5-10 分かかることも⌛⌛

---

# 注意点<br>その３

--

## おなじみのクラス／オブジェクトが無い
- console
- XMLHttpRequest／fetch
- タイマー系 (setTimeout 等)

--

## W3C/WHATWG 由来のモノは<br>提供されていない
- 規格の制定元が違うという大人の事情

--

## polyfill ライブラリー<br>はじめました
https://github.com/horihiro/moddable-polyfill<br>
<img style="object-fit: cover; object-position: top center; width: 800px; height: 400px" src="./assets/polyfill_github.png">

---

## 興味がある方人がいましたら<br>情報交換しましょう
公式リポジトリもやさしいです<br>
https://github.com/Moddable-OpenSource/moddable

---

# 終
<font style="border-bottom: 5px solid white;">制作・著作</font><br>
<div style="position: relative">
  <font style="line-height: 1.8em;position: absolute;top: 0;left: 0; width: 100%;letter-spacing: 0.35em; font-size: 0.8em;">ほりひろ</font>
  <font style="line-height: 1.8em;position: absolute;top: -0.2em; left: -0.1em; width: 100%;">◯◯◯◯</font>
</div>
