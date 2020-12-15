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



