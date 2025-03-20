

## エラーメッセージ

PHPは、スクリプトの文法上の誤りや、動作上の不具合をブラウザの画面に表示してくれます。

1. `public`ディレクトリ内に`error.php`を作成します。左のバーから`public`を選択し、右クリックで「新しいファイル...」を選択してください。 ![](./images/new_file.png)
2. ファイル名を`error.php`と入力するとファイルが作成できます。
3. `error.php`に下記コードを書いてください。<br>

  `error.php`

  ```php

    <!DOCTYPE html>

    <html lang="ja">

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>エラーPHP</title> <!-- タイトルも変更する -->
    </head>

    <body>
        <?php
        echo <p>Hello,PHP</p>; // 文字列をシングルクォーテーションで囲まなかった  
        ?>
        <p>0J0X0XX神戸電子</p>
    </body>

    </html>
  ```
1. 先ほどと同様VSCode下部の**ポート**をクリックしてください。

![](./images/port-view.png)

2. マウスカーソルをあてる(ホバーする)と、地球マークが出てくるので選んでください。

![](./images/port-view-hover.png)

3. ブラウザが立ち上がり、アドレスバーに`http://localhost:ポート番号`と表示されるので、末尾に`/error.php`を追記してエンターを押してください。

4. 次のように表示されます。
![](./images/error.png)<br>

このメッセージは、次のように解釈することができます。<br>

   - `Parse error: syntax error, unexpected '<'`<br>
   予期しない `<` による構文エラー<br><br>

   - `in /var/www/error.php on line 12`<br>
   その `<` は`error.php`の12行目に書かれている。<br><br>

## 課題の作成と提出

### テキストファイルの追加(add)とコミット(commit)

1. 課題として提出するファイルをVSCodeで開きます。VSCodeのメニューから「ファイル->フォルダーを開く」を選択し、<br>`C:¥web_app_dev¥03-first-php-GitHubのユーザー名`を選択してください。
2. VSCodeサイドバーのGit Graphのアイコンを押す。
3. 変更の欄に`hello.php`,`error.php`が表示されていることを確認し、+ボタンを押す。<br>
![](./images/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202023-04-12%2017.04.21.png)
1. 「ステージされている変更」に移動していれば、addは成功。
2. メッセージの欄にメッセージを入力し、✔のボタンを押すとcommitは完了。<br><br>

### テキストファイルをプッシュ(push)する

あとは課題を提出するのみ。

1. 変更の同期ボタンを押す。<br>![](./images/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202023-04-21%209.35.15.png)<br>
※ちなみにこの「変更の同期ボタン」は、「Branchの発行」という文言に変わることもあるが、どちらもリポートリポジトリにpushできるので問題ありません。

1. ブラウザで、再度課題のリンクにアクセスすると(cloneで使ったURLでも良い)、編集内容が反映されているのがわかる。<br>
<img src="./images/push.png" width="90%">

### (※追記)Dev Containersを起動した状態で、add、commit、pushができない場合

Dev Containersを起動した状態で、commitなどしようとした際、`Managed unsafe...`というメッセージが出るだけでうまくできないという学生が散見されます。その場合、下記のいずれかを実施してください。

#### ワークスペースの信頼を管理

1. コマンドパレットを開いて(Ctrl-Shift-P MacはCmd-Shift-P)、`workspace trust`と入力 ![](./images/seigen2.png)
2. 「親ディレクトリを信頼」を押す
   ![](./images/seigen3.png)

#### (追記)Dev Containers一旦停止してpush

1. コマンドパレットを開いて、`dev containers local`と入力
2. 「フォルダーを再度ローカルで開く(Dev Containers: Reopen Folder Locally)」を選択
3. すると普通にadd、commit、pushができるようになります

## 採点について(今回の課題から)

今回から、提出した課題がGitHub上で自動採点されます。pushした課題が合格したかはpush後に必ず確認してください。

### 課題の合格基準について

- `hello.php`をブラウザで開いた時、`Hello,PHP`と表示されること
- PHPの出力命令を用いて出すこと
- **最初の**「pタグ」の要素として出すこと

### 合格確認方法

1. 課題を提出してください。※既に実施済み
1. 下記青色背景のリンクからリモートリポジトリにアクセスしてください。※もしこのページを閉じている方は、[今回の課題ページ](https://classroom.github.com/a/S1hjL1LX)からアクセスすることができます<br>
   ![](./images/repository_link.png)
2. 画面上部にある`Actions`をクリックしてください。<br>
   <img src="./images/actions.jpg" width="70%">
3. **一番上**の行のタイトル横に、緑色のチェックが入っていればOK。<br>
   ![](./images/autograding.jpg)

### エラーが出た時の対処法

自動採点がエラーになると、タイトルの横に赤いばつ印がでます。その場合の解決策を下記に示します。

#### タイムアウトになっていないかを確認する

※タイムアウト自体はGitHubの仕様上防ぎようがありませんので、あらかじめご了承ください。タイムアウトになっている場合は、GitHub上で処理を再開すると解決できます。<br>
例えば、エラーが出た場合、右端の赤枠で囲まれている箇所に処理時間があります。ここが4分前後かかっている場合は、まずタイムアウトの可能性を疑ってください。
![](./images/timeout1.png)

具体的なタイムアウトの確認・解決方法は、

  1. `Actions`のタイトルが下記のようにリンクになっているので、クリック
      ![](./images/timeout2.png)
  2. `Arun-autograding-tests.png`をクリック
      ![](./images/run-autograding-tests.png)
  3. 赤いばつ印が出ている行をクリックし、開く
      ![](./images/timeout4.png)
  4. `Operation timed out after 180000 milliseconds with 0 bytes received`のメッセージがあればタイムアウト
      ![](./images/timeout5.png)
  5. 解決策としては、右上に`Re-run jobs`(再実行)のボタンがあるので、`Re-run failed jobs`(失敗した処理だけ再実行)をクリックしてください。
      ![](./images/timeout6.png)<br>
      ![](./images/timeout7.png)
  6. タイムアウトにならず処理が終了したらOK。また、タイムアウトになった場合は、同じことを繰り返す。※タイムアウトでないエラーは、次の解決策を参照。

### プログラムが正確に書かれているか確認する

プログラムが正確に書かれているかを確認してください。たとえ、ブラウザの画面でそれっぽく表示されても、自動採点ですので融通は聞きません。エラーが出た際は、以下の点を確認してください。

- `Hello,PHP`の大文字と小文字が正しく書けているか
- `Hello,PHP`の前後、間にスペースが入っていないか
- HTMLタグ(`<>`で囲まれているもの)が正しく書けているか
  
  - `Hello,PHP`前後の、`<p>`タグ大事です。HTMLでブラウザにテキスト(文字情報)を表示するときは、`<p>`タグなど、何らかのタグで括られているのが一般的です。タグの記述をおろそかにしないようにしましょう。

## (追記)Dev Containersの停止方法

1. コマンドパレットを開いて、`dev containers local`と入力
2. 「フォルダーを再度ローカルで開く(Dev Containers: Reopen Folder Locally)」
