# CakePHP3のプロジェクト作成

##### 以下はWindowsで開発することを前提とした環境の構築手順です。  

## ◆使用ソフトウェア
|ソフト/FW|参照先|
|----|----|
|XAMPP|[https://www.apachefriends.org/jp/index.html](https://www.apachefriends.org/jp/index.html)|
|Composer|[https://getcomposer.org/](https://getcomposer.org/)|
|CakePHP3|[https://cakephp.org/jp](https://cakephp.org/jp)[![alt](/img/trasition.png)](https://book.cakephp.org/3/ja/index.html)|

## ◆XAMPPインストール
[こちら](https://sourceforge.net/projects/xampp/files/) からXAMPPのzip形式をダウンロード、解凍して C:\xampp に配置し、環境変数のPATHにC:\xampp\phpを追加する。  
※PHPのバージョンが5.6〜7.4でない場合、CakePHP3のプロジェクトが作成できない。  
※今回は [xampp-portable-windows-x64-7.4.27-2-VC15.zip](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/7.4.27/xampp-portable-windows-x64-7.4.27-2-VC15.zip/download) を使用。

## ◆Composerインストール

xampp-control.exeのshellを起動して以下のコマンドを実行。  

    # php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

    # php -r "if (hash_file('sha384', 'composer-setup.php') === '906a84df04cea2aa72f40b5f787e49f22d4c2f19492ac310e8cba5b96ac8b64115ac402c8cd292b8a03482574915d1a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

    # php composer-setup.php

    # php -r "unlink('composer-setup.php');"

### ◆Composerの更新

    # php C:\xampp\composer.phar self-update

## ◆php.iniの修正
C:\xampp\php\php.ini の以下の行をコメントアウトする。  
※intlが使用不可の場合、CakePHP3でのプロジェクト作成ができない。

    ;extension=intl
    ⇓
    extension=intl

## ◆CakePHP3のプロジェクト作成
xampp-control.exeのshellを起動して以下のコマンドを実行してプロジェクトを作成する。  
※v.3系を指定しない場合、デフォルトはv.4系で構築される。

    # php C:\xampp\composer.phar create-project --prefer-dist cakephp/app:^3.8 <プロジェクト名>

## ◆サーバー起動
以下のコマンドでサーバーを起動する。

    # bin\cake server

起動後、[http://localhost:8765](http://localhost:8765/) をアクセスする。