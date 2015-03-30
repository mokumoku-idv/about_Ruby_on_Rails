# about_Ruby_on_Rails
Ruby on Railsについて

## Ruby on Railsとは
* オープンソースのWebアプリケーションフレームワーク  
* MVCアーキテクチャに基づいて構築されている

## 使用してみての印象
特にToolのようなもの開発を行う際にRailsを使用すると、コード量が少なく済み、工数もかなり減らすことができる

## Railsアプリケーションの作成
```
$ rails new アプリケーション名
```

## Railsフォルダ構造
```
プロジェクト名/
  - app/     アプリケーションのファイル群
　　  - controllers/  コントローラのファイル群
　　  - models/       モデルのファイル群
　　  - views/        ビューのファイル群
  - config/  設定ファイル群
  - db/      スキーマやマイグレーションのファイル群（後の章で詳しく説明します）
  - doc/     アプリケーションについてのドキュメントを配置
  - lib/     共有のコードの配置場所
  - log/     ログファイル群
  - public/  Webから直接アクセス可能なファイルを配置
  - script/  スクリプト群
  - test/    テストコードのファイル群
  - tmp/     一時ファイル群
  - vendor/　 外部のコードを配置
```

## Railsをローカルで実行
```
$ bundle install
$ rails s
```
localhost:3000でアクセス可能

## マイグレーション（migration）
* マイグレーションとは  
直接SQLを使わずに、データベースのテーブルやカラムなどの構造を変更できる仕組み  

このあたりを参考にした  
参考URL: http://railsdoc.com/migration  
参考URL: http://ruby-rails.hatenadiary.com/entry/20140810/1407634200  


## ファイル自動生成のコマンド一覧
上記マイグレーションを含め、いろいろなファイル自動生成のコマンドがある  
ここを見たほうが早い  

参考URL: http://techracho.bpsinc.jp/shibuya/2014_07_24/18388  

## Toolなどの開発に便利なscaffold
* scaffoldとは  
データベースのテーブルへの登録（CREATE）、参照（READ）、更新（UPDATE）、削除（DELETE）を行う、  
Webアプリケーションのひな形となるソースコードを自動生成する。  
scaffoldを実行させれば、最低限のCRUDを行うWebアプリケーションを作成することができる。

* scaffold作成コマンド
```
$ rails generate scaffold モデル名 フィールド名1:データ型1 ...
```
* モデル名 は**単数形**(作成されるテーブルの名前になる)  
* フィールド名：データ型 は作成されるテーブルのカラムになる。ここに書いたものが入力画面のフォームなどに使われる  
* カラムのdefault値やindexを追加したいとき、入力フォームでは必要ないけど他のカラムに必要なときなどは、  
このコマンドで作成されるmigrateファイルを直接編集する。  

参考URL: http://www.techscore.com/tech/Ruby/Rails/quick-start/Rails4/4-1/

## ページャを簡単に導入できるkaminari
下記ページを見てそのまま導入すると、簡単にページャ機能ができた  
参考URL: http://ruby-rails.hatenadiary.com/entry/20141113/1415874683

## APIの開発で使われているGrape
このあたりを参考にした  
参考URL: https://github.com/intridea/grape  
参考URL: http://dev.classmethod.jp/server-side/ruby-on-rails/ruby-on-rails_create_grape_web-api/