# LiffWithSalesforce

### 準備

#### カスタムオブジェクトの作成

##### サークルイベントオブジェクト

* API名：CircleEvent__c

|項目名|API名|形式|
|:--|:--|:--|
|サークルイベント名|Name|テキスト(80)|
|開催日|EventDate__c|日付|

##### サークルイベント出欠オブジェクト

* API名：CircleEventAttendance__c

|項目名|API名|形式|
|:--|:--|:--|
|サークルイベント出欠ID|Name|自動採番　CEA-{0000}|
|サークルイベント|CircleEvent__c|参照関係(サークルイベント)|
|ユーザID|UserId__c|テキスト(255)|
|ユーザ名|UserName__c|テキスト(255)|
|画像URL|ImageUrl__c|テキスト(255)|
|出席する|Attendance__c|チェックボックス|
|出席表示|DisplayAttendance__c|数式(テキスト)|


出席表示の数式
```
if (Attendance__c == true, "出席", "欠席")
```

#### カスタムオブジェクトにデータを入れる
プロファイルで、サークルイベントとサークルイベント出欠オブジェクトの参照。編集権限を付与して、
タブを「常に表示」にしてください。

サークルイベントオブジェクトに、適当な日付とタイトルで、レコードを1件登録してください。

#### コントローラーを設定
開発者コンソールを開いて、
Apexクラス「CircleEventAttendanceController」を作成してください。

ソースコードは、
CircleEventAttendanceController.apxc
の内容を張り付けてください

#### Visualforceページを設定
開発者コンソールを開いて、
Visualforceページ「CircleEventAttendancePage」を作成してください。

ソースコードは、
CircleEventAttendancePage.vfp
の内容を張り付けてください

#### サイトを設定
Salesforceの「設定」⇒「サイト」で新規サイトを作成し、
「CircleEventAttendancePage」を有効なホームページとして設定してください。

サイトの「公開アクセス設定」で表示されるプロファイルに、
CircleEventAttendanceControllerクラスのアクセス権限を付与してください。

サイトの「公開アクセス設定」で表示されるプロファイルに、
「サークルイベント」「サークルイベント出欠」のオブジェクトの参照。編集権限を付与してください。


サイトの表示ラベル、サイトの名前は何でもいいです。
「イベント出欠ページ」「circleEvent」など。
