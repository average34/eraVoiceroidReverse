_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
・名称		R#ぽ0616test版++用勝手に修正パッチRel3
・動作環境	eratohoReverse# ぽ0616test版++
・作者		/L
・配布元	http://ux.getuploader.com/aba98725/
_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#

[修正内容]
　□CSV
　　1.CFLAG:1230,奴隷の首輪封印を追加
　　2.Str.csv, 0~103までをACT分類毎に区切るように
　　3.Train.csv, 0~70までを分類毎に区切るように
　　4.Tequip.csv, 88,着衣露出 100,調教対象Ｃ使用にコメントを追加
　　5.Tcvar.csv, 40,状態変化のコメントを現行仕様に合うように
　□ACT_ABLE.ERB
　　1.@ACT_ABLE11胸愛撫に於いてTEQUIP:性交奉仕中, 2, 5, 6の際は規制するように
　□ACT_APPLY.ERB
　　1.@ACTION_APPLY2_57に於いてREACT分類"拒否", "暴れる", "逃げる"の箇所を修正
　　　COM自慰し始めるとACT派生で切り分け、汚れ処理も切り分けるように
　□ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE2_11に於いてTFLAG:ACT派生 == 3のみで受容扱いの箇所に!IS_COMGRONAME("暴れる")を追加
　　2.@TRAIN_MESSAGE2_27に押し倒し終了の分岐を追加
　　3.@TRAIN_MESSAGE2_42のIS_COMGRONAME("積極的従う")をIS_COMGRONAME("受け入れる/積極的従う")に
　　4.@TRAIN_MESSAGE2 奉仕系の拒絶となる箇所にIS_NOWCOMNAME("自慰し始める")を追加
　　5.@TRAIN_MESSAGE_51にACT派生1,フェラ強制を追加
　□SOURCE_MESSAGE.ERB
　　1.調教対象絶頂及び調教対象射精の際、NOWEX:MASTER:放尿を弾くように
　　2.下層にNOWEX:MASTER:放尿を処理する箇所を追加
　□COM_XX.ERB
　　1.@COM7に於いてREACT1をCOM印象"0から遠ざかる"に
　　2.@COM21に於いてREACT派生を定義し、Ｖ/Ａ性交をそれぞれREACT派生で参照できるように
　　3.@COM30でREACT派生を定義。REACTION_MESSAGEに倣い、快SOURCEで派生0と1に分ける
　　4.@COM33を@COM7と同様に修正。派生1の「意見を出すなんていい度胸だね！」は納得できる形に
　　5.@COM52内のTFLAG:ACTをIS_NOWACTNAMEに。自慰系はGETBITで見るようにそれぞれ変更
　□COMABLE.ERB
　　1.@COMABLE21及び@COMABLE22に於いてTALENT:MASTER:オトコである場合の規制を解除
　　2.@COMABLE50に於いてACT15,キス時に発生するのは違和感があったので規制
　□REACTION_MESSAGE.ERB
　　1.COM0にアイマスク装着時の分岐を追加
　　2.COM7に「意見を出すなんていい度胸だね！」の場合の処理を追加
　　3.COM22,負荷2の箇所をV_SEX(TARGET)で分けるように
　　4.COM32に負荷2の処理を追加
　　5.COM33に「怯えに対し苛立つ」の処理を追加
　　6.COM41に「消極的なのが気に入らない」の処理を追加
　□EVENT_S.ERB
　　1.@EVENTTURNEND, 奴隷の首輪イベントを口上側で封印可能なように
　　　任意の箇所でCFLAG:奴隷の首輪封印 = 1することで封印が可能
　□COMMON_GETTER_TRAIN.ERB
　　1.@ACTSTRに於いてその他の処理になる際、ACT名称を返すように

[Rel2, 修正内容]
　□SOURCE.ERB
　　1.KOJO_EVENT(20)呼び出し箇所のMASTER_EX及びTARGET_EXのビット和での指定を廃し省略するように
　　2.上記箇所の前にFLAG:地の文制御をリセットするように

[Rel3, 修正内容]
　□CSV
　　1.Tcvar.csv 60,満足ボーナス/61,今回で大満足/62,今日の満足ボーナスを追加
　□EVETRAIN.ERB
　　1.満足ボーナスのRESULT参照箇所を拡張の上、TCVAR:今日の満足ボーナスへの代入処理を追加し調教中に参照可能なように
　　　当該フラグは39行目で-1にリセット
　□EVENTCOMEND.ERB
　　1.大満足ボーナスの箇所、723行目にTCVAR:今回で大満足への代入処理を追加。現状、他の箇所での参照には用いていない
　□ACT_ABLE.ERB
　　1.@ACT_ABLE35に於いてTEQUIP:ペニスバンド、TEQUIP:バイブによる規制を解除
　　　TEQUIP:アナルバイブ、TEQUIP:アナルビーズ、TEQUIP:浣腸器＋プラグの際は規制するように
　□ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE_25, "クリップローターを貼り付けようとした"→"クリップローターを取り付けようとした"に変更
　　2.@TRAIN_MESSAGE2_35, IS_COMGRONAME("消極的従う")の箇所に於いて、"嫌がった", "悲鳴をあげる"をCOMで切り分け
　　　より納得のできる形に変更
　　3.@TRAIN_MESSAGE2_41, IS_COMGRONAME("許しを乞う")の箇所を書き直し
　□REACTION_MESSAGE.ERB
　　1.派生をTRAINNAME:SELECTCOMで記述するように変更
　　2.COM7,許しを乞うに於いて、負荷2の箇所を一部修正
　　3.COM8,気持ち良くしてにTFLAG:REACT派生 == 1の処理を追加

※Emuera1818+v7も付けてあります。今回は必須という訳ではありませんが、なるべく新しいものが望ましいです

※付属の各フォルダを本体のERB、CSVフォルダに上書きして使用して下さい
　現状あくまでも非公式であることをご理解の上、導入してください
　また、当パッチを導入した事による不具合のサポートを、システム側に求めないようお願いします

●連絡先
Twitter:@L7switch
mail:layer7.inc@gmail.com
(2014/03/26) /L