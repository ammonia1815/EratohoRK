revkoishi作業分 for eratohoReverse# こ_L30601版＆修正1 ver.1 (14/06/01)
※『eratohoReverse# こ_L30601版』に『eratohoReverse# こ_L30601 修正1』を適用했다環境が대상となります
※前任者のインシデント対応重点な。前任者はセプクしま했다のでごあんしんください


変更内容
・죠교대상が여자の場合、ステータス画面で【엉덩이に삽입시켰다】が表示されない問題を修正　※페니스밴드使用で취득可能
・【엉덩이に삽입시켰다】の취득時の文言が正しく表示されず【】になる問題を修正　※『,』が入ってた
・STRNAME:1305とSTRNAME:1306が逆になっていたので修正　※세이브データには영향ないはず…
・コメントの誤りを修正。その他微調整


変更箇所
------------------------------------------------------------------------------------------------------------------------
\CSV\
    Str.csv                     1305,1A___엉덩이を~         コメントの誤りを修正(쾌Ｂ→쾌Ａ)
                                1306,1A___가슴を~             コメントの誤りを修正(쾌Ａ→쾌Ｂ)
                                1347,3P___엉덩이に~         여자の場合にステータス画面で表示されない問題を修正。취득時文言が表示されない問題を修正
    Strname.csv                 1305,쾌Ｂ                   쾌Ｂ→쾌Ａに修正
                                1306,쾌Ａ                   쾌Ａ→쾌Ｂに修正
                                                            ※この2箇所は文字列による参照をしていないため세이브データに영향ありません。ごあんしんください

\ERB\FUNCTION\GETTER\
    COMMON_GETTER_SURRENDER.ERB @IS_SURRENDER_DISPLAYABLE   他の判定にも使えるように名称を@IS_SURRENDER_ENABLEに変更

\ERB\SYSTEM\SHOP\
    SHOP_TRAINERDATA.ERB        @PRINT_STATUS2              @IS_SURRENDER_DISPLAYABLEの関数名変更に伴う修正

\ERB\TRAIN\TRAINSYS\
    SOURCE_MARK.ERB             @MARK_CHECK_GET             念の為@IS_SURRENDER_ENABLEで有効判定を行うように変更
