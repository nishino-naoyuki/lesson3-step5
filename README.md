# 【Level3-5】

## テーマ
既存プログラムを参考に、CRUD機能が作成できること
ページ遷移とバリデーションの仕組みが理解できること
templateへの記載ができるようになること

## 演習課題の準備（開発環境について）
* この演習では、Codespacesと呼ばれるサービスを使って開発を行います。
* ブラウザ上で動作する開発環境です、インストール不要で使う事ができます。
* レベル0で実施した[手順](/Codespacesの実行手順.md)を参照して、演習課題の準備をしましょう。

## 演習内容
lessonを参考に実績削除機能を作成しましょう。

## 演習内容詳細
実績削除機能を作成しましょう。  
実績管理画面のゴミ箱ボタンを押すことで機能するようにしましょう。
![image](https://user-images.githubusercontent.com/32722128/191274872-9b01043f-f750-415a-92b1-2612bfea5a08.png)
![image](https://user-images.githubusercontent.com/32722128/191274979-f519ce30-e58d-417b-a99c-e7600494aec2.png)
以下の順序で実装を行ってください。

1. `id`指定で実績を削除するために`ArchievementDao`クラスに`deleteArchievement`メソッドを追加してください。
2. 今回追加したDAOクラスのメソッドを使用するため`ArchievementService`クラスに`deleteArchievement`メソッドを追加してください。
3. `ArchievementController`クラスに、削除のリクエストを処理する`delete`メソッドを追加してください。


それぞれに対応する、授業管理機能(Lesson)のファイルを参考に作成してください。

|Archievement|Lesson|
|---|---|
|ArchievementController|LessonController|
|ArchievementService|LessonService|
|ArchievementForm|LessonForm|
|Archievement|Lesson|
|ArchievementDao|LessonDao|

## 1.`ArchievementDao`クラスに`deleteArchievement`メソッドを追加
`JdbcTemplate`クラスの`update`メソッドを使用して以下のSQL文を実行するようにしてください。  
先ほどの演習で作成した、`updateArchievement`メソッドなどを参考に作成してみましょう。
```
DELETE FROM ARCHIEVEMENT WHERE id = ?
```
戻り値として、実行されたSQL文が影響を与えた行数(削除件数)を返すようにしてください。 

## 2.`ArchievementService`クラスに`delete`メソッドを追加
`ArchievementDao`クラスの`deleteArchievement`メソッドを呼び出し、`id`指定で削除を行うようにしてください。  
戻り値として0が返された場合は、DELETEの処理が正常に完了してませんので、`NotDeleteException`クラスの例外を投げるようにしてください。
先ほどの演習で作成した、`updateArchievement`メソッドなどを参考に作成してみましょう。  

## 3. `ArchievementController`クラスに、削除処理を行うための、`delete`メソッドを追加
パス`/detail/{id}`に対して送信されたGETリクエストを処理するようにしてください。
先ほどの演習で作成した`detail`メソッドなどを参考に作成してみましょう。
処理後は、`/archievemen`のパスに対してリダイレクトを行うようにしてください。

## 課題の提出
* 課題の提出は[課題提出の操作](/課題の提出手順.md)のコミット・プッシュ・プルリクエストを実施しましょう。

