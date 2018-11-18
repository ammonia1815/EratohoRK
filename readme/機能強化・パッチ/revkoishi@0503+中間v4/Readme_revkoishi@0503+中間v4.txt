revkoishi作業分 for eratohoReverse# こ_L0503+中間 ver.4 (14/05/28)
※R#こ_L0503+中間.7z からの差分になります。変更箇所のv3+v4は含みますがv1,v2は含みません
※v2までの変更点は下部に記載했다ところ実際長いと評判だったので決断的にマージしま했다。実際見やすいがあまり短くなっていない気もする
※R#のユーザインタフェースの文句は私に言え(震え声)　か、書けって脅당했다んです…書かないと正体をバラバラにするって…(レイプ目)
※私ね、これが終わったら、またしばらく放浪하면서구상書こうと思うんだ…(謎)


お詫びと訂正
・revkoishi@0503test版v2にて각인ポイント表示の計算が正しく行われていなかった問題を修正しま했다。
　なお、担当者は自主的にケジメしま했다ので、囲んで棒で叩きま했다。ごあんしんください
・revkoishi@0503test版v2にて독심능력が変更可能だった不具合が正しく修正されていなかったので修正しま했다。
　なお、担当者はアバシリへ研修に送られま했다のでごあんしんください
・revkoishi@0503+中間v3にてTRAIN_PROCESS.ERBの変更履歴の更新漏れというインシデントが発生しま했다ので修正しま했다。
　なお、担当者は許してくださいお願いします何でもしますからと言いま했다ので、ケジメしま했다。ごあんしんください
・revkoishi@0503+中間v3にて@GET_SURRENDER_NUMの戻り値仕様の記載ミスというインシデントが発生しま했다ので修正しま했다。
　なお、担当者はカロウシのためケジメはありません。ごあんしんください


変更内容
・@ASSISWAPで、不필요なMASTER-ASSI間のSWAPが行われてPALAM等のデータが破壊される不具合を修正
・@CONFIG_ANIMATION_EFFECTを呼ぶとREDRAWの値が強制的に0に書き換わる場合があるのを修正
・@CONFIGUREで直接値を打ち込むと状況に関わらず독심능력が変更可能だった不具合を修正
・@CONFIG_PADでEnterキーを新たに割り当てる事が出来なかった不具合を修正
・一部環境でフェード処理がうまくいかなかったようなので対策
・ステータス表示画面と마력使用画面、コンフィグ画面をガリガリと改悪。主に表示項目と色と拡張性(表示関連の不備修正含む)
・굴복実績関連の決断的大規模손入れ。질내사정Ｖ절정を【굴복:60】として復活。他2種追加
・시오후키関連の仕様追加(補完)。EX:MASTER:시오후키 が機能するように、EXP:시오후키경험 の追加、【굴복:59】시오후키 の追加
・画面に表示されるｃ/ｖ/ｂ/ａは大文字に修正
・汎用関数をいくつか追加
・その他微調整


ステータス画面の主な仕様
・無駄にボタン化されていた箇所をボタン化しないようにしま했다。安心です
・아라이멘도の色を調整しま했다ので、ごあんしんください
・能力、경험のうち0のものはグレー表示にしま했다。安心です
・分類カラー表示と죠교履歴の改行位置自動判別に対応しま했다。ごあんしんください


마력仕様画面の主な仕様
・죠교도구分類表示の上に、カスタマイズ後名称変更＆虹色表示します。ごあんしんください
・素質変動カラー表示で改行位置自動判別。多い日も安心です


コンフィグ画面の主な仕様
・ON/OFFの集合画面は基本的にチェックボックスを表示。わかりやすさ重点により安心です


굴복実績の主な仕様
・Str.csvでLvと대상性別と表示文言2種を一括定義可能。
　文言見直しの際にgrep結果とにらめっこする필요は無くなりま했다のでごあんしんください。Lv変更も容易で安心です
　(既存の세이브データは再計算しないと齟齬が発生しますが対応も容易ですのでごあんしんください)
・ステータス画面では定義されている分だけLv毎に번호順に表示します。
　Str.csvでLv順に定義する필요はありませんのでごあんしんください。改行位置も自動判定。安心です
・CSTR:구상독자실적Xで、구상独自の実績を定義可能ヤッター！最大16枠使えますのでごあんしんください。
　判定は@KOJO_CHECK_SURRENDER_KX1内か、구상内の任意の位置で@MARK_CHECK_GETが使えます。安心です
・本体の굴복実績が64種→112種まで増やせるようになりま했다。安心です
・新規実績は시오후키、질내사정Ｖ절정、사중절정、젖음の4種です。여자も후타나리の子もごあんしんください


変更箇所
------------------------------------------------------------------------------------------------------------------------
\CSV\
    Cflag.csv                   302,각인2                       新規追加@v3
    Cstr.csv                    70-85                           新規追加@v3
    Exp.csv                     14,시오후키경험                   新規追加@v3
    Str.csv                     1300-1427                       굴복実績の仕様変更と新規追加@v4
                                                                ※文言案は/L＝サンから頂きま했다。ありがとうございます
    Strname.csv                 1300-1427                       新規追加@v4

