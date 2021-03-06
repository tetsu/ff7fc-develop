----------------------------------------------------------------------
FF7FC
----------------------------------------------------------------------
■プログラム製作者
  BETA

■操作方法
  ・↑↓→←         : 矢印キー
  ・決定             : x
  ・キャンセル       : z
  ・メニュー         : space
  ・キャラチェンジ   : c
  ・終了             : ESC or q
  ・エンカウント     : s
  ・デバッグ情報表示 : a
  ・エンカウントのオンオフ切り替え: a + s
  ・イベント情報出力 : F1
  ・処理速度を上げる : テンキーのプラス
  ・処理速度を下げる : テンキーのマイナス
  ・処理速度を通常に戻す : テンキーのアスタリスク
  ・当たり判定有効／無効切り替え: 左シフトキー
  ・簡易セーブデータ切替: F2
    F2押下で記録先を以下のように切り替える
       ./save/status_data => ./save/status_data1 => ./save/status_data2 => ./save/status_data3 => ./save/status_data4
    => ./save/status_data => (繰り返し)
  ・簡易セーブ       : F5 (./save/status_data(なし,1,2,3,4)に記録する)
  ・簡易ロード       : F7 (./save/status_data(なし,1,2,3,4)を復元する)
    ※簡易セーブ＆ロード機能で記録＆復元されるデータは以下のみ
    ・全メンバーのステータス
    ・パーティ構成
    ・所持アイテム
    ・所持ギル
    ・コンフィグ設定
    ・イベントフラグの７番以降

■設定
  ・config_CS.exe
    ・XキーとZキーの入れ替え
    ・画面サイズ変更
    ・垂直同期on/off設定
    ・ゲーム開始時のシーン選択
    ・ゲームスタート位置
    ・ウィンドウ非アクティブ時の挙動
  ・keyConfig.exe
    ・キー設定

■動作環境
  以下の環境で正常動作を確認済み
  ・OS    :windows7
  ・CPU   :Intel Corei5 CPU 750 @2.67GHz
  ・MEMORY:4.00GB
  ・グラボ:NVIDIA GeForce GT220

