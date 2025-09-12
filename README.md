# **LM Studio Web Chat with File Upload**

これは、ローカルで実行されているLM Studioサーバーと対話するための、多機能なWebベースのチャットインターフェースです。テキストプロンプトに加えて、さまざまな種類のファイルをアップロードし、その内容をLLMへのコンテキストとして送信できます。

## **主な機能**

* **多様なファイル形式に対応**:  
  * テキストファイル (.txt, .md, .js, .py, .html, .css, .json, .csv)  
  * Microsoft Office ファイル (.docx, .xlsx)  
  * 画像ファイル (.png, .jpg, .gif, etc.)  
* **ファイルプレビュー**: アップロードしたファイルは、送信前にプレビューで確認・削除できます。  
* **マルチモーダルチャット**: テキストと画像を同時に送信し、マルチモーダルモデルと対話できます。  
* **マークダウン & シンタックスハイライト**: モデルからの返答はマークダウンとして整形され、コードブロックはシンタックスハイライト付きで表示されます。  
* **スタンドアロン**: サーバーサイドの処理は不要です。index.htmlをブラウザで開くだけで動作します。

## **使い方**

1. **LM Studioの準備**  
   * お使いのPCに[LM Studio](https://lmstudio.ai/)をインストールし、実行します。  
   * 左側のメニューから 🚀 アイコンをクリックし、ローカルサーバーを起動します。  
2. **接続先アドレスの編集**  
   * index.html ファイルを開き、297行目付近にあるfetch関数のURLを、あなたのLM Studioサーバーのアドレスに書き換えます。  
     // const response \= await fetch('\[http://xxx.xxx.xxx.xxx:1234/v1/chat/completions\](http://xxx.xxx.xxx.xxx:1234/v1/chat/completions)', {  
     const response \= await fetch('http://localhost:1234/v1/chat/completions', { // \<-- このように編集

3. **チャットの開始**  
   * 編集したindex.htmlファイルをWebブラウザで開きます。  
   * プロンプトを入力したり、「file」ボタンからファイルをアップロードしたりして、「Send」ボタンで送信します。

## **依存ライブラリ**

このプロジェクトは、以下の外部ライブラリをCDN経由で利用しています。

* [markdown-it](https://github.com/markdown-it/markdown-it)  
* [highlight.js](https://highlightjs.org/)  
* [mammoth.js](https://www.google.com/search?q=https://github.com/mwilliamson/mammoth.js)  
* [SheetJS (xlsx.js)](https://sheetjs.com/)

## **ライセンス**

このプロジェクトはMITライセンスの下で公開されています。詳細はLICENSE.txtファイルをご覧ください。