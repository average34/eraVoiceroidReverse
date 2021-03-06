﻿_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
・名称		口上テンプレート Preview Release4.9
・動作環境	eratohoЯeverse v1.2.14以降
・作者		/L
_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#

◎重要なお知らせ
******************************
eratohoЯeverseは全てのファイルのエンコードをUTF-8(BOM付き)に改めました
v1.010以降の本体同梱のテンプレを使用する場合は問題ありませんが
以前のものを流用している場合、それらのファイルのエンコードはS-JISになっているはずです

現行のテンプレに移すという手もありますがこれは面倒で非効率です
エンコード変換ツール(フリーのものが多く出回っています)でフォルダ毎一括変換してしまう方が良いでしょう

もし、エンコードと言われてもピンとこないという場合はS-JISのまま投げて貰えれば
こちらで取り込む際にUTF-8(BOM付)に変換して格納します

あとテキストエディタですが、ユニコード対応のものでないと問題が出る可能性があります
ユニコード対応のエディタを使用するようにして下さい
現在、殆どのエディタは対応していますし、サクラエディタもV2以降(Unicode版)なら問題ありません


◎はじめに
******************************
これはeratohoЯeverse口上テンプレート Preview Release4.9版です
現在、助手口上以外のものは揃っています(一部のファイルは暫定的な仕様)

ファイルは呼び出しタイミングと属性によって分けています
完全に個人的趣味ですが、経験上、フローの把握、各呼び出し毎の分類の把握にはこの形が良いと思っています
単体のものを切り分けるより、予め用途毎に分けてあるものを、必要に応じて統合する方がより楽なのでは
という事もあります

基本的に、埋めるだけでokという類のものを目指していません
各口上作者には、必要なものを見極める事を要求する構造になっています

分量が多目ですが、最小限何かを表示する為の手間は、実は非常に少なく
中を見えもらえれば、効率的に手を抜く手段が用意されている事に気付いて貰えると思います

まず最小限の構成と一通り作り、足りないと思う箇所にピンポイントで追加してく
そんな感じで考えてもらえればいいかと

で、記入チェックは空の分岐でもONにしない限りそこで食われる事がないので
最低限度の補完をしてやれば、一定以上の分岐を設けないと、進行状況によっては口上が表示されないといった事とは無縁です
要素を追加すればするだけ多彩な事が出来る。最小限度でもそれなりに機能する。そういったシステムになっています

ま、その辺りの説明も、正式版では漏れなくしていくつもりではあります

ACT表はもはや不要と思われたので削除しました
一覧的なものが見たい場合は調教者コマンド（ACT）はStr.csvを。調教対象のコマンド（COM）はTrain.csvを参照して下さい

CLASSIC版口上テンプレは削除しました

●その他
******************************
Preview Release4より@口上記入チェック仕様のものを"modern"として追加
これまで通りのものは"classic"として残してあります
従来のLOCALを使ったものと異なり、関数によって分岐のON/OFFを行います。単なる真偽だけでなく確率も使えます
戻り値はRETURN LOCALではなくRETURN 1のように決めうちする必要があります
現状ではこいし口上と永琳口上、拙作アリス口上、及び旧Reverseから移植された口上で使用されています

classicの場合はKX1、modernの場合はKX2をそれぞれ口上主のキャラ番号に置換して使用して下さい
フォルダ内のファイルを一括して検索、置換可能なソフトを使うとより簡単、確実です
フリーソフトでいくつか出回っているので、自分に合うものを選ぶと良いでしょう（Devasあたりはお勧め）

口上関数の置換漏れ、置換ミスはローカルではまぁ別にいいんですが、
公開した場合は色々と望ましくない事態を引き起こすこともあるので注意してください

正直、最終的な仕様については悩んでいるところなんですが、取り込み可で口上を投げてくれれば
本体に取り込んだ上で必要な修正を施し、最新のテンプレートに移植、なんて事を考えています

※更新履歴
******************************
[PR4.9, 追加と変更]
1.COM71,キスするの追加に対応
2.CLASSIC版口上テンプレの削除

[PR4.8, 追加と変更]
1.本体の仕様変更に合わせ、EVENT_OTHERS_KX1|2.ERBに方針"ご奉仕したい"を追加

[PR4.7, 追加と変更]
1.本体の仕様変更に合わせ、EVENT_OTHERS_KX1|2.ERBに方針"抱いてほしい"を追加
2.満足ボーナスの参照を@IS_SATIS_BONUSで行うように

[PR4.6, 追加と変更]
1.日常イベント口上テンプレートを追加
2.ショップイベント口上テンプレートを追加
3.ディレクトリ構造を変更。本体の構造を反映したものに
	(ERBフォルダとreadmeフォルダを本体に直接上書き可能な仕様)

[PR4.5, 追加と変更]
1.modern（口上記入チェック仕様）にEV20_絶頂口上.ERBとTRAIN_OTHERS.ERBを追加。KOJO_TRAIN_KX2フォルダ内にあります
	これは絶頂時の口上、及び状態変化口上、刻印口上等を処理するものですが、とりあえずの暫定仕様
2.modern（口上記入チェック仕様）にKOJO_SUBACT_KX2.ERBを追加。口上フォルダ直下に置いてあります
	これは脱衣口上、追加アクション口上、媚薬等使用口上を処理するものですが、これもまた暫定仕様
※classic分を作業する余裕はありませんでした…

[PR4fix3, 追加と変更]
1.CFLAG:調教回数の仕様変更に伴い、EVENT11にてKFLAGで行っていた回数カウントを粛清
	KFLAG:999で参照していた箇所をCFLAG:調教回数に変更

[PR4fix2, 追加と変更]
1.ファイル名、関数名をclassic→KX1, modern→KX2にそれぞれ変更
	非公式とも言えなくなったので[非公式]の看板を外す

[PR4fix, 追加と変更]
1.コンフィグ設定。AI自由度部分のコメントをbit毎及びbit和で書き直し
2.classic側に混じっていた口上記入チェック等を本来の仕様に沿ったものに修正
3.modern側に混じっていたLOCAL = 0等を本来の仕様に沿ったものに修正
4.REACT関連ファイルに於いてIS_NOWCOMNAMEの指定の誤りがあった箇所を修正
5.その他、細かな修正等

[PR4, 追加と変更]
1.従来のものをclassic。@口上記入チェック仕様のものをmodernとして二つのバージョンに切り分け
2.EVENT7,奴隷の首輪取得/EVENT8,調教者妊娠ファイルを追加
3.評価順の誤りを修正
4.REACTに於いて想定されるCOMを記述
5.その他、細かな修正等

[PR3, 追加と変更]
1.0616版に対応。変更されたAPPLY/ACT_MESSAGE/REACTION_MESSAGEに沿った仕様に
2.各所のコメント類を現行版に対応するように
3.フォルダ名、ファイル名を変更。今後もおそらくこの路線
	例えばACTの場合、フォルダ名→KOJO_ACT_KXX/ファイル名→ACT0_会話_KXXのように変更
4.一部、細かな修正等

[PR, 追加と変更]
1.EVENT関連ファイルを追加(調教ターン中のものは含まず)
2.「基本設定・ライセンス・ターミナル」ファイルを追加
3.一部不具合のあった箇所を修正
4.フォルダ構造の変更

●連絡先
layer7.inc@gmail.com
https://twitter.com/L7switch
(2019/04/26)/L