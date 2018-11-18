_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
・名称			R#ぽ0203+6用勝손に修正パッチRel3
・動作環境		eratohoReverse# ぽ0203test版+6
・作者			/L
・配布元		http://ux.getuploader.com/aba98725/
_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#

[修正内容]
EVENT_K.ERB
　　1.@KOJO_REACTにコンビネーションREACT及び派生元を呼び出す処理を追加
ACT_APLLY.ERB
　　1.@ACTION_APPLY2_5に於いてREACT분류の誤りと思われるものを修正
ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE_12に於いてRAND:2をT_COND("정욕")に変更
　　2.@TRAIN_MESSAGE_14において不要な空行と思われるものを削除
　　3.@TRAIN_MESSAGE_34に於いて、意味不明な空のPRINTFORMLを正しいと思われる形に修正
　　4.성교봉사系@TRAIN_MESSAGEにおいて@V_SEXがTARGETを参照していたのをMASTERに修正
　　5.@TRAIN_MESSAGE_99に於いて代入されていないACT파생を参照しているのを修正
　　6.@TRAIN_MESSAGE_303に於いて脱字を修正
　　7.@TRAIN_MESSAGE2_5に於いて、下位の分岐の妨げになると思われるELSEIF ACTION_APPLY2_5V(-1) == 2をコメントアウト
　　8.修正の際に一緒に置換されてしまったと思しき空行用のPRINTFORMLをPRINTLに
　　9.コピペの際にずれたと思しきインデントを修正
SOURCE_MESSAGE.ERB
　　1.コンビネーションに派生し得る箇所のIS_NOWACTNAMEをGET_ACTNAME(GET_NORMALACTNUM(TFLAG:ACT))に
　　2.조수協力時のCFLAG:ASSI:조조방바늘 == 1をTCVAR:(ASSI:1):조수방침 == GET_ASSIMENUNUM("コンビネーション")に

[Rel2. 修正内容]
COMMON_GETTER_TRAIN.ERB
　　1.REACT인상関連関数群
　　　@COMIMPLIST/@GET_COMIMPNAME/@COMIMPNAME/@GET_COMIMPNUM/@COMIMPNUM/@NOWCOMIMPNAME/@IS_NOWCOMIMPNAME/@IS_COMIMPNAME
　　　以上のものを追加
ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE2_40に於いて受容となる箇所にREACT분류:受け入れを追加の上、적극적으로 한다と並列処理
　　2.@TRAIN_MESSAGE2_45に於いて受容となる箇所にREACT분류:受け入れるを追加
ACT_APPLY.ERB
　　1.@ACTION_APPLY2_57に於いて受容となる箇所にREACT분류:소극적으로 한다を追加
　　　拒絶となる分岐にREACT분류:거부を追加
　　2.@ACTION_APPLY2_90に於いてIS_NOWCOMNAME("자위를 시작한다")の箇所のSET_COMGRO("거부")をコメントアウト
　　3.@ACTION_APPLY_92に於いてCOM도구를 제거한다で날뛴다扱いになり得るTEQUIP解除処理を追加の上コメントアウト
　　　(本体側の判断に委ねたい意向)
COM_00.ERB
　　1.@COM1に於いて애원となる分岐条件にIS_NOWACTNAME("매도")を追加
　　2.@COM7に於いてREACT파생 = 0の処理をELSE以降で行うように
COM_10.ERB
　　1.@COM11に於いてACT:역강간の際REACT분류:날뛴다にならないように修正
COM_30.ERB
　　1.@COM32に於いてACT:역강간の際REACT분류:날뛴다にならないように修正
　　2.@COMM33に於いてREACT파생 = 0の処理をELSE以降で行うように
COM_50.ERB
　　1.@COM50 派生:勝손にオナニーするなとなる箇所の条件にMENUMATCH(TFLAG:ACT, "봉사")とIS_NOWACTNAME("휴식시킨다")を追加
　　　SET_COMGRO/SET_COMIMPの処理を派生毎に切り分け。派生1はSET_COMGRO("거부")/SET_COMIMP("悪印象大")に
　　　의존도변화処理も別途追加
REACTION_MESSAGE.ERB
　　1.CA%TSTR:2%SE 4,강하게 응답한다のREACT파생代入処理をコメントアウト(@COM4で代入が行われている為)
　　2.CASE 7,용서를 빌다の負荷2が納得いかなかったので修正
　　3.CASE 12,서투르다고 모욕한다に於いてTFLAG:REACT인상をIS_COMIMPNAMEに
　　4.CASE 14,쾌감을 참는다に於いて負荷2/COMCOR_POSI()の箇所が納得いかなかったので修正
　　5.CASE 30,고통을 참는다に於いてACT:이라마치오かつ負荷0の場合「歯を食い縛る」となるのを回避するよう修正
　　6.CASE 70,가게해줘に於いてREACT파생0相当の分岐がなかったので追加

[Rel3. 修正内容]
COMMON_GETTER_CHARA.ERB
　　1.@AFFECTIONに定義"공포", "반항"を追加、及び未定義でエラー落ちする際(%ARGS%)で内容を拾えるように
EVENT_DAYLY.ERB
　　1.DAILY_LIFE_NURSINGにARG:1(疲労で조교중止되었다場合)を追加
　　　구상側は일상이벤트@KOJO_EVENT_KX_201(ARG)に於いてIF LOCAL && ARG == 1で記述する事が可能
ROUTINE.ERB
　　1.FLAG:END달성への代入をRESULT値0以上で行うように
EVENTCOMEND.ERB
　　1.죠교終了の判定の際にFLAG:일상제어をリセットするように
EVENTRAIN.ERB
　　1.대만족보너스関連を손入れ
　　　"%CALLNAME:TARGET%님 대만족 보너스"の表示が目立つように変更
　　　KOJO_EVENT(16)後にPRINTLで空行が入るように
　　　CFLAG:만족보のリセットを금일의방침地の文の処理を抜けてから行うように
　　　上記の変更に伴い、금일의방침(항문/징계・/하드)の箇所は만족보の有無で地の文が변화するように
　　　금일의방침派生をTFLAG:금일의방침からPOLICY("금일")に変更
TRAIN_PROCESS.ERB
　　1.전회의행동を表示して今回の행동を決定の箇所で%TSTR:2%を%TSTR:前죠교指令%
　　　%TSTR:1%を%TSTR:죠교指令%にそれぞれ変更
ACT_ABLE.ERB
　　1.성봉系ACT(ACT_ABLE95~103)に於いてTEQUIP:삼각목마を規制
COMABLE.ERB
　　1.@COMABLE40に於いて역강간を거부できないように
その他
　　本体付属の이벤트구상번호.txtから存在していない(14,コマンド前구상)部分を削除

※これまでリリース했다分はRel3に統合してあります。
　付属の各フォルダを本体のERBフォルダに上書きして使用して下さい

●連絡先
Twitter:@L7switch
mail:layer7.inc@gmail.com

(2013/06/15) /L