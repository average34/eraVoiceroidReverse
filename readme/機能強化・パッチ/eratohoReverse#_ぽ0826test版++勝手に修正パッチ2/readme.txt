2012/10/1

以下の不具合を修正

・SANDBOX、EXTRAモード開始時に調教対象の体力気力理性の最大値がおかしくなることがある
・押し倒し中に調教対象が絶頂しても解放されない
・調教で得られる魔力が想定よりも少ない

2012/9/26

自前修正が溜まってきたのでうｐ
以下の不具合を修正

・潤滑、鬱屈が上がらない
・顔面騎乗しているのに調教者が調教対象の背後にいるような文が表示される
・助手１の行動が助手２の行動として表示されることがある
・素質「長身」を持っていても表示されない


具体的な変更箇所

COMMON_GETTER_CHARA.ERB
・長身のカテゴリを非表示から体質に移動

TRAIN_PROCESS.ERB
・助手のACT処理後にASSI = ASSI:1を追加

MASTER_POSE.ERB
・顔面騎乗、押し倒しによる強制仰向けの処理で
　TCVAR:MASTER:位置前後 = TEQUIP:押し倒し中 || IS_NOWACTNAME("押し倒す") ? 1 # 0
　↓
　TCVAR:MASTER:位置前後 = 1

SOURCE.ERB
SOURCE_1.ERB
・SUMARRAYが入力値を無視して常に0を返してくる所を単純加算に置き換え

MASTERCUSTOM.ERB
・BASE_MASTER_SETUPの処理を複雑化
