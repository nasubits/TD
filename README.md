# タワーディフェンスの進めかた
## 目標を作る
- 全体の目標
  - がめおべらとクリアができるまで！
  - 敵と味方が戦う感じになればよき
  - とりあえず完成したい！(立ち消えたくない！)
  - *最低限の動作！*

- 個人の目標
  - のむさん目標
    - みんながpython覚える
    - 1か月いないに完成
  - ハマちゃんの目標
    - if と for の使い方を覚える(使いどころ)
    - whileの使い方を覚える(使いどころ)
  - おなすの目標
    - 外部ファイルの読み書き、参照とかしたい。
    - エクセルうまく使いたい！

## 仕様決め
- (最初はCUIで超最低限のものだけを作る)(ゲーム性無視、動くこと優先)
  - マップ
      CUI・セル
  - 位置情報(敵も味方も)
  - 死亡フラグ
    - 自分の体力が0になる
  - 敵の移動
    - 進める範囲を見て、敵がいたらそこまで進む(複数いたら一番近いやつまで)
  - 味方の配置
    - (味方拠点と敵生成地点を省く)[1:9]
  - 勝敗条件
    - 勝利条件：敵の全滅
    - 敗北判定：味方拠点に辿り着かれる
  - 敵と味方の接触判定(攻撃)
    - 同セル
  - 生成コスト
    - 最大10


## まとめる
- map
  - list(全長)[10]
  - goal(味方拠点)[-1]
  - start(敵生成地点)[10]

- player
  - 位置情報:int
    - 攻撃判定(接触時：同マス)
  - death_flag:bool(Ture or False)
  - ステータス
    - 体力(10)・攻撃力(10)・攻撃範囲(0)・消費コスト(1)

- enemy
  - ステータス
    - 進行スピード・体力(今回は1)・攻撃力(今回は1)・攻撃範囲(0)
  - 位置情報
    - 攻撃判定
    - 進行判定(同セルに敵がいたら進まない)
  - death_flag

  - ゲームの流れ
    - 1. Mobの生成・配置、ターン進行:while文
      - Mobの配置
        - map情報を取り出し、コストを消費して空きセルに配置
        - 取り出した情報から、空きセルとenemyの位置を表示する
      - ターン進行
        - 1を繰り返すフラグを偽にする
    - 2. ターン：Mob・enemyの動作
    - 3. ターン終了・ゲームのオートセーブ


## 役割分担
  - それぞれの目標のところをやる
    - はまー：for，if，while
    - なす：外部ファイルの入出力

## 日程を決める
- 週に１回進捗報告的なのをする
- 週に３回は集まって作る(２時間くらい)
- 
## 作っていく


flag = True
while flag == True
create :配置
attack :flag = False