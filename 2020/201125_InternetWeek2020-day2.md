# Internet Week 2020(day2/2020-11-25)

## 概要

* <https://www.nic.ad.jp/iw2020/program/>
* 途中参加、きけるときにきけるものをきくスタンス

---

## C24 ドメインハイジャック時のインシデント対応と外部機関との連携の重要性について

* by 喜屋武 慶大(コインチェック株式会社), 中井 尚子(JPCERT/CC)
* コインチェックさんで起きたドメインハイジャックについて紹介　：NSレコードの改ざん <https://tech.coincheck.blog/entry/2020/06/24/120000>
* 発覚の経緯
    * 6/1mon　：サービスの外形監視で、5/31sunからレスポンスタイムが大きく遅延していることが発覚、SREチームによる調査開始
    * 各機器のどこにも異常がなく、遅延の原因がつかめない　→人によって遅延の有無があり、「経路がおかしい？」疑惑があり、tracerouteで確認　→遅延が起きている人はなぜかオランダを経由していた
        * 名前解決の結果を確認したところ、東京リージョンのCloudfrontのIPが返ってくるはずが、アムステルダムリージョンのCloudfrontのIPが返ってきた。
    * whoisがなぜか5/31sun 0:11JSTに更新されていた（勿論チーム内でそうした変更作業はしていない）　→セキュリティインシデントとして対応
* 対応
    * 6/1 19:30過ぎ　：レジストラのサポートに「アカウントが乗っ取られた」旨問い合わせ（サポートの時間外だったが対応してもらえた）
        * 「CSIRT協議会の会員一覧からレジストラの方にコンタクトをとりました」 <https://www.nca.gr.jp/member/>
    * 6/1 20:50過ぎ　：復旧
    * この間にコインチェック側でも原因調査をしていたものの、よく分からず。
    * その後の原因調査にて
        * MXレコードが増えていることが発覚
            * 6/1 1:35にGitHubのパスワード変更のメールがきていた
            * GitHubのパスワードリセットが行われた痕跡があった（増えていたMXレコードはこのリセットパスワードを受け取るためのもの）
    * GitHubのアカウント所持者にはパスワードリセットを依頼したり。代わりのドメインを手配したり。
    * JPCERTさんにテイクダウン対応を依頼。
        * Passive DNSなどを利用して調査しました
        * 関係各事業者（含 海外）に英語で調整をかけました
            * ISP「誰がNS建ててるかも分からないし、正当なものかとも言えないから僕らからユーザに何かを言うことはできない」と言われることもあったり。
        * 謎に登録されていた3台は、6/4になり名前が引けないようにしてもらった。
    * プレスリリースは代わりのメールサーバの手配ができてから出した。
    * レジストラより問題を修正した連絡を受けたので、プレスリリース最終報告＆サービス再開
        * **個人的にはここ`レジストラより問題を修正`が知りたいなああああ！！！！！！（大声）**
        * これかな <https://www.onamae.com/news/domain/20200603_1/>
* QA
    * Q. 攻撃者がもし東京リージョン使ってたら？
        * A. どこかで気づけたとは思うけど・・・・・・

---

## C25 なんちゃってCSIRTを抜け出したい - SIM3による成熟度評価 -

* by 杉浦 芳樹(NTTデータ先端技術株式会社 NTT-CERTメンバー / NCA チームトレーニング委員), 小村 誠一(NTTアドバンステクノロジ株式会社 / NCA SIM3実行委員、CSIRT評価モデル検討WG), 原子 拓(日本シーサート協議会(NCA) / 株式会社ラック)
* 「CSIRTの方と話すと、（自分たちの活動について）やっぱり自信なさげな回答をされる方が多いんですよね」
    * 「まず、何を活動の指標とされていますか？」（チームとしての能力や実施量、成熟度で測るなどなど）
* なんちゃってCSIRTって？　→「自分たちの置かれている状況が分かっていないんじゃないでしょうか？」
    * 何も起きないから何もしてない／作ったけど、見直しをしていない、など
    * じゃあ、どう改善すればいいか？
        * 「まず、CSIRTをパーツごとに分解してみましょう」　→形・構成、人材、メンバーが使うツールや環境、どのように活動するか、など
        * 分解したパーツごとに考えてみましょう　：ここでSIM3の登場 <http://opencsirt.org/wp-content/uploads/2019/12/SIM3-mkXVIIIc.pdf>
            * 組織／人材／ツール／プロセスに分けて、レベルが定義されている
            * 全てのレベルが4にならなくてもいい。むしろそうなるとオーバースペック。
            * （とりあえず弊社はCSIRTのミッションを明確に定義したほうがいい）（少なくともいちメンバーである私は認識できていない）
            * レベル3=レビューを経た方法で定義されており、チームとしてノウハウが蓄積された状態で繰り返し実施可能な状態／SIM3内の項目によってはレベル2でとどめておく方がよかったりもします

---

## C26 CSIRT24時、そのとき何が？ Vol.3 - 最新インシデントハンドリング事例 -

* by 近藤 学(株式会社パロンゴ 代表取締役社長), 猪俣 敦夫(大阪大学), 茂岩 祐樹(株式会社ディー・エヌ・エー システム本部セキュリティ部 / NCA ログ分析WG主査), 守屋 英一(明治大学ビジネス情報倫理研究所 / NCA 事例分析WG主査), 原子 拓(日本シーサート協議会(NCA) / 株式会社ラック)
* 事例　：dockerデーモンのオープンポートを狙うソフトウェア
    * 攻撃者は、攻撃対象のマシンにコマンドを叩き、入ってるRedisのslaveにさせる　→syncで.isoを送り込んで攻撃
    * マシンのオーナーはセキュリティチームの方／オーナー「Redisを明確に入れた記憶はない」　→何かのソフトがRedis込みで作られていて、ポートも開いてて認証もかかってない状態だったのでは。
* 事例　：大学CSIRTやってみた
    * やってみるとインシデントが欲しくなる→でも起きてみると家に帰れなくなる→つかれる→人材／予算を増やしてもらうお願いをする→インシデントが欲しくなる、以下略
    * 大学で起きるインシデント　：誤送信はやっぱり多い
        * オンライン講義のURLを当日慌ててToで配信してしまった
        * →学生にとっては「自分がどの授業を受けているかも知られたくない」、個人情報。本省への報告案件となる。
* 以下略