\ERB\FUNCTION\GETTER\
    COMMON_GETTER_CHARA.ERB     @ABL_TYPE                       新規作成@v3
                                @EXP_TYPE                       新規作成@v3
                                @TALENT_TYPE                    微調整@v1
    COMMON_GETTER_SITUATION.ERB @GET_ITEMNAME                   新規作成@v2
                                @ITEM_TYPE                      R#仕様に変更@v1
                                @ITEM_TYPENAME                  R#仕様に変更@v1
    COMMON_GETTER_SURRENDER.ERB @GET_SURRENDER_LV               新規作成@v3
                                @GET_SURRENDER_NUM              新規作成@v3
                                @GET_SURRENDER_POINT            新規作成@v3
                                @GET_SURRENDER_STR_M            新規作成@v3
                                @GET_SURRENDER_STR_T            新規作成@v3
                                @IS_SURRENDER_DISPLAYABLE       新規作成@v4
                                @SURRENDER_LV2POINT             新規作成@v3

ERB\FUNCTION\PROCESS\
    COMMON_PROCESS_CALC.ERB     @ASSISWAP                       不要なSWAPにより不具合が生じていたので修正@v1

ERB\FUNCTION\PROCESS\KOMEIJI_FUNCTIONS\
    MISC.ERB                    @INPUT_RANGE                    某パッチより取り込み@v1
                                @NOBYNAME                       某구상より取り込み@v1
                                @SIGNS                          某パッチより取り込み@v1
                                @SIGNV                          某パッチより取り込み@v1
                                @SRL                            某구상より取り込み@v1

\ERB\FUNCTION\ぱにめーしょん\
    PANIMATION.ERB              @FADE                           一部環境(主に私のNotePC)でフェードがうまく機能しなかったので対策@v4

ERB\SYSTEM\
    START_SELECT.ERB            @START_CHARA_SELECT_T           微調整@v2

\ERB\SYSTEM\SHOP\
    BONUS_GAIN.ERB              @BONUS_GAIN                     R#仕様に変更。LOCAL地獄をケジメ。微調整@v3
    CONFIGURE.ERB               @CONFIGURE                      状況に関わらず독심능력が変更可能だったのを修正。他、微調整@v3
                                @CONFIG_AI_FREEDOM              微調整@2
                                @CONFIG_ANIMATION_EFFECT        REDRAWを変え하며 戻していないのを修正。あと若干魔改造@v1
                                @CONFIG_MASTER_PREGNACY         @CONFIGUREに統合@v3
                                @CONFIG_MINDREADING             @CONFIGUREに統合@v3
                                @CONFIG_PAD                     Enterを新たに割り当てる事が出来なかったのを修正。他、微調整@v3
                                @CONFIG_RENAME_MASTER           微調整@v2
                                @CONFIG_SHOW_TALENT             @CONFIGUREに統合@v2
                                @KOJO_COUFIG_SET                @KOJO_CONFIG_SETに名前変更。微調整@v3
                                @SET_KEY_DEFAULT                微調整@v2
    SHOP_TRAINERDATA.ERB        @NEW_PRINT_ABL                  改行位置と表示項目と色の調整@v3
                                @NEW_PRINT_EXP                  参照ずれを修正。改行位置と表示項目と色の調整@v3
                                @NEW_PRINT_TALENT               改行位置等調整。LOCAL地獄をケジメ。微調整@v3
                                @PRINT_STATUS                   微調整@v2
                                @PRINT_STATUS2                  未취득分もグレー表示されるように変更。改行位置等調整。굴복実績の仕様変更@v4
                                @PRINT_TENSION                  微調整@v2

\ERB\TRAIN\
    EVENTCOMEND.ERB             @EVENTCOMEND                    굴복実績の仕様変更@v3
    TRAIN_PROCESS.ERB           @SHOW_STATUS                    無駄にボタン化しないように変更。微調整@v4
    USERCOM.ERB                 @SHOW_EQUIP                     시오후키追加、Ｃ절정/Ｖ절정/Ｂ절정/Ａ절정を大文字に修正。他、微調整@v3

\ERB\TRAIN\ACT\
    ACT_MESSAGE.ERB             @TRAIN_MESSAGE2_90              +にならない場合もあった気が했다ので修正@v3
                                @TRAIN_MESSAGE2_91              同上(多分こっちはならないけど)@v3
                                @TRAIN_MESSAGE2_92              同上(多分こっちはならないけど)@v3

\ERB\TRAIN\TRAINSYS\
    EXP_CHECK.ERB               @EXP_CHECK                      굴복実績の仕様変更。Ｃ경험/ｖ경험/ｂ경험を大文字に修正。시오후키追加@v3
    INFO_GAUGE.ERB              @INFO_GAUGE_TRAINER             無駄にボタン化しないように変更。他、微調整@v3
    SOURCE_1.ERB                @CALC_SOURCE00_EX               뽑지않고두발と뽑지않고세발を調整。시오후키追加@v3
    SOURCE_MARK.ERB             @MARK_CHECK_GET                 굴복実績の仕様変更@v3
                                @MARK_CHECK_SOURCE_SURRENDER    굴복実績の仕様変更。뽑지않고두발/三発をSOURCE_1.ERB@CALC_SOURCE00_EXに移動@v4
                                                                ※TFLAG:안빼고 がこの直後にクリアされるため。あるいは손抜き
                                @MARK_CHECK_SOURCE_SURRENDER_CHECK  굴복実績の仕様変更@v3
