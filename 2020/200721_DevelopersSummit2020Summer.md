# Developers Summit 2020 Summer

## 概要

* <https://event.shoeisha.jp/devsumi/20200721#outline>
* developer（開発者／アプリレイヤ）向けイベント

---

## APP Meets NW! 垣根を越えて生きていく入門

### 生田 和正[シスコシステムズ]さん

* ネットワーク（インフラ）とアプリケーションって、垣根ありません？
* 今日はネットワークの技術トレンドについて紹介しに来ました。
    * 「昔からこの業界にいた方はインフラもアプリも一緒にやってたでしょうが、ここ10-15年くらいでは分業：”インフラ屋なのでコード書けません”,”アプリの人間なのでネットワークとか分かりません”→融合というトレンドになってきた印象です。」

* ネットワークプログラマビリティのトレンドについて
    * SDNコントローラ型モデル
        * 各無線APが持ってる情報をAPIで吸い上げ、中央のコントローラで集中管理するもの
        * 「このAPIなんかはけっこうレイヤ高めの人向けに作られてる感じもあるので、アプリの人とかこういうの触ってみたいんじゃないですかね？」
    * ネットワークOSでのAPI標準化と普及
        * ネットワーク機器は、APIなどプログラマブルなインターフェイスを実装するのが当たり前になってきています。
    * ネットワーク装置でのプログラマビリティ機能
        * 「ネットワーク機器の上にアプリケーションをホスト」して、自動化してたりします。
        * tool comand language(cisco)などなど
        * ホストしたアプリケーション／pythonスクリプトを置いたりして、ダイナミックにやることもできるよ
    * IaC, 構成管理ツールの普及
        * AnsibleやTeraformなどの構成管理ツールが普及してきてます。モジュールも充実してきてるよ。

* 人によっては、まだ垣根があるのかもしれないですね。
    * でもネットワークの世界って、意外とプログラマブルな感じに変化してきてるんですよ。
    * ネットワークの人も、pythonと聞いてどきっとしないとか、垣根を越えていく必要が出てきてます。
    * DevNetは15%ネットワーク、85%はgitやbash
    * gartnerのブログによると、「ネットワークエンジニアがAnsibleとかのAPIによるSI構築経験があれば、給料30%上がる」みたいな話もありますしね。

### 円佛 公太郎[プログデンス]さん

* アプリ屋→ネットワーク屋になって感じた違い
    * アプリ屋　：「新しいものをどんどん取り入れる印象」、ネットワーク屋　：「あんまり効率化されてない印象」
        * コミュニケーション、バージョン管理、継続的インテグレーション・・・
        * バージョン管理などされておらず、configはサフィックスを変えて大量に陳列されているだけ
    * 「ネットワーク業界にはまだまだアプリ業界の常識は普及してない。でも逆にこれはチャンスでは？」
        * アプリ業界の常識を持ち込めば、ぐっと生産性が上がるはず。
        * トラフィック情報そのものが本当に宝の山であり、プログラマブルなスキルを活かすシチュエーションはたくさん。
* クラウド時代のネットワーク設定について
    * コマンド（CLIの特定のフレーズ）を覚えて設定　→　REST APIとかを使えばもっと分かりやすくできたりもする。
    * スキルセットの作り方　：「何かひとつのスキルがあれば、という世界でもなくなってきている印象。3軸くらい欲しい。」
* 学習ツールいろいろ紹介
* よくある質問「チュートリアルとかで勉強してみたはいいけど、実際業務にどう生かしたらいいの？」
    * DevNetがその答えなのではないかと思う。
    * 実際のCisco製品とどう連携するのかについても分かるようになってるので。
    * DevNet sandboxで自分の書いたコードを試したりもできるよ

* APPの皆様にお伝えしたいこと「ネットワークは宝の山です。もうAPIとかでプログラマブルに収集して、新しいものを作ったりすることができるようになっているんですよ！！！！！！！！！」

* （ハッシュタグ見てると「DevNet知らなかった」とかけっこうあるように、ほんとに垣根そこそこあるんだなーという実感。）

---

## apt update my-society: シビックテックとCOVID-19

* 関 治之[Code for Japan]さん
* 2月のデブサミ資料 <https://www.slideshare.net/codeforjapan/code-for-japan-227910934>
    * cf. Code for Japan <https://www.code4japan.org/>

