_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
・名称			R#ぽ0203+6用勝手に修正パッチRel3
・動作環境		eratohoReverse# ぽ0203test版+6
・作者			/L
・配布元		http://ux.getuploader.com/aba98725/
_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#

[修正内容]
EVENT_K.ERB
　　1.@KOJO_REACTにコンビネーションREACT及び派生元を呼び出す処理を追加
ACT_APLLY.ERB
　　1.@ACTION_APPLY2_5に於いてREACT分類の誤りと思われるものを修正
ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE_12に於いてRAND:2をT_COND("情欲")に変更
　　2.@TRAIN_MESSAGE_14において不要な空行と思われるものを削除
　　3.@TRAIN_MESSAGE_34に於いて、意味不明な空のPRINTFORMLを正しいと思われる形に修正
　　4.性交奉仕系@TRAIN_MESSAGEにおいて@V_SEXがTARGETを参照していたのをMASTERに修正
　　5.@TRAIN_MESSAGE_99に於いて代入されていないACT派生を参照しているのを修正
　　6.@TRAIN_MESSAGE_303に於いて脱字を修正
　　7.@TRAIN_MESSAGE2_5に於いて、下位の分岐の妨げになると思われるELSEIF ACTION_APPLY2_5V(-1) == 2をコメントアウト
　　8.修正の際に一緒に置換されてしまったと思しき空行用のPRINTFORMLをPRINTLに
　　9.コピペの際にずれたと思しきインデントを修正
SOURCE_MESSAGE.ERB
　　1.コンビネーションに派生し得る箇所のIS_NOWACTNAMEをGET_ACTNAME(GET_NORMALACTNUM(TFLAG:ACT))に
　　2.助手協力時のCFLAG:ASSI:助調方針 == 1をTCVAR:(ASSI:1):助手方針 == GET_ASSIMENUNUM("コンビネーション")に

[Rel2. 修正内容]
COMMON_GETTER_TRAIN.ERB
　　1.REACT印象関連関数群
　　　@COMIMPLIST/@GET_COMIMPNAME/@COMIMPNAME/@GET_COMIMPNUM/@COMIMPNUM/@NOWCOMIMPNAME/@IS_NOWCOMIMPNAME/@IS_COMIMPNAME
　　　以上のものを追加
ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE2_40に於いて受容となる箇所にREACT分類:受け入れを追加の上、積極的従うと並列処理
　　2.@TRAIN_MESSAGE2_45に於いて受容となる箇所にREACT分類:受け入れるを追加
ACT_APPLY.ERB
　　1.@ACTION_APPLY2_57に於いて受容となる箇所にREACT分類:消極的従うを追加
　　　拒絶となる分岐にREACT分類:拒否を追加
　　2.@ACTION_APPLY2_90に於いてIS_NOWCOMNAME("自慰し始める")の箇所のSET_COMGRO("拒否")をコメントアウト
　　3.@ACTION_APPLY_92に於いてCOM道具を外すで暴れる扱いになり得るTEQUIP解除処理を追加の上コメントアウト
　　　(本体側の判断に委ねたい意向)
COM_00.ERB
　　1.@COM1に於いて哀願となる分岐条件にIS_NOWACTNAME("罵倒")を追加
　　2.@COM7に於いてREACT派生 = 0の処理をELSE以降で行うように
COM_10.ERB
　　1.@COM11に於いてACT:逆レイプの際REACT分類:暴れるにならないように修正
COM_30.ERB
　　1.@COM32に於いてACT:逆レイプの際REACT分類:暴れるにならないように修正
　　2.@COMM33に於いてREACT派生 = 0の処理をELSE以降で行うように
COM_50.ERB
　　1.@COM50 派生:勝手にオナニーするなとなる箇所の条件にMENUMATCH(TFLAG:ACT, "奉仕")とIS_NOWACTNAME("休ませる")を追加
　　　SET_COMGRO/SET_COMIMPの処理を派生毎に切り分け。派生1はSET_COMGRO("拒否")/SET_COMIMP("悪印象大")に
　　　依存度変化処理も別途追加
REACTION_MESSAGE.ERB
　　1.CA%TSTR:2%SE 4,強気に応答するのREACT派生代入処理をコメントアウト(@COM4で代入が行われている為)
　　2.CASE 7,許しを乞うの負荷2が納得いかなかったので修正
　　3.CASE 12,下手だと罵るに於いてTFLAG:REACT印象をIS_COMIMPNAMEに
　　4.CASE 14,快感を我慢するに於いて負荷2/COMCOR_POSI()の箇所が納得いかなかったので修正
　　5.CASE 30,痛みを我慢するに於いてACT:イラマチオかつ負荷0の場合「歯を食い縛る」となるのを回避するよう修正
　　6.CASE 70,イかせてに於いてREACT派生0相当の分岐がなかったので追加

[Rel3. 修正内容]
COMMON_GETTER_CHARA.ERB
　　1.@AFFECTIONに定義"恐怖", "反抗"を追加、及び未定義でエラー落ちする際(%ARGS%)で内容を拾えるように
EVENT_DAYLY.ERB
　　1.DAILY_LIFE_NURSINGにARG:1(疲労で調教中止になった場合)を追加
　　　口上側は日常イベント@KOJO_EVENT_KX_201(ARG)に於いてIF LOCAL && ARG == 1で記述する事が可能
ROUTINE.ERB
　　1.FLAG:END達成への代入をRESULT値0以上で行うように
EVENTCOMEND.ERB
　　1.調教終了の判定の際にFLAG:日常制御をリセットするように
EVENTRAIN.ERB
　　1.大満足ボーナス関連を手入れ
　　　"%CALLNAME:TARGET%さま大満足ボーナス"の表示が目立つように変更
　　　KOJO_EVENT(16)後にPRINTLで空行が入るように
　　　CFLAG:満足ボーのリセットを今日の方針地の文の処理を抜けてから行うように
　　　上記の変更に伴い、今日の方針(アナル/お仕置き/ハード)の箇所は満足ボーの有無で地の文が変化するように
　　　今日の方針派生をTFLAG:今日の方針からPOLICY("今日")に変更
TRAIN_PROCESS.ERB
　　1.前回の行動を表示して今回の行動を決定の箇所で%TSTR:2%を%TSTR:前調教指令%
　　　%TSTR:1%を%TSTR:調教指令%にそれぞれ変更
ACT_ABLE.ERB
　　1.性奉系ACT(ACT_ABLE95~103)に於いてTEQUIP:三角木馬を規制
COMABLE.ERB
　　1.@COMABLE40に於いて逆レイプを拒否できないように
その他
　　本体付属のイベント口上番号.txtから存在していない(14,コマンド前口上)部分を削除

※これまでリリースした分はRel3に統合してあります。
　付属の各フォルダを本体のERBフォルダに上書きして使用して下さい

●連絡先
Twitter:@L7switch
mail:layer7.inc@gmail.com

(2013/06/15) /L