
補足メモ

---

# インターネットはプロトコルでつながっている

## 前半 - プロトコル

* TCP/IPの話についておすすめ本　：『マスタリングTCP/IP』まずは入門編 <https://www.amazon.co.jp/%E3%83%9E%E3%82%B9%E3%82%BF%E3%83%AA%E3%83%B3%E3%82%B0TCP-IP-%E5%85%A5%E9%96%80%E7%B7%A8-%E7%AC%AC5%E7%89%88-%E7%AB%B9%E4%B8%8B/dp/4274068765>
    * 3Fロッカー横に置いてるので、辞書がわりに都度読みに来てもらってokです。（情報量多めの本なので、たとえば「NATって何？」とかなった時に索引引いてNATの項目だけ見る・・とかいう使い方もok。というか私はそうしてた。）

## 後半 - ルーティング

* MKIの使っているASはAS17673
    * 貰っているIPv4アドレスは以下
        * 150.67.0.0/16　：MKI（全社）
            * MKI（全社）はMKI（DC）のいち顧客
        * 203.223.80.0/22だっけ　：DC内部用
        * 211.19.30.0/22だっけ　：DC顧客用
    * よそのASとの境目にいるルータはcr03.tky2, cr04.tky2, br03.tky2
        * crはトランジットとの接続点、brはIXとの接続点。
        * 他の会社（ISP）では、内部のセグメントや顧客用セグメントを区別するために”プライベートAS”を使い、プライベートASの境目ごとにBGPを喋れるルータを置くこともある。　：うちのDCの規模／構成ならまあ不要

---

# インターネットは物理でつながっている

* 近くで物理層の話が比較的わかるのは箕輪さん、本間さん、保野さんくらいかしら・・建物寄りの話なら志澤さん。社会インフラのネットワーク系の同期繋がりで聞いた方が情報得やすいかもね。
* 「光ファイバをどこまで曲げるとダメになるのか」　：JPIX主催の「ケーブリングセミナー」（今年はまだ案内出てなかった）で体験できます。物理層をまとまって学べる良セミナーなので行ってらっしゃい。
* こないだのJANOGで光ファイバのO-band/C-bandがどうのとか聞いたけど、終始「ふーん」ってなるくらい分からんくて笑った。全然今知らなくていいけどまあこういう世界もあるよってことで。 cf. <https://www.janog.gr.jp/meeting/janog45/application/files/6715/7984/3115/032_100gdci_02-kato.pdf>
* 光ファイバのSC/LCくらいは見分けつくようになるといいね。石渡さんとか連れて1F電算室に落ちてるケーブルとか漁ってみるといいです。

---

# インターネットはコミュニティでつながっている

* これよこれ。インターネット系のコミュニティはweb系とかと比べてなんとなく閉鎖的というか、初心者が居づらい空気があるにはあるものの、「積極的に自ら学ぼうとする人」には優しく教えてくれる人達が多い気はします。あとおっさんばっかりなので、若者というだけで優しくしてもらえます。
* 「自分の”普通”が誰かの”すごい！”かもしれない」
    * 初心者3の頼りない紹介文のやつがわたしですが、意外と票入ってたんですよね。こういうこともあるんだねーへええっと驚いた事例。 <https://www.janog.gr.jp/meeting/janog45/lt_vote>
* そういえば以前、DCのコミュニティ：JADOGで三鷹セコムSCセンター本館あたりにいるセコムさんの方と知り合えたりしました。「優先給油とか実際どうなってんすか？」「我々が周辺給油事業者に直電かけて頑張るんでそこはね・・・！大丈夫です・・！」とか話したりして。おもろい。
* 「意外とみんな急に輪にはいっても気にしない」まじでこれ！！！！！！！！！
    * 「あら、若い人が来てくれましたよ！」「どこの会社さん？お仕事は？」「DNS運用してるのかー頑張るね・・！」みたいな感じで、なんか勝手に話は広がる。