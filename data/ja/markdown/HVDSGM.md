<div>

|                    |                                                                                                                                                                                                                                                                                                        |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| タイトル           | HVDSGM                                                                                                                                                                                                                                                                                                 |
| 画像               | [<img src="/images/thumb/0/00/Mastodon_logo.png/120px-Mastodon_logo.png" srcset="/images/thumb/0/00/Mastodon_logo.png/180px-Mastodon_logo.png 1.5x, /images/0/00/Mastodon_logo.png 2x" width="120" height="120" alt="Mastodon" />](/%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB:Mastodon_logo.png "Mastodon") |
| 開発者             | [墓場人夜](/%E5%A2%93%E5%A0%B4%E4%BA%BA%E5%A4%9C "墓場人夜")                                                                                                                                                                                                                                           |
| プラットホーム     | Linux (サーバー)、ウェブ (クライアント)                                                                                                                                                                                                                                                                |
| プログラミング言語 | C++                                                                                                                                                                                                                                                                                                    |
| サービス開始日     | 2017年8月                                                                                                                                                                                                                                                                                              |
| ライセンス         | [GNU Affero General Public License](/GNU_Affero_General_Public_License "GNU Affero General Public License")                                                                                                                                                                                            |

  
**HVDSGM**は、[分散SNS](/%E5%88%86%E6%95%A3SNS "分散SNS")。独自のプロトコルを用いるため、他の分散SNSと[連合](/%E9%80%A3%E5%90%88 "連合")を形成することができない。

<div>

<div lang="ja" dir="ltr">

## 目次

</div>

-   [1 名称](#.E5.90.8D.E7.A7.B0)
-   [2 アーキテクチャ](#.E3.82.A2.E3.83.BC.E3.82.AD.E3.83.86.E3.82.AF.E3.83.81.E3.83.A3)
-   [3 サービス](#.E3.82.B5.E3.83.BC.E3.83.93.E3.82.B9)
    -   [3.1 ソーシャルグラフサービス](#.E3.82.BD.E3.83.BC.E3.82.B7.E3.83.A3.E3.83.AB.E3.82.B0.E3.83.A9.E3.83.95.E3.82.B5.E3.83.BC.E3.83.93.E3.82.B9)
    -   [3.2 テキストサービス](#.E3.83.86.E3.82.AD.E3.82.B9.E3.83.88.E3.82.B5.E3.83.BC.E3.83.93.E3.82.B9)
    -   [3.3 マルチメディアサービス](#.E3.83.9E.E3.83.AB.E3.83.81.E3.83.A1.E3.83.87.E3.82.A3.E3.82.A2.E3.82.B5.E3.83.BC.E3.83.93.E3.82.B9)
    -   [3.4 疫病サービス](#.E7.96.AB.E7.97.85.E3.82.B5.E3.83.BC.E3.83.93.E3.82.B9)
-   [4 沿革](#.E6.B2.BF.E9.9D.A9)
-   [5 関連項目](#.E9.96.A2.E9.80.A3.E9.A0.85.E7.9B.AE)
-   [6 脚注](#.E8.84.9A.E6.B3.A8)
-   [7 外部リンク](#.E5.A4.96.E9.83.A8.E3.83.AA.E3.83.B3.E3.82.AF)

</div>

## 名称

名称の由来は**Horizontally and virtically distributed social graph and messaging**の略であるが、アクロニムである**HVDSGM**が正式な名称である。発音はアルファベットそのままの「エッチブイディーエスジーエム」である。

テキストサービス (後述、以下同様) の実装の名称は**Zipgun**、疫病サービスの実装の名称は**Takeyari**である。いずれも手製かつ即席の武器の名称に由来している。

マルチメディアサービスの実装の名称は[素朴ディジタル画像インフラストラクチャー](/%E7%B4%A0%E6%9C%B4%E3%83%87%E3%82%A3%E3%82%B8%E3%82%BF%E3%83%AB%E7%94%BB%E5%83%8F%E3%82%A4%E3%83%B3%E3%83%95%E3%83%A9%E3%82%B9%E3%83%88%E3%83%A9%E3%82%AF%E3%83%81%E3%83%A3%E3%83%BC "素朴ディジタル画像インフラストラクチャー")である。これは、HVDSGMとは独立に開発されていた画像アップローダーを流用したものである。

## アーキテクチャ

[Mastodon](/%E3%83%9E%E3%82%B9%E3%83%88%E3%83%89%E3%83%B3 "マストドン")などの主要な分散SNSが複数の[インスタンス](/%E3%82%A4%E3%83%B3%E3%82%B9%E3%82%BF%E3%83%B3%E3%82%B9 "インスタンス")から構成されるのに対して、HVDSGMは複数の**サービス**が分散SNSを構成する。HVDSGMのサービスとは、機能別に分化したサーバーである。同じ機能を持つ複数のサービスがあってもよい。それぞれのサービスは別の運営者によって運営されていてもよい。ユーザーは複数のサービスを自由に組み合わせて利用することができる。

## サービス

HVDSGMには以下のサービスがある。

### ソーシャルグラフサービス

ユーザーのソーシャルグラフ (フォロー／被フォロー関係) とプロフィールを保持するサービス。任意の静的ウェブサイトにJSONファイルを設置することでソーシャルグラフサービスとして機能する。そのため、専用の実装は存在しない。

### テキストサービス

文字列を送受信し、タイムラインを構成するサービス。実装の名称は**Zipgun**。

### マルチメディアサービス

画像などのメディアを保持するサービス。実装の名称は[素朴ディジタル画像インフラストラクチャー](/%E7%B4%A0%E6%9C%B4%E3%83%87%E3%82%A3%E3%82%B8%E3%82%BF%E3%83%AB%E7%94%BB%E5%83%8F%E3%82%A4%E3%83%B3%E3%83%95%E3%83%A9%E3%82%B9%E3%83%88%E3%83%A9%E3%82%AF%E3%83%81%E3%83%A3%E3%83%BC "素朴ディジタル画像インフラストラクチャー")。

### 疫病サービス

[ミステリーポスト](/%E3%83%9F%E3%82%B9%E3%83%86%E3%83%AA%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88 "ミステリーポスト")を保持するサービス。実装の名称は**Takeyari**。

## 沿革

2017年7月30日、開発を開始。

2017年8月7日、完成。以後は小規模な改良が行われた。

2017年9月2日、第2回分散SNSフォーラム<sup>[\[1\]](#cite_note-1)</sup>の講演で解説された。

2017年12月20日、運用を終了。

## 関連項目

-   [Yayaka19](/Yayaka19 "Yayaka19")

## 脚注

<div>

1.  [↑](#cite_ref-1) <a href="https://distsn.connpass.com/event/61187" rel="nofollow">https://distsn.connpass.com/event/61187</a>

</div>

## 外部リンク

-   <a href="https://github.com/hvdsgm" rel="nofollow">https://github.com/hvdsgm</a>

</div>