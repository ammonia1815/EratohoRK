_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
・名称		R#ぽ0616test版++用勝손に修正パッチRel3
・動作環境	eratohoReverse# ぽ0616test版++
・作者		/L
・配布元	http://ux.getuploader.com/aba98725/
_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#

[修正内容]
　□CSV
　　1.CFLAG:1230,노예목걸이봉인を追加
　　2.Str.csv, 0~103までをACT분류毎に区切るように
　　3.Train.csv, 0~70までを分類毎に区切るように
　　4.Tequip.csv, 88,착의노출 100,죠교대상Ｃ사용にコメントを追加
　　5.Tcvar.csv, 40,상태변화のコメントを現行仕様に合うように
　□ACT_ABLE.ERB
　　1.@ACT_ABLE11가슴애무に於いてTEQUIP:성교봉사중, 2, 5, 6の際は規制するように
　□ACT_APPLY.ERB
　　1.@ACTION_APPLY2_57に於いてREACT분류"거부", "날뛴다", "逃げる"の箇所を修正
　　　COM자위를 시작한다とACT파생で切り分け、汚れ処理も切り分けるように
　□ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE2_11に於いてTFLAG:ACT파생 == 3のみで受容扱いの箇所に!IS_COMGRONAME("날뛴다")を追加
　　2.@TRAIN_MESSAGE2_27に밀어넘어짐終了の分岐を追加
　　3.@TRAIN_MESSAGE2_42のIS_COMGRONAME("적극적으로 한다")をIS_COMGRONAME("受け入れる/적극적으로 한다")に
　　4.@TRAIN_MESSAGE2 봉사系の拒絶となる箇所にIS_NOWCOMNAME("자위를 시작한다")を追加
　　5.@TRAIN_MESSAGE_51にACT파생1,펠라強制を追加
　□SOURCE_MESSAGE.ERB
　　1.죠교대상절정及び죠교대상사정의際、NOWEX:MASTER:방뇨を弾くように
　　2.下層にNOWEX:MASTER:방뇨を処理する箇所を追加
　□COM_XX.ERB
　　1.@COM7に於いてREACT1をCOM印象"0から遠ざかる"に
　　2.@COM21に於いてREACT파생を定義し、Ｖ/Ａ성교をそれぞれREACT파생で参照できるように
　　3.@COM30でREACT파생を定義。REACTION_MESSAGEに倣い、快SOURCEで派生0と1に分ける
　　4.@COM33を@COM7と同様に修正。派生1の「意見を出すなんていい度가슴だね！」は納得できる形に
　　5.@COM52内のTFLAG:ACTをIS_NOWACTNAMEに。자위系はGETBITで見るようにそれぞれ変更
　□COMABLE.ERB
　　1.@COMABLE21及び@COMABLE22に於いてTALENT:MASTER:남자である場合の規制を解除
　　2.@COMABLE50に於いてACT15,키스時に発生するのは違和感があったので規制
　□REACTION_MESSAGE.ERB
　　1.COM0に눈가리개장착時の分岐を追加
　　2.COM7に「意見を出すなんていい度가슴だね！」の場合の処理を追加
　　3.COM22,負荷2の箇所をV_SEX(TARGET)で分けるように
　　4.COM32に負荷2の処理を追加
　　5.COM33に「怯えに対し苛立つ」の処理を追加
　　6.COM41に「消極的なのが気に入らない」の処理を追加
　□EVENT_S.ERB
　　1.@EVENTTURNEND, 노예목걸이이벤트を구상側で봉인可能なように
　　　任意の箇所でCFLAG:노예목걸이봉인 = 1することで봉인が可能
　□COMMON_GETTER_TRAIN.ERB
　　1.@ACTSTRに於いてその他の処理になる際、ACT名称を返すように

[Rel2, 修正内容]
　□SOURCE.ERB
　　1.KOJO_EVENT(20)呼び出し箇所のMASTER_EX及びTARGET_EXのビット和での指定を廃し省略するように
　　2.上記箇所の前にFLAG:지문제어をリセットするように

[Rel3, 修正内容]
　□CSV
　　1.Tcvar.csv 60,만족보너스/61,금회대만족/62,금일만족보너스を追加
　□EVETRAIN.ERB
　　1.만족보너스のRESULT参照箇所を拡張の上、TCVAR:금일만족보너스への代入処理を追加し조교중に参照可能なように
　　　当該플래그は39行目で-1にリセット
　□EVENTCOMEND.ERB
　　1.대만족보너스の箇所、723行目にTCVAR:금회대만족への代入処理を追加。現状、他の箇所での参照には用いていない
　□ACT_ABLE.ERB
　　1.@ACT_ABLE35に於いてTEQUIP:페니스밴드、TEQUIP:바이브による規制を解除
　　　TEQUIP:항문바이브、TEQUIP:항문비즈、TEQUIP:관장그릇＋플러그の際は規制するように
　□ACT_MESSAGE.ERB
　　1.@TRAIN_MESSAGE_25, "クリップ로터を貼り付けようと했다"→"クリップ로터を取り付けようと했다"に変更
　　2.@TRAIN_MESSAGE2_35, IS_COMGRONAME("소극적으로 한다")の箇所に於いて、"嫌がった", "悲鳴をあげる"をCOMで切り分け
　　　より納得のできる形に変更
　　3.@TRAIN_MESSAGE2_41, IS_COMGRONAME("용서를 빌다")の箇所を書き直し
　□REACTION_MESSAGE.ERB
　　1.派生をTRAINNAME:SELECTCOMで記述するように変更
　　2.COM7,용서를 빌다に於いて、負荷2の箇所を一部修正
　　3.COM8,기분좋게 해にTFLAG:REACT파생 == 1の処理を追加

※Emuera1818+v7も付けてあります。今回は必須という訳ではありませんが、なるべく新しいものが望ましいです

※付属の各フォルダを本体のERB、CSVフォルダに上書きして使用して下さい
　現状あくまでも非公式であることをご理解の上、導入してください
　また、当パッチを導入했다事による不具合のサポートを、システム側に求めないようお願いします

●連絡先
Twitter:@L7switch
mail:layer7.inc@gmail.com
(2014/03/26) /L