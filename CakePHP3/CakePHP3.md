# CakePHP3のプロジェクト作成

##### 以下はWindowsで開発することを前提とした環境の構築手順です。  

## ◆使用ソフトウェア
|ソフト名|説明|
|----|----|
|XAMPP|PHP v.5.6～v.7.4のものを使用。[![alt](/img/trasition.png)](https://sourceforge.net/projects/xampp/files/)|
|Composer|PHPコマンドでダウンロード。[![alt](/img/trasition.png)](https://getcomposer.org/)|


## ◆XAMPPインストール
[こちら![alt](/img/trasition.png)](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/7.4.27/) からXAMPPのzip形式をダウンロード、解凍して C:\xampp に配置する。  
※今回は [xampp-portable-windows-x64-7.4.27-2-VC15.zip](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/7.4.27/xampp-portable-windows-x64-7.4.27-2-VC15.zip/download) を使用。

## ◆Composerインストール

xampp-control.exeを起動。  
shellを起動して以下のコマンドを実行。  

    # php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

    # php -r "if (hash_file('sha384', 'composer-setup.php') === '906a84df04cea2aa72f40b5f787e49f22d4c2f19492ac310e8cba5b96ac8b64115ac402c8cd292b8a03482574915d1a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

    # php composer-setup.php

    # php -r "unlink('composer-setup.php');"

### ◆Composerの更新

    # php C:\xampp\composer.phar self-update

## ◆php.iniの修正
C:\xampp\php\php.ini の以下の行をコメントアウトする。

    ;extension=intl
    ⇓
    extension=intl

## ◆CakePHP3のプロジェクト作成
xampp-control.exeのshellを起動して以下のコマンドを実行してプロジェクトを作成する。

    # php C:\xampp\composer.phar create-project --prefer-dist cakephp/app:^3.8 <プロジェクト名>

## ◆サーバー起動
以下のコマンドでサーバーを起動する。

    # bin\cake server

起動後、[こちら](http://localhost:8765/) をアクセスする。