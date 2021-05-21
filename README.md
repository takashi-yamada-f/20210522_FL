# 技術選定の観点から見てゆく、CakePHP、Laravel、Node、goなどの勉強会

## 【１】技術選定の観点言語、フレームワークを選定する際の観点を列挙してみました。

### （１）開発面

* エンジニア調達は容易か？
* 経験の蓄積はある？なければ学習しよう。
* WEBや書籍、ユーザーコミニティから、技術的なノウハウは得やすい？
* 学習コストはかかる？自分で学習して問題を解決できる？
* 実績があり、信頼できるか？
* 将来性はある？
* ライセンス、費用は大丈夫？
* 開発環境の用意、実装、コンパイル、テスト、デプロイのコストは適正？

### （２）運用面

* 障害対応できる？
* セキュリティバージョンアップは必要な期間、提供されて行くのか？
* 日常の運用コストは適正？

### （３）機能要件の充足

* 必要な機能、ライブラリはあるか？
* フルスタックであれば、ライブラリが充実しているか？開発は盛んか？

### （４）速度要件の充足

* 求める速度を充すか？

## 色々見ていく前に、前提知識として

マイクロサービス (microservices) とは - 概要 | Red Hat<br>
https://www.redhat.com/ja/topics/microservices

フルスタックフレームワークから脱却してマイクロサービスライクにサービスを構築する<br>
https://qiita.com/tooooooooomy/items/a62eee60b2b2a6bd4251<br>
メリット、デメリットの部分を見てください。おすすめのライブラリ部分はこの人の私見程度で。

## 【２】有名なベンチマークサイトから、どんな言語、フレームワークがあるのか？見ていってみましょう。

https://www.techempower.com/benchmarks/#section=data-r17&hw=ph&test=query&d=1l

* 一般論として、コンパイル言語は速く、同じ言語でもマイクロサービスフレームワークは軽量で機能が限定される代わりに速く、フルスタックフレームワークは遅いです。
* 一位のactixはRustのマイクロサービスフレームワークです。RustはC言語に変わることを目指すコンパイル言語です。
* vertex、servlet-mysqlはJavaのフレームワークです。Javaのフルスタックフレームワークといえばspring。137位。
* http4kはkotlinのマイクロサービスフレームワークです。5位って本当？Javaエンジニアは押さえておいた方がよい言語かと思います。
* aspcoreは、asp.NET core MVCのことで、C#のフレームワークです。
* gin、fasthttp、echoはGo言語のフレームワークです。
* nodejsは102位と高速です。expressでmysqlを使った場合は153位になっています。

サーバサイド最多の言語PHPのフレームワークは、
* 上位にswoole、slim、yii2、phalconと言ったフレームワークが入っています。swooleは高速ですが日本語情報が少ないです。yiiは旧共産圏で利用が多いsymphony系フレームワークです。
* phalconは高速なフルスタックフレームワークですがCのエクステンションの為、インストールが必要になります。slimは軽量フレームワークです。
* zend、cakephp、laravel、fuelと言ったフルスタックフレームワークは、200位に行かないあたりで固まっています。

* rubyのrailsは184位。pythonのdjangoは202位。スクリプト言語のフルスタックフレームワークは速度は似た通ったかですね。

## 【３】先ずは実証実験してみよう。

PoC<br>
https://www.ntt.com/bizon/glossary/e-p/poc.html

## Go言語
速いです。普通のスクリプト言語と勝手が違い、失敗するプロジェクトもあるので、よく理解して導入する必要があります。

Go言語(golang)とは？人気が高まっている理由を言語の特徴を踏まえて解説！<br>
https://udemy.benesse.co.jp/development/system/golang.html

他言語プログラマがgolangの基本を押さえる為のまとめ - Qiita<br>
https://qiita.com/tfrcm/items/e2a3d7ce7ab8868e37f7

Golang on DockerでEchoを動かす - Qiita<br>
https://qiita.com/kiyc/items/fc65d999f86d4d59354c

Golang Echoでのテスト駆動のAPI開発 - Qiita<br>
https://qiita.com/kiyc/items/c20ac7bb6997c0753314

PHPからgoへの移行で分かったこと - SlideShare<br>
https://www.slideshare.net/greetech/phpgo-200234954

## Node.js
サーバーサイドJS。WebSocket通信機能が使える他、実行速度が高速という特徴もあります。


Node.js + Expressで超簡単API - Qiita<br>
https://qiita.com/k-penguin-sato/items/5d0db0116843396946bd

今話題のチャットボットを作ってみた ～スマホ・PC同時 ...- Qiita<br>
https://qiita.com/riversun/items/279c1dd5ab40a1c8c8cf

【Node.js入門】FirebaseにNode.jsプロジェクトをホスティングする方法！<br>
https://www.sejuku.net/blog/86468

GraphQLをNode.jsとexpressでためしてみる<br>
https://dev.classmethod.jp/articles/graphql-tutorial-nodejsexpress/


## PHP CakePHP
バージョン２台はかつての主流でした。運用案件は未だに多いです。

CakePHP 4.x Strawberry Cookbook 日本語マニュアル<br>
https://book.cakephp.org/4/ja/index.html

CakePHP 4 の Bake コマンド の基本的な使い方<br>
https://tt-computing.com/cake4-bake-basic#preparation

クエリービルダー<br>
https://book.cakephp.org/4/ja/orm/query-builder.html


## PHP Laravel
スクリプト言語のフルスタックフレームワーク代表。

Laravel<br>
https://readouble.com/laravel/

Laravel入門 - 使い方チュートリアル - - Qiita<br>
https://qiita.com/sano1202/items/6021856b70e4f8d3dc3d

Laradockでの環境構築方法２パターンを細かめに説明<br>
https://qiita.com/wajima/items/69fad6c2b42c52928e

Laravelで認証処理を作ってみる - Qiita<br>
https://qiita.com/apricotcomic/items/d7407d4b12f41e2ff5ed

【Laravel】ユーザ登録時にメール認証する(v5.7以上) - Qiita<br>
https://qiita.com/nekyo/items/03e50b4d0dd6f09287d6

Laravel CRUDを実装する - 思考の葉<br>
https://noumenon-th.net/programming/2020/01/30/laravel-crud/

LaravelベースのCMS OctoberCMS入門 - Qiita<br>
https://qiita.com/pikanji/items/ac05bbfbab955bf7fc5b<br>
日本語の情報が少なく、導入しづらい典型。勧めません。

Laravel Mixでフロントエンド開発環境を手軽に構築 2020年版 ...<br>
https://tech.arms-soft.co.jp/entry/2020/04/01/090000
