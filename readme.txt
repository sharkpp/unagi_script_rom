famicom ROM cartridge utility - unagi
ROM dump script version 0.35.0
公式サイト http://unagi.sourceforge.jp/

--スクリプトファイルと nes header マッパ番号一覧--
==Nintendo 製とその互換品==
script        #
----------------
nrom.ud       0
unrom.ud      2
uorom.ud      2
gnrom.ud      66
mmc1normal.ud 1
mmc1_4M.ud    1
mmc2.ud       9
mmc3.ud       4,118,etc..
mmc4.ud       10
mmc5.ud       5

==Konami 製とその互換品==
注意: VRC2,4 はマッパ番号があまり役に立ちません。
script        #
----------------
rc809.ud      87
vrc1.ud       75
vrc2a01.ud    23
vrc2a10.ud    22
vrc3.ud       73
vrc4a.ud      21
vrc4b.ud      25
vrc4c.ud      21
vrc4d.ud      25
vrc4e.ud      23
vrc6.ud       24,26
vrc7.ud       85

==Sunsoft 製==   ==Taito 製==     ==Irem 製==
script        #  script        #  script        #
---------------- ---------------- ----------------
sunsoft2b.ud  89 x1_005.ud     80 irem_g101.ud  32
sunsoft3.ud   67 x1_017.ud     82 irem_h3001.ud 65
sunsoft5b.ud  69 tc0190.ud     33

==Namcot 製==    ==Bandai 製==    ==Jaleco 製==
script        #  script        #  script        #
---------------- ---------------- ----------------
namcot118.ud  88 bandai_70.ud  70 jaleco_72.ud  72
namcot163.ud  19 fcg1.ud       16 jaleco_92.ud  92
                 lz93d50.ud    16
                 fcjump2.ud    16?

--補足説明--
補足説明にて必要動作未確認と記載したもので動作確認がとれたものは是非報
告をお願いします。

特定のソフトは個別にコマンドラインオプションをつける必要があります。
この場合下記の要素を追加してください。
 unagi.exe d [スクリプトファイル] [出力ファイル] [flag] [mapper]
mapper の部分はなくてもよい場合が多いです。

==diskbios.ud==
disksystem の bios 専用です。このスクリプトは、NESヘッダを生成しません。

==mmc1_4M.ud==
大容量ROM搭載のファイナルファンタジーI.IIとドラゴンクエストIV専用です。

==mmc1normal.ud==
上記以外の MMC1 搭載ソフトに使用してください。

==mmc3.ud==
flag:S mapper:118
	ワンダラーズフロムイース
	RPG 人生ゲーム
flag:_ mapper:118
	アルマジロ

==namcot106.ud==
flag:SV
	ファミリーサーキット'91

==sunsoft3.ud==
コメントにも書いたんですが、スクリプトを書き終わった後にこのマッパのカ
セットを持ってないことに気づきました。動作未確認です。

--Konami VRC series--
マッパ番号はあてになりません。ゲームタイトルと一致するスクリプトを使用
してください。vrc シリーズを採用していないものは無関係です。

vrc1.ud:
	がんばれゴエモン！からくり道中
	キングコング2 怒りのメガトンパンチ
	エキサイティングボクシング
	鉄腕アトム
vrc2a01.ud:
	コナミ ワイワイワールド
	月風魔伝
	ドラゴンスクロール 甦りし魔竜
	魂斗羅 (注:初代)
	じゃりん子チエ
	がんばれゴエモン2
vrc2a10.ud:
	がんばれペナントレース
	ツインビー3 ポコポコ大魔王
vrc3.ud:
	沙羅曼蛇
vrc4a.ud:
	ワイワイワールド2 SOS!!パセリ城
vrc4b.ud:
	バイオミラクル ぼくってウパ (注:ROM)
	がんばれゴエモン外伝 消えた黄金キセル (本当は VRC2)
	グラディウスII
	レーサーミニ四駆 ジャパンカップ
vrc4c.ud:
	がんばれゴエモン外伝2 天下の財宝
vrc4d.ud:
	Teenage Mutant Ninja Turtles
	Teenage Mutant Ninja Turtles 2
vrc4e.ud:
	パロディウスだ！
	悪魔城すぺしゃる ぼくドラキュラくん
	クライシスフォース
	タイニートゥーン・アドベンチャーズ (注:初代)
vrc6.ud:
	悪魔城伝説
vrc6.ud: flag:S mapper:26
	魍魎戦記 MADARA
	エスパードリーム2
vrc7.ud:
	ラグランジュポイント
	タイニートゥーン・アドベンチャーズ2

--スクリプト募集--
150くらいあるマッパのスクリプトを全て私だけで書くことは出来ません。手
軽にスクリプトを追加することが出来るので、スクリプトが書けた人は公式サ
イトまで連絡をください。
採用基準は下記とさせていただきます。

* そのスクリプトを使って実際に動作確認をして読み出せたこと(とかいって
  おきながら sunsoft3.ud は動作未確認...)
* 動作確認をしたソフト数本の名称か型番をスクリプト先頭にコメントをいれ
  ること
* 読み出しに必要なレジスタは初期化してから読み出すこと (マッパのマイ
  ナーバージョンによって電源投入後の初期値が異なる場合があるので必ず
  行ってください)

