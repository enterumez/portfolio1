# soulmates live出演バンド管理アプリ
サークル内でのライブに出演するバンドを管理することができます。
大まかな機能として
- ライブ登録
- メンバー登録
- バンド登録
- バンドごとにメンバーを登録
- ライブごとに出演バンド、出演順、出演時間、メンバーを表示

# Dependency
言語:PHP 7.1.23
データベース
開発環境:MySQL 8.0.15
本番環境:MySQL 5.5.62

# setup
ローカルで動作させるためには、ブランチをdevelopに切り替えてcloneしてください。

`git clone -b develop https://github.com/RinyuDrvo/soul_live_app.git`

mysqlサーバ起動後、
conf/database_confを作成し、
下記のデータベース情報を入力
```
<?php
//データベース設定
$dbServer = 'ホスト名';
$dbUser = 'ユーザー名';
$dbPass = 'パスワード';
$dbName = 'データベース名';
?>
```

# Usage
- ライブ確認(index.php)
    - トップページではどんなライブがあるか確認することができます。
    - ライブ名横の選択ボタンを押すと各ライブに出演するバンド一覧へ移動します
    - ライブメンテナンス画面とメンバーメンテナンス画面へ移動することができます
- ライブメンテナンス(live_maintenance.php)
    - ライブIDとライブ名の一覧を確認できます。
    - ライブ名の右側のボタンでライブを削除することができます。
- ライブ追加(live_insert.php)
    - サークルで開催するライブを追加する事ができます。
        - ライブにはライブIDを設定する必要があります。
            重複するとエラーになるので、既存のライブIDを確認した後追加してさい
            又、下記ルールに従って必ず7文字で入力してください
            例)201901A→2019年１番目のライブのA日程
- メンバーメンテナンス(member_maintenance.php)
    - 登録されているメンバーIDと名前を確認することができます。
    - 名前右側の削除ボタンでメンバーを削除することができます
- メンバー登録(member_insert.php)
    - サークルメンバーを登録することができます。
        - メンバーにはメンバーIDを登録する必要があります。
            重複するとエラーになるので、既存のメンバーIDを確認した後追加して下さい
            又、下記ルールに従って必ず7文字で入力してください
            例)2019001→2019年の1番目に登録した人
- 出演バンド(band_maintenance.php)
    - 選択したライブに出演するバンドが確認できます。
    - 各バンドの右にあるボタンより削除や変更、メンバー追加ができます。
    - 出演バンド追加画面に飛ぶことができます
- バンド登録(band_insert.php)
    - ライブごとに出演するバンドを登録することができます。又、出演順や出演時間を登録できます
        - バンドにはバンドIDを登録する必要があります。
            重複するとエラーになるので既存のバンドIDを確認した後追加して下さい
            又、下記ルールに従って必ず4文字で入力してください
            例）B001→そのライブの登録1番目
- バンド登録情報更新(band_update.php)
    - バンド情報を更新できます。バンドID以外を登録と同じように入力してください
- バンドメンバー結成(formation.php)
    - バンドメンバーを登録されたメンバーから結成することができます。
        追加にはメンバーIDが必要となります

# Authors
RinyuDrvo