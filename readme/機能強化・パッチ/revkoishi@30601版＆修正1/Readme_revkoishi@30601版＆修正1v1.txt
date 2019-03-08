revkoishi作業分 for eratohoReverse# こ_L30601版＆修正1 ver.1 (14/06/01)
※『eratohoReverse# こ_L30601版』に『eratohoReverse# こ_L30601 修正1』を適用した環境が対象となります
※前任者のインシデント対応重点な。前任者はセプクしましたのでごあんしんください


変更内容
・調教対象が女の子の場合、ステータス画面で【アヌスに挿入させた】が表示されない問題を修正　※ペニスバンド使用で取得可能
・【アヌスに挿入させた】の取得時の文言が正しく表示されず【】になる問題を修正　※『,』が入ってた
・STRNAME:1305とSTRNAME:1306が逆になっていたので修正　※セーブデータには影響ないはず…
・コメントの誤りを修正。その他微調整


変更箇所
------------------------------------------------------------------------------------------------------------------------
\CSV\
    Str.csv                     1305,1A___アヌスを~         コメントの誤りを修正(快Ｂ→快Ａ)
                                1306,1A___胸を~             コメントの誤りを修正(快Ａ→快Ｂ)
                                1347,3P___アヌスに~         女の子の場合にステータス画面で表示されない問題を修正。取得時文言が表示されない問題を修正
    Strname.csv                 1305,快Ｂ                   快Ｂ→快Ａに修正
                                1306,快Ａ                   快Ａ→快Ｂに修正
                                                            ※この2箇所は文字列による参照をしていないためセーブデータに影響ありません。ごあんしんください

\ERB\FUNCTION\GETTER\
    COMMON_GETTER_SURRENDER.ERB @IS_SURRENDER_DISPLAYABLE   他の判定にも使えるように名称を@IS_SURRENDER_ENABLEに変更

\ERB\SYSTEM\SHOP\
    SHOP_TRAINERDATA.ERB        @PRINT_STATUS2              @IS_SURRENDER_DISPLAYABLEの関数名変更に伴う修正

\ERB\TRAIN\TRAINSYS\
    SOURCE_MARK.ERB             @MARK_CHECK_GET             念の為@IS_SURRENDER_ENABLEで有効判定を行うように変更
