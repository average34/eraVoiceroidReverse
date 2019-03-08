revkoishi作業分 for eratohoReverse# こ_L30601版＆修正4 ver.1 (14/06/07)
※『eratohoReverse# こ_L30601版』に『eratohoReverse# こ_L30601 修正4』を適用した環境が対象となります
※抜かずインシデント対応重点


変更内容
・中出しターンより前にペニスが抜けた場合でも抜かずフラグを折れるように処理変更
・Ｗ逆レイプ/谷渡り時に調教者へ中出しした際にも抜かず判定を有効に
・抜かずの二発/抜かずの三発が@MARK_CHECK_SOURCE_SURRENDERで正しく判定出来るように遅延判定用関数を追加


抜かずのｎ発の主な仕様変更箇所
・Ｖ⇔Ａの体位変更やコンビネーション性交奉仕で明らかにペニスが抜けている場合は抜かずカウントがリセットされるようになりました
・抜かず遅延判定用関数追加により、抜かずの二発/抜かずの三発の判定タイミングが少し後に(他の大部分と同じタイミングに)なりました


変更箇所
------------------------------------------------------------------------------------------------------------------------
\ERB\TRAIN\ACT\
	ACT_APPLY.ERB				@ACTION_APPLY_95				Ａ→Ｖ挿し替え時にTFLAG:抜かずを折る処理を追加@v1
								@ACTION_APPLY_96				Ａ→Ｖ挿し替え時にTFLAG:抜かずを折る処理を追加@v1
								@ACTION_APPLY_97				Ａ→Ｖ挿し替え時にTFLAG:抜かずを折る処理を追加@v1
								@ACTION_APPLY_98				Ａ→Ｖ挿し替え時にTFLAG:抜かずを折る処理を追加@v1
								@ACTION_APPLY_99				Ｖ→Ａ挿し替え時にTFLAG:抜かずを折る処理を追加@v1
								@ACTION_APPLY_103				Ａ→Ｖ挿し替え時にTFLAG:抜かずを折る処理を追加@v1

\ERB\TRAIN\ASSI_ACT\
	ASSI_ACT.ERB				@ASSIACT_SELECT					Ｗ逆レイプ/谷渡り時にTFLAG:抜かずを折る処理を追加@v1

\ERB\TRAIN\TRAINSYS\
	SOURCE_1.ERB				@CALC_SOURCE00_EX				微調整@v1
								@CALC_SOURCE00_EX_R				ちょっとだけ改造@v1
								@IS_UNEXTRACTION				新規作成。抜かず遅延判定用@v1
								@_UNEXTRACTION					新規作成。抜かず遅延判定用@v1
	SOURCE_MARK.ERB				@MARK_CHECK_SOURCE_SURRENDER	抜かずの二発/抜かずの三発の調整@v1
