# Controlled Vocabulary Designer (CVD)
CVDは、統制語彙の作成を視覚的なインターフェースでサポートするツールです。<br>
自然言語処理の計算結果や既存の統制語彙を参照して、同義関係や上下関係を効率的に定義できます。
さらに、アプリケーションウィンドウで語彙全体を確認しながら直感的に編集することができます。
作成された統制語彙は、RDFファイルとして出力・保存できます。<br>
CVDのヘルプページは[こちら](https://fujitsu.github.io/controlled-vocabulary-designer/)

# システム要件
- docker : バージョン19.03以上
- docker-compose : バージョン1.23以上

# セットアップ方法
1. ```docker-compose up -d```
2. 作業環境のWEBブラウザで以下にアクセスします。

```
http://(hostname):10081/
```

# サポートブラウザ
* Google Chrome
* Microsoft Edge
* Firefox

# サポートファイル形式
* 読み込み用ファイル形式
  * 編集用語彙_meta（語彙のメタファイル） : .csv
  * 編集用語彙（語彙を編集するファイル） : .csv
  * 参照用語彙（既存の語彙ファイル） : .csv

* 書き出し用ファイル形式
  * 編集用語彙（語彙を編集したファイル） : .csv
  * 統制語彙（語彙を編集したファイル） : .n3, .nquads, .nt, .trix, .turtle, .xml, .jsonld


## 編集用語彙_metaのサンプル

```
語彙の名称,語彙の英語名称,バージョン,接頭語,語彙のURI,語彙の説明,語彙の英語説明,語彙の作成者
サンプル語彙,sample vocabulary,1.0.0,my,http://myVocabulary/,サンプル用の語彙です,The vocabulary for sample,サンプル太郎
```

## 編集用語彙のサンプル

```
用語名,代表語,言語,代表語のURI,上位語のURI,他語彙体系の同義語のURI,用語の説明,作成日,最終更新日,同義語候補,上位語候補,x座標値,y座標値,色1,色2,確定済み用語
コンビニ,コンビニエンスストア,ja,http://myVocabulary/1,http://myVocabulary/2,,コンビニエンスストアの略称です,2021-04-02T12:43:02Z,2021-04-08T16:07:59Z,"常駐警備, 警備員, 機械警備, ビルメンテナンス, 運送会社, 運転代行, 貴重品輸送警備, ホームセキュリティ, ガーディアンエンジェルス, 警備保障",,3.779367076,-44.97713738,black,black,0
コンビニエンスストア,コンビニエンスストア,ja,http://myVocabulary/1,http://myVocabulary/2,,コンビニエンスストアの略称です,2021-04-02T12:43:02Z,2021-04-08T16:07:59Z,"子育て支援センター, 介護予防, 生涯学習, 高齢者福祉, 母子生活支援施設, 育児支援, 社会的養護, 地域包括支援センター, 海士町中央図書館, 福祉",,16.81118132,-61.70717408,black,black,0
convenience store,convenience store,en,http://myVocabulary/1,http://myVocabulary/2,,Alias of convenience store,2021-04-02T12:43:02Z,2021-04-08T16:07:59Z,"郵便物, 速達郵便, 郵便局, 小包, 郵便事業, 配達, 国際郵便, 郵便サービス, 航空郵便, 集配人","デリバリー, デリヴァリー, 持参, 送達, 配信, 配送, 配達, コミュニケイション, 伝達, 通信, メッセイジ, ドキュメント, 一札, 文書, 方策, ご書, 書, 書きもの, 書付, 書付け, 書契, 書札, 書案, 書き物, 記, 記文, テキス, テキスト, 原文, 文, 文章, 本文, 正文, 正本, コレクション, 収集物, 固まり, 群, 蓄積, 集まり, 集合体, 集合物, 集団, 集積物",-7.53980653,-51.30562908,black,black,0
drug store,convenience store,en,http://myVocabulary/1,http://myVocabulary/2,,Alias of convenience store,2021-04-02T12:43:02Z,2021-04-08T16:07:59Z,"空き家問題, 空家, 廃屋, 民家, 空き室, アパート, 米軍ハウス, 公営団地, 住宅, 家賃滞納",,-7.911179493,-26.26668782,black,black,0
the corner shop,convenience store,en,http://myVocabulary/1,http://myVocabulary/2,,Alias of convenience store,2021-04-02T12:43:02Z,2021-04-08T16:07:59Z,"アムラックス, 銀座三越, モデルルーム, 日産ギャラリー, イセタン, コワーキングスペース, カリモク家具, 自社ビル, ポーゲンポール, 蔦屋家電",,-43.68659491,42.18700014,black,black,0
店舗,店舗,ja,http://myVocabulary/2,,http://otherVocabulary/16,,2021-04-01T11:40:15Z,2021-04-09T09:22:11Z,"リテラシー, 金融, 人材マネジメント, リテラシ, esg投資, コーポレートファイナンス, アントレプレナーシップ, ソーシャルマーケティング, ニューノーマル, 労働経済学",,7.237030405,-51.76710593,black,black,0
店,店舗,ja,http://myVocabulary/2,,http://otherVocabulary/16,,2021-04-01T11:40:15Z,2021-04-09T09:22:11Z,"賃貸, 不動産投資, 不動産業, 不動産仲介, 不動産会社, 信託受益権, 不動産開発, 中古マンション, サブリース, プロパティマネジメント","プロパティ, プロパティー, 保有物, 所有, 所有地, 所有物, 持物, 有形の所有物, 財産, 資産, 身代",-47.93248755,34.79784645,black,black,0
store,store,en,http://myVocabulary/2,,http://otherVocabulary/16,,2021-04-01T11:40:15Z,2021-04-09T09:22:11Z,"生体認識, 生体情報, 生体物質, 細胞, 生体材料, 分子レベル, 遺伝子改変動物, 体内, 細胞分化, 人体","生き物, 有機体, 生体, 生活体, 生物, 生き物, バディ, ししむら, 五体, 体, 体躯, 図体, 御身, 肉体, 肉叢, 肉塊, 肉身, 足手, 身, 身体, 身躯, 身骨, 躯体, 骨身",9.110486157,-80.63532085,black,black,0
shop,store,en,http://myVocabulary/2,,http://otherVocabulary/16,,2021-04-01T11:40:15Z,2021-04-09T09:22:11Z,"プラットフォーム, web, モバイルアプリケーション, ウェブ, yammer, アプリケーション, opensocial, クラウドプラットフォーム, ホスティングサービス, typepad",,32.98654788,33.62595116,black,black,0
```

## 参照用語彙のサンプル

```
用語名,代表語,言語,代表語のURI,上位語のURI,他語彙体系の同義語のURI,用語の説明,作成日,最終更新日,x座標値,y座標値
カイトウメン,カイトウメン,ja,http://cavoc.org/cvo/ns/3/C822,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,3.779367076,-44.97713738
Gossypium barbadense,カイトウメン,en,http://cavoc.org/cvo/ns/3/C822,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,16.81118132,-61.70717408
ペルー綿,カイトウメン,ja,http://cavoc.org/cvo/ns/3/C822,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,-7.53980653,-51.30562908
シーアイランド綿,カイトウメン,ja,http://cavoc.org/cvo/ns/3/C822,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,-7.911179493,-26.26668782
エジプト綿,カイトウメン,ja,http://cavoc.org/cvo/ns/3/C822,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,-43.68659491,42.18700014
スーダン綿,カイトウメン,ja,http://cavoc.org/cvo/ns/3/C822,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,7.237030405,-51.76710593
ワタ,ワタ,ja,http://cavoc.org/cvo/ns/3/C876,,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,-47.93248755,34.79784645
モメン,ワタ,ja,http://cavoc.org/cvo/ns/3/C876,,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,9.110486157,-80.63532085
Cotton,Cotton,en,http://cavoc.org/cvo/ns/3/C876,,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,63.98654788,-13.62595116
Gossypium arboreum,Cotton,en,http://cavoc.org/cvo/ns/3/C876,,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,84.94554788,-65.64325116
Gossypium herbaceum,Cotton,en,http://cavoc.org/cvo/ns/3/C876,,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,22.86783788,-30.67687116
Gossypium hirsutum,Cotton,en,http://cavoc.org/cvo/ns/3/C876,,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,-52.98788,-42.625
食用綿実,食用綿実,ja,http://cavoc.org/cvo/ns/3/C1055,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,91.99742788,-43.65986116
Edible cotton,Edible cotton,en,http://cavoc.org/cvo/ns/3/C1055,http://cavoc.org/cvo/ns/3/C876,,,2017-10-02T12:02:48Z,2021-07-14T12:43:45Z,56.98865788,-77.97631116
```

## 読み込み用ファイルの作成方法
読み込み用ファイルの作成方法は[こちら](example-inputdata-creation/README.md)を参照ください。


# URIプレフィックス
「Config.js」を使用して、URIプレフィックスの略語を設定することができます。入力したURIに、設定したURIプレフィックスが含まれている場合、対応する略語に自動的に変換されアプリケーションウィンドウ上で確認することができます。また、設定した略語をアプリケーションウィンドウ上で入力することもできます。いずれの場合も「Config.js」で設定したURIプレフィックスとして認識され、データベースに保存されます。


## Config.jsのURIプレフィックスの略語の設定の例
URIプレフィックスである"origin"のバリューは"equiv"のバリューに変換されます。<br>
以下のサンプルでは、`'http://cavoc.org/'`は`'cavoc:'`に、`'http://example.org/'`は`'ex:'`に変換されます。

```
'prefix': [
  {
    'origin': 'http://cavoc.org/',
    'equiv': 'cavoc:',
  },
  {
    'origin': 'http://example.org/',
    'equiv': 'ex:',
  },
],

```


# 用語の座標値のスケール倍率
編集用語彙の用語の座標値と参照用語彙の用語の座標値のスケールに大きな違いがある場合は、「Config.js」を編集することで参照用語彙の用語の座標値のスケール倍率を調整することができます。

## Config.jsの用語の座標値のスケール倍率の設定の例
参照用語彙の用語の座標値のスケールのデフォルトの倍率は「1」です。正の数と負の数ともに設定することができます。

```
'magnification': [
  {
    'reference': 1,
  },
],

```

# 削除方法
1. ```docker-compose down```
2. ```docker volume rm controlled-vocabulary-designer-db-data```

<div align="right">
    <img src="https://img.shields.io/badge/nginx-1.19.3-color.svg?style=plastic&logo=nginx">
    <img src="https://img.shields.io/badge/npm-lts-red.svg?style=plastic&logo=npm">
    <img src="https://img.shields.io/badge/python-3-blue.svg?style=plastic&logo=python">
    <img src="https://img.shields.io/badge/postgreSQL-12.4-white.svg?style=plastic&logo=postgreSQL">
    <br>
    <img src="https://img.shields.io/badge/react--blue.svg?style=plastic&logo=react">
    <img src="https://img.shields.io/badge/MaterialUI--white.svg?style=plastic&logo=Material-UI">
    <img src="https://img.shields.io/badge/Webpack--blue.svg?style=plastic&logo=Webpack">
    <img src="https://img.shields.io/badge/Flask--white.svg?style=plastic&logo=Flask">
</div>

# 謝辞
本研究テーマは、内閣府総合科学技術・イノベーション会議「戦略的イノベーション創造プログラム（SIP）ビッグデータ・AI を活用したサイバー空間基盤技術」（NEDO）の支援のもと遂行されました。

# 連絡先
contact-cvd@cs.jp.fujitsu.com
