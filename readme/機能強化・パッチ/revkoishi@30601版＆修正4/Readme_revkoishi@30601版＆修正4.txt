revkoishi作業分 for eratohoReverse# こ_L30601版＆修正4 ver.1 (14/06/07)
※『eratohoReverse# こ_L30601版』に『eratohoReverse# こ_L30601 修正4』を適用했다環境が대상となります
※안빼고インシデント対応重点


変更内容
・中出しターンより前に페니스が抜けた場合でも안빼고플래그を折れるように処理変更
・Ｗ역강간/타니와타리時に죠교자へ中出し했다際にも안빼고判定を有効に
・뽑지않고두발/뽑지않고세발が@MARK_CHECK_SOURCE_SURRENDERで正しく判定出来るように遅延判定用関数を追加


안빼고のｎ発の主な仕様変更箇所
・Ｖ⇔Ａの体位変更やコンビネーション성교봉사で明らかに페니스が抜けている場合は안빼고カウントがリセットされるようになりま했다
・안빼고遅延判定用関数追加により、뽑지않고두발/뽑지않고세발の判定タイミングが少し後に(他の大部分と同じタイミングに)なりま했다


変更箇所
------------------------------------------------------------------------------------------------------------------------
\ERB\TRAIN\ACT\
	ACT_APPLY.ERB				@ACTION_APPLY_95				Ａ→Ｖ挿し替え時にTFLAG:안빼고を折る処理を追加@v1
								@ACTION_APPLY_96				Ａ→Ｖ挿し替え時にTFLAG:안빼고を折る処理を追加@v1
								@ACTION_APPLY_97				Ａ→Ｖ挿し替え時にTFLAG:안빼고を折る処理を追加@v1
								@ACTION_APPLY_98				Ａ→Ｖ挿し替え時にTFLAG:안빼고を折る処理を追加@v1
								@ACTION_APPLY_99				Ｖ→Ａ挿し替え時にTFLAG:안빼고を折る処理を追加@v1
								@ACTION_APPLY_103				Ａ→Ｖ挿し替え時にTFLAG:안빼고を折る処理を追加@v1

\ERB\TRAIN\ASSI_ACT\
	ASSI_ACT.ERB				@ASSIACT_SELECT					Ｗ역강간/타니와타리時にTFLAG:안빼고を折る処理を追加@v1

\ERB\TRAIN\TRAINSYS\
	SOURCE_1.ERB				@CALC_SOURCE00_EX				微調整@v1
								@CALC_SOURCE00_EX_R				ちょっとだけ改造@v1
								@IS_UNEXTRACTION				新規作成。안빼고遅延判定用@v1
								@_UNEXTRACTION					新規作成。안빼고遅延判定用@v1
	SOURCE_MARK.ERB				@MARK_CHECK_SOURCE_SURRENDER	뽑지않고두발/뽑지않고세발の調整@v1
