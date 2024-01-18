# 開発環境・検証環境・本番環境

## ドメインを分ける・分けない

開発と本番を同一ドメインにした場合の下記デメリットを解決する為、当面<font color="Red">ドメインを分ける</font>

* ポータルの設定やkintone全体カスタマイズの環境分けができないため、これらの動作検証ができない。
* JavaScirptカスタマイズを適用するには、本番ドメインのkintoneシステム管理権限が必要。
* 同ドメイン内では同じ(1つの)プラグインIDでプラグインの実装が共通となり、プラグインのバージョンアップ版を開発すると本番アプリに適用されてしまうため、プラグインIDを分ける必要がある。
* 既製のプラグインの場合はIDを分けることができないため、同ドメイン内では動作検証できない。
* ユーザーや組織情報が共通のため、動作検証時に本番のユーザーへ通知や作業者の割り当てが行われるリスクがある。
* 開発アプリにデータ移行テストなどの目的で大量のデータを取り込む場合、アクセス権設定に関わる変更を行った際にアクセス権の事前評価に時間がかかり、その間同ドメイン内の本番アプリの変更が不可となる。

![image](https://github.com/ShopChannelIT/Vendor-Potal-Systme/assets/88366591/403a7429-a7b3-48d9-907c-802af8e9703d)

[kintone開発環境の考え方](https://kintone.cybozu.co.jp/kintone-signpost/guide/development_environment.html)


# 配備

* プラグインサービス　[gasuku deproit](https://deploit.gusuku.io/?_gl=1*1x1k8ey*_ga*MTQzMjgxOTQzNC4xNzA1MDM2MzE2*_ga_0703L2JJFB*MTcwNTU1ODE0OS4xLjAuMTcwNTU1ODE0OS4wLjAuMA..)
* 本番環境変更権限は、特定のメンバーへ制限する
* 本番環境変更する場合、Kintone本番環境の『本番環境変更申請アプリ』を利用する



# 各管理者

*各管理者は、下記のとおり運用する。[各管理者の詳細説明](https://jp.cybozu.help/k/ja/admin/permission_admin/admin_type.html#permission_admin_permissions_concept_20)

| № |  | 開発ドメイン | 本番ドメイン |
| - | - | - | - |
| 1 | cybozu.com共通管理者 | 経営企画部/IT本部 | 経営企画部/IT本部 |
| 2 | サイボウズドットコム ストア管理者 | 経営企画部/IT本部 | 経営企画部/IT本部 |
| 3 | システム管理者 | 経営企画部/IT本部 | 経営企画部/IT本部 |
| 4 | アプリ管理者 | JSC従業員のうちアプリ開発するメンバー | JSC従業員のうち本番環境変更権限付与者（数名） |
| 5 | スペース管理者 | JSC従業員のうちアプリ開発するメンバー | JSC従業員のうち本番環境変更権限付与者（数名） |


# メンテナンス中画面

* kintone定期メンテナンス中のログインさせない・ログイン中ユーザーへの連絡を知らせる案内やメンテナンス画面の検討

