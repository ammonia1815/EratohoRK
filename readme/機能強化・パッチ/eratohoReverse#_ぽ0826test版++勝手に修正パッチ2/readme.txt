2012/10/1

以下の不具合を修正

・SANDBOX、EXTRA모드開始時に죠교대상の체력기력이성の最大値がおかしくなることがある
・밀어넘어지는중に죠교대상が절정しても해방されない
・죠교で得られる마력が想定よりも少ない

2012/9/26

自前修正が溜まってきたのでうｐ
以下の不具合を修正

・윤활、울굴が上がらない
・안면승마しているのに죠교자が죠교대상の背後にいるような文が表示される
・조수１の행동が조수２の행동として表示されることがある
・素質「장신」を持っていても表示されない


具体的な変更箇所

COMMON_GETTER_CHARA.ERB
・장신のカテゴリを非表示から体質に移動

TRAIN_PROCESS.ERB
・조수のACT処理後にASSI = ASSI:1を追加

MASTER_POSE.ERB
・안면승마、밀어넘어짐による強制누움の処理で
　TCVAR:MASTER:위치전후 = TEQUIP:밀어넘어지는중 || IS_NOWACTNAME("밀어 넘어트린다") ? 1 # 0
　↓
　TCVAR:MASTER:위치전후 = 1

SOURCE.ERB
SOURCE_1.ERB
・SUMARRAYが入力値を無視して常に0を返してくる所を単純加算に置き換え

MASTERCUSTOM.ERB
・BASE_MASTER_SETUPの処理を複雑化