■フォルダ構成
  FF7FC
  |--documents/            各種ドキュメント置き場
  |  |--イベントスクリプト命令一覧.txt
  |  `--イベントフラグ管理表.xls
  |
  |--event/                イベントファイル格納フォルダ
  |  |--script/            イベントスクリプトファイル格納フォルダ
  |  |--script_e/          イベントスクリプトファイル格納フォルダ(英語版)
  |  |--event.csv          イベント情報(NPCの追加など)
  |  `--event_e.csv        イベント情報(NPCの追加など)(英語版)
  |
  |--image/                画像ファイル格納フォルダ
  |--item/                 アイテムデータ格納フォルダ
  |--item_e/               アイテムデータ格納フォルダ(英語版)
  |--mapdata/              マップデータ格納フォルダ
  |  |-- mapdata_000       マップエディタで作成したマップデータ
  |  |        |
  |  |-- mapdata_999
  |  `-- setting.txt       マップ毎の以下の設定が定義されているファイル
  |                        BGM/戦闘画面背景画像ファイル名/エンカウントする敵グループID
  |--mapeditor/            マップエディタ
  |--monsterdata/          モンスターデータ格納フォルダ
  |  |-- monster_data.csv        敵個別のステータス、画像ファイル名などの定義
  |  `-- monster_party_data.txt  敵グループIDの定義ファイル
  |--monsterdata/          モンスターデータ格納フォルダ(英語版)
  |
  |--save/                 セーブファイル格納フォルダ
  |
  |--sound/                サウンドファイル格納フォルダ
  |  |--bgm/               BGM格納フォルダ
  |  |--se/                SE格納フォルダ
  |  `--setting.txt        戦闘以外のBGMファイル名の定義
  |
  |--text/                 文字列リソースファイル格納フォルダ
  |--text_e/               文字列リソースファイル格納フォルダ(英語)
  |--tools/                ツール類
  |  |--make_map_data/     マップ画像及びマップチップ画像からマップデータを生成するツール
  |  |--map_chip_edit/     不明
  |  `--map_chip_id_replacer/ チップＩＤを変換するツール
  |
  |--config_CS.exe            各種設定変更用プログラム
  |--EventEditor_CS.exe    イベント作成ツール
  |--FF7FC.exe             ゲーム本体
  |--ini.bin               config.exeで生成した設定ファイル
  |--keyConfig.exe         キー設定ツール
  |--keySetting.bin        キー設定情報定義ファイル
  |--readme.txt            このファイル
  |--SaveDataEditor.exe    セーブデータ編集ツール
  |--マップNO対応表.txt    マップNO対応
  `--新キャラチップ対応表.txt キャラID対応表

  ●マップ毎のBGMの設定を変更したい場合
    ・"./mapdata/setting.txt"を編集する
      IDの列に0から999までの数字が並んでいるので、
      対応する行のbgmの項目を書き換えて下さい
      id         :マップID
      type       :未使用
      bgm        :BGMファイル名
      battle_back:戦闘画面背景

■実装保留項目
  ・マップに入ったときにマップ名を画面上部に表示させる
  ・オープニング電車
  ・ボス消滅アニメ
  ・パーティアタック
  ・ジャンプのchg_speed

■更新履歴
  ・更新履歴は以下を参照
    https://github.com/beta1139/ff7fc-develop/commits/master

  ・2013/1/8
	・イベントスクリプトの命令追加
	  ・loop_inf〜pool文
	  ・play_se_loop
  ・2013/1/2
    ・脱出時の爆発のエフェクト入れた
	・モンスター画像追加
  ・2013/1/1
	・イベントスクリプトの命令追加
      ・chg_image_pos
      ・chg_image_pos_offset
      ・set_image_trans_col
  ・2012/12/31
	・イベントスクリプトの命令追加
	  ・draw_image
	  ・erase_image
	  ・set_image_alpha
	  ・inc_image_alpha
	  ・dec_image_alpha
  ・2012/12/30
	・イベントスクリプトの命令追加
	  ・draw_countdown
	・エレベーター移動中にカウントダウンウィンドウの表示を消すようにした
	・chg_char_state_moveを実行中に別のイベントスクリプトの実行が始まった場合に、
	  キャラの動作が止まることがあるバグ修正
	・map_id:7のマップにmap_doorを設置
	・マップエディタのマップ座標表示を追加
  ・2012/12/29
	・マップエディタにコピペ機能追加
  ・2012/12/27
	・イベントスクリプトの命令追加
	  ・backup_char_dir
	  ・restore_char_dir
	・マップ間ワープ中にmap_objの表示が消えることがあったバグ修正
	・ロードでthroughのマップから始めると無音になるバグ修正
  ・2012/12/26
    ・oggファイル再生開始時にLOOPSTARTコメントを読み取り、
	　ループ位置を設定するようにした
  ・2012/12/23
    ・config_CS.exeでゲーム開始時の初期位置を設定できるようにした
	・イベントスクリプトの命令追加
	  ・chg_char_img_tmp
	  ・reset_char_img_tmp
	  ・set_map_draw_y_offset
	  ・inc_map_draw_y_offset
	  ・dec_map_draw_y_offset
	・エレベーターのイベントをＤＱ４風にした
  ・2012/12/22
	・bgm_throughで戦闘ＢＧＭ鳴りっぱなし修正
	・ショップを開いた後、セリフウィンドウにNPCが隠れなくなるバグ修正
    ・if分の入れ子対応した
	・セレクトボタンでキャラチェンジなしにした
	・エンカウントのエフェクト中のmap_objとmap_doorの表示がそのままなのを直した
	・以下のイベントスクリプトの命令追加
	  ・enable_char_chg
	  ・disable_char_chg
	  ・chg_char_state_move
	  ・chg_char_state_event
	  ・chg_npc_y_offset
	・Ｆ１押下でイベントデータの情報をファイル(event_info.txt)出力するようにした
  ・2012/12/20
    ・Part9@635のマージ
  ・2012/12/19
    ・map_obj.bmpの画像の幅を256固定にして、
　　  はみ出す分は下の行の画像を使うようにした
  ・2012/12/17
    ・Part9@597をマージ
  ・2012/12/15
    ・ワープ時にmap_objとmap_doorの表示がおかしいバグ修正
    ・キャラチップ更新
    ・以下のイベントスクリプトの命令追加
	  ・set_text_col
  ・2012/12/14
    ・キャラチップ更新
	・テキストに()追加
	・起動直後のＦＦ３風テキストイベント実装
	・config.exeをC#で作り直した
	  起動直後のゲームの状態を以下から選択できるようにした
	  ・ＦＦ３風テキストイベント
	  ・タイトル画面
	  ・はじめからorコンティニュー画面
  ・2012/12/13
    ・Part9@547,549をマージ
	  (内容)
	  ・バレット怒りモーションのキャラチップ追加
      ・二つの「map_door」(map_door.bmp)を追加
      ・「se」フォルダの"warp out.wav"の最後に乗ってたポップノイズを除去
      ・「bgm」フォルダの"Ex-02-Train_Noise_Open.ogg"の音量をマイナス1.5db
      ・mapdata016のグラを一部修正
      　(座席があるとその後場所変える必要ないなと思ったので・笑)
      ・イベントフラグに七番スラムのBGM(ティファ加入)を収納
        mapdataのsetting.txtを変更
      　これにより七番街スラムのBGMを途中で切り替え(On_that〜→Barrett's_Theme)
      　(セブンスヘブンのBGMは固定)
      ・map_obj.bmpを更新
      　アバランチ・アジトの入り方を変更
      　(手前でAボタンを押してジャンプ)(でも地味だという/笑)
      ・列車飛び降りシーンでのマップ＆スクリプトを微修正
      　(原作のように途中でトンネルに入るようにした)
      ・一番魔晄炉の前々から気になってたスペースに宝箱配置
      　(手前でAボタンを押してジャンプ)
      　(こういうオリジナルの遊びをちょくちょく入れとくのも面白いかなと思ってるんですが、
      　不要なら遠慮なくデリートでw)
      ・一番魔晄炉と七番スラムにセーブポイントを追加
  ・2012/12/11
    ・Part9@539のスクリプトファイルをマージ
  ・2012/12/09
    ・スクリプトの命令追加
	  jump_char_target_pos
	・イベント作成
	  ユフィのイベント作りかけ
  ・2012/12/08
    ・スクリプトの命令追加
	  jump_char
  ・2012/12/07
    ・スクリプトの命令追加
      set_slide_walk_char_flag
      reset_slide_walk_char_flag
	  set_slide_npc_flag
	  reset_slide_npc_flag
	  set_slide_walk_npc_flag
	  reset_slide_walk_npc_flag
	  warp_ff3
	  door_open
	  door_close
	・イベントタイプ追加
	  map_obj
	  map_door
	・セブンスヘブンのイベントでカウンター上げ下げを実装
	・列車内でジェシーがドアを閉めるイベント実装
	・７番街スラムに開閉するドアを設置
  ・2012/12/06
    ・BGM追加
      Ex-02-Train_Noise_Open.ogg
      Ex-01-Train_Noise_Close.ogg
    ・SE追加
      ケアル、ケアルラ
    ・jump_npcのsameでchg_npc_imgが利かなくなる不具合修正
    ・スクリプトの命令追加
      set_slide_char_flag
      reset_slide_char_flag
  ・2012/12/03
    ・move_char命令を非同期に変更
    ・スクリプトファイルのmove_charを使用している全ての箇所に
      キャラの移動量*16の時間のsleepを挿入
  ・2012/12/02
    ・以下のイベントスクリプトの命令追加
      ・chg_npc_img
      ・chg_event_move_char_speed
    ・イベントフラグのid:0の値が4のときは
      再生中のBGMをずっと再生させたままになるようにした
    ・./mapdata/setting.txtでthrough指定で前に再生していた
      フィールドBGMを再生するようにした
  ・2012/12/02
    ・以下のイベントスクリプトの命令追加
      ・loop 〜 pool文
      ・set_text
      ・set_text_alpha
      ・clear_text
    ・デバッグエリアに上記の命令を使用したイベント追加
  ・2012/12/01
    ・>>part9@451のマージ
    ・>>part9@458のマージ
    ・BGMファイルリネーム
    ・ニューゲーム、つづきからの画面に背景画像表示
  ・2012/11/27
    ・七番街到着〜ティファ合流までのイベントを作成
    ・マップID:701,702を追加
    ・マップID:22のグラ、アタリ判定を一部変更
    ・宿屋のBGMをSEフォルダに変更(ループ再生を防ぐため)
    ・ワープチョコボ一部変更
    ・"mapdata_011"と"mapdata_033"を削除
    ・chg_typeでnpc3指定できないバグ修正
    ・npc_eventをnot_moveにすると
      chg_typeでnpcにしてchg_speedでnot_move以外にしても動かなくなるバグ修正
    ・リミットアニメーション中も瀕死時の汗が表示されていたのを修正
  ・2012/11/26
    ・ガードスコーピオン戦前のイベントにキーン音追加
    ・セーブポイント実装(event_editor_CS.exeも更新)
    ・BGM追加(1-00-Barrett's_Theme.ogg)
    ・アイテムを拾ったときのSE更新
    ・マップNO対応表.txtを格納
    ・ジャンプするキャラに話しかけるときに移動キー入力でバグるのを修正
    ・デバッグエリアのNPCのIDかぶり修正
    ・駅長の画像を駅長に変更
  ・2012/11/25
    ・キャラチップに駅長追加
    ・ヘビーショットの色を赤に変更
    ・BGM追加(1-02-00-Opening.ogg)
    ・以下のイベントスクリプトの命令を追加
      ・play_event_bgm
      ・recover_active_chara
      ・step_npc
      ・jump_npc
      ・jump_npc_target_pos
      ・slide_npc
      ・slide_walk_npc
      ・set_npc_pos
  ・2012/11/24
    ・キャラチップ更新
    ・取水塔マップ追加
    ・フォントに'〜'を追加
    ・「ぼうぎょ」、「チェンジ」の選択をキャンセルすると
    　カーソル位置がバグるのを修正
    ・マテリアの画像更新
    ・マップ上に落ちているマテリアをアニメーションさせるようにした
    ・マテリア取得時SE変更
    ・通常戦闘BGM更新
    ・BGM追加(生命の流れ(海外名：3-02-Life_Stream))
  ・2012/11/23
    ・7番街のイベントスクリプトをマージ
    ・列車内のBGM変更
    ・ゲーム開始時にデバッグ用ワープ装置配置
    ・バトルキャラの画像更新
    ・ケアル、ケアルラのエフェクト実装
    ・ロード時にNPCの位置がずれるバグ修正
    ・ファイアとブリザドのSE追加
    ・瀕死キャラの汗実装
    ・リミットが溜まった後１回だけTIMEが早く溜まるようにした
  ・2012/11/18
    ・フォントに「ぁぃぅぇぉ」を追加
  ・2012/11/17
    ・話しかけても振り返らないnpc3を実装
    ・以下のイベントスクリプトの命令を追加
      ・if_owned_item 〜 fi 文
    ・アイテムデータを拡充
  ・2012/11/16
    ・config.exeに言語の選択項目を追加
    ・花売りイベントを強制化
    ・花売りイベントで花を買ったかの結果を
    　イベントフラグに格納するようにした
    ・コンティニューで始めるとDOORがNPCになるバグ修正
  ・2012/11/11
    ・戦闘中でもカウントダウンのイベントでゲームオーバーになるようにした
    ・ゲーム開始から一番魔光炉突入までは戦闘中でもフィールドBGMを流したままに修正
  ・2012/10/14
    ・以下のイベントスクリプトの命令を追加
      ・if_party_mem 〜 fi 文
      ・if_active_mem 〜 fi 文
      ・if_char_img 〜 fi 文
      ・wait_target_talk
      ・reset_talk_flag
      ・backup_npc_dir
      ・chg_dir_to_char
      ・set_talk_npc
      ・restore_npc_dir
      ・reset_talk_npc
  ・2012/10/11
    ・wait_talkのイベントの上に拾えるアイテムを
      重ねて話しかけるとバグるのを修正
    ・screen_effect blueの効果を薄くした
    ・shop系のスクリプト命令の仕様を変更
    ・以下のイベントスクリプトの命令を追加
      ・kill_through
      ・recover_talked_npc_dir
  ・2012/10/07
    ・八番街の兵士に追い込まれるイベント実装
    ・列車内のイベント実装
    ・以下のイベントスクリプトの命令を追加
      ・chg_param
  ・2012/10/05
  　・選択肢のあるセリフを実装
  　・八番街のはなうりのイベントを実装
    ・キャラステータスに好感度のパラメータを追加
    ・以下のイベントスクリプトの命令を追加
      ・wait_target_talked
      ・if_flag 〜 fi 文
      ・add_gil
      ・sub_gil
      ・add_likability
      ・sub_likability
  ・2012/10/03
    ・コンフィグ画面を作成
    ・ATBのウェイトに対応
    ・カーソル位置のきおく実装
  ・2012/10/01
    ・爆破ミッションのカウントダウンを実装
  ・2012/09/30
    ・「サンダー」,「サンダラ」,「サンダガ」のアニメーションを実装
    ・一番街駅で最初のイベントエンカウントが終わるまではエンカウントしないようにした
    ・イベント「materia」を廃止。代わりに「treasure_item」を実装
      マテリアだけでなくマップ上に落ちているアイテムを何でも拾えるようになった
    ・以下のイベントスクリプトの命令追加
      ・wait_event_invalid
      ・set_eternal_event
      ・set_flag_wall
      ・open_item_shop
      ・open_weapon_shop
      ・open_armor_shop
      ・open_materia_shop
      ・open_acce_shop
  ・2012/09/28
    ・攻撃魔法詠唱時のエフェクト実装
    ・「ブリザド」,「ブリザラ」,「ファイア」,「ファイラ」の
    　アニメーションを実装
  ・2012/09/27
    ・リミット技開始時のエフェクト実装
    ・回復魔法詠唱時のエフェクト実装
  ・2012/09/25
    ・爆破ミッションのイベントを実装
    ・リミット技「ブレイバー」,「ヘビーショット」のアニメーションを実装
    ・セーブ画面に表示されるキャラをパーティメンバーのみとした
    ・セーブデータに汎用イベント用フラグ100バイトを追加
  ・2012/09/20
    ・独自仕様イベントスクリプトを導入
    ・一番街駅のイベントを実装
  ・2012/09/14
    ・マップ上に落ちているマテリアを拾えるようにした
  ・2012/09/13
    ・セーブデータにイベントデータを追加
    ・SaveDataEditorを新セーブデータ仕様に対応
    ・マップ毎にエンカウントの有無を外部ファイルで設定できるようにした
  ・2012/09/10
    ・バトルコマンド「リミット」を実装
    ・戦闘後にドロップアイテムがドロップする処理実装
  ・2012/09/09
    ・バトルコマンド「まほう」を実装
    ・バトルコマンド「アイテム」を実装
  ・2012/09/06
    ・戦闘後のフィールドＢＧＭ再生開始位置が
      戦闘前のフィールドＢＧＭ再生停止位置となるようにした
  ・2012/09/05
    ・バトルコマンド「にげる」を実装
  ・2012/09/04
    ・バトルコマンド「 ぼうぎょ」、「チェンジ」を実装
  ・2012/09/03
    ・敵が死ぬときのアニメーション実装
    ・バトルウィンドウの表示位置調整
    ・瀕死時および死亡時にＨＰの表示色を変えるようにした
    ・リミットが溜まるようにした
    ・戦闘画面およびメニュー画面のリミットバー表示処理実装
  ・2012/08/15
    ・SaveDataEditorを作成
  ・2012/06/29
    ・EventEditor.exeをC#で作り直した(環境依存で動作しない問題解消した？)
    ・通常攻撃のバトルエフェクトを実装した
  ・2011/09/11
    ・宝箱を実装
  ・2011/09/07
    ・エンカウント処理を実装した
    ・ダンジョンを作った
  ・2011/09/05
    ・通常攻撃のダメージ算出に計算式を導入
    ・メニュー画面から回復魔法を使えるようにした
  ・2011/09/03
    ・レベルアップ処理を実装
    ・獲得ＡＰがマテリアに溜まる処理実装
    ・セーブデータをバイナリ化
    ・セーブデータにキャラクターのステータス情報などを追加
  ・2011/09/01
    ・マテリアを装備できるようにした
　・2011/08/30
    ・マテリア屋実装
　・2011/08/29
    ・武器を装備できるようにした
    ・防具を装備できるようにした
    ・アクセサリを装備できるようにした
　・2011/08/24
　　・アイテムデータの定義を拡充
  ・2011/07/14
    ・EventEditorを作成した
  ・2011/07/09
    ・ぶき屋実装
    ・ぼうぐ屋実装
    ・アクセサリー屋実装
  ・2011/07/06
    ・どうぐや実装
    ・メニューからのアイテム使用実装(以下のアイテムのみ)
      ・ポーション
      ・ハイポーション
      ・エクスポーション
      ・エーテル
      ・エーテルターボ
      ・エリクサー
      ・フェニックスの尾
  ・2011/06/25
    ・キーコンフィグアプリ作成
  ・2011/05/24
    ・戦闘システムの雛形ができた
  ・2011/05/14
    ・新マップデータ仕様に対応
    ・マップ毎に外部ファイルでBGMを設定できるようにした
    ・キャンセルキーの押しっぱなしでダッシュできるようにした
    ・セーブ/ロードを実装(マップＩＤ，X座標、Y座標のみ)
    ・イベントファイルのマップＩＤを新しいマップに対応したものに修正
    ・Sキーの入力で現在位置の表示/非表示ができるようにした
    ・JoyPadに対応
  ・2010/12/31
    ・メニュー画面を作成中
    ・キャラチェンジ対応
  ・2010/12/26
    ・alpha 1.00 release

----------------------------------------------------------------------
※要望、バグ報告など募集