* みなさんコロナ禍の中でどう過ごしていましたか？私はシビックテックの活動してました。　：都の委託事業として都内の最新感染動向のあのページを作りました。
    * 「不安を煽るいろんなニュースが流れていたので、いったん雑音をシャットアウトして、自分にできることをしよう、コードを書こう。と考えました。」 cf. <https://twitter.com/hal_sk/status/1233902877069869056>
    * これまでの行政のサイトと大きく違うのは「GitHubでオープンソース化したところ」です。
    * そしたら世界中からcontributeがありました・・！また、全都道府県にも波及しました！
    * 民間の支援情報を集約して公開するページ／コロナ禍を乗り切る様々なアイデア（企業活動・働き方, etc.）を募集するページも作ったりしました。
        * パブリックコメントだと「送りっぱなし」になってしまうので。
    * 各地域のcode for xxxも、テイクアウトマップ作ったりしてました。
    * などなどなど、こういう危機の時にはシビックテックが活発になる。

* 「がしかし、そういう時にヒットを打つには普段からの素振りが必要です。」
    * 実際、都のコロナ対策サイト開発には以前やってた紙マップPJ<https://kamimap.com/>での経験やそこでのメンバーとのつながりが多いに役立った。
    * code for japanのslack参加リンク <https://www.code4japan.org/activity/community>

* OSSに対する日本国内の理解があまり進んでいないのも現状。
    * それでこういう記事が出てくる
        * <https://visual-shift.jp/19350/>
        * <https://employment.en-japan.com/engineerhub/entry/2020/05/19/103000>
    * たとえばCOCOAについては、開発したOSSチーム→運用チームへの引継ぎがうまいこといってなかったのでは、など。 <https://note.com/hal_sk/n/ne5d695d8ad2a>
    * このあたりも、「エンジニアが行政と対話するのを面倒くさがってきたからなのでは。」
        * **なんか、普通の働き方にも通ずるものがあるなあ・・**

* 「自分自身の技術を会社のためだけに使うのもったいなくないですか？隙間時間でもいいよ、社会のためにも使ってみましょうよ！面白い人にもたくさん出会えるよ！！」

* めちゃめちゃ同意な会場コメント　：**「関 治之: 協力しよう、と思っていただいただけでありがたいです。　こういったコメント頂けると、次に繋がると思った。これはチームでも、業務でも同じな気がする。少しの挑戦に対して、しっかり感謝に繋がると、またやろうって思える。」** <https://twitter.com/JuKoA453/status/1285433171517992962>

---

## Life of a packet: Google Cloud ネットワークのセキュリティ

* 森永 大志[グーグル・クラウド・ジャパン]さん
* 「今日はパケットの気持ちになってください」
    * というより実際はGCPの機能紹介だった感はある

* GFE(Google Front End)　：Googleのネットワークの入口
    * ここのセキュリティ設計が一番難しい＝Googleが関与できない要素がたくさん
    * 世界中に配置しているエッジポップからGoogleの各リージョンに向かう
    * クライアント～GFE間のデータ暗号化は、TLSでやってます。
* GFEに入ったあと、ロードバランシング／cloud armourへ。
    * Global load balancing　：anycastでIPが割り振られている。
    * →grobal fowarding ruleにもとづき、target proxyに投げる
    * →backend service　→managed instance groupに投げる／firewall ruleと連携
* （新機能紹介）serverless network endpoint group
    * GCPのサーバーレス系サービスの前段に置けるLB
    * 今までもスケールアウトはできたが、くわえてglobalなanycast IPを使えたり、コンテンツベースルーティングが使えたりするようになった。
* Google Cloud Armor（DoS対策・WAF機能）
    * Googleのエッジポップにも実装されている
    * LBにCloud Armorを当てて有効化して使う
* VPCネットワークのセキュリティについて
    * firewall ruleについて
        * リソースにつけたタグに対するrule
        * **VPCごとに同じrule作らなくていいの良いね**
    * プライベートアクセスについて
        * Googleネットワーク内のプライベートIPでGoogle API（orをかませてほぼ全てのGCPサービス）と通信可能
    * firewall ruleロギングについて
        * サンプリングせず全データをとる
    * packet mirroring
        * 検査用に他インスタンスにトラフィックをコピーして転送
* APIサービスへのアクセス
    * VPC service controlsについて
        * VPCの設定だけでは防ぎきれない情報流出例
            * IAMポリシーの設定ミスによる意図しないread action
            * クレデンシャル漏れ
            * 内部犯によるデータ持ち出し
            * 他のGoogle APIへの意図しないデータ転送
        * これらを防ぐための機能
            * 同じ目的のリソース群に共通してかけられる境界線。境界をまたぐデータの移動アクションが発生したら、IAMとは別チェックが走る。
* （資料の全体図めっちゃ良いな）