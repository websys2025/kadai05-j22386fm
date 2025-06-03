## 外部APIの呼び出しのミニレポート
### Q3-1. 郵便番号APIについて説明せよ。
* エンドポイントと機能
  * <b>エンドポイント</b>：`https://zipcloud.ibsnet.co.jp/api/search?zipcode=2640024 (※郵便番号が2640024の場合)`
  * <b>機能</b>：郵便番号を入力すると、都道府県名コード、都道府県名、市区町村名、町域名とそれぞれのカナ表示が出力される。
* リクエストとレスポンスのフォーマット
  * <b>リクエスト</b><br>HTTPメソッド: GET<br>
クエリパラメータ：zipcode: 検索したい郵便番号
  * <b>レスポンス</b><br>都道府県コード: ${address.prefcode}<br>
                　都道府県名　: ${address.address1}<br>
                　市区町村名　: ${address.address2}<br>
                　　町域名　　: ${address.address3}<br>
                都道府県名カナ: ${address.kana1}<br>
                市区町村名カナ: ${address.kana2}<br>
                　町域名カナ　: ${address.kana3}

---
### Q3-2. 各自で調査したAPIについて説明せよ。
* APIの名称と参照URL
  * APIの名称：NUMBERSAPI　URL：http://numbersapi.com/#5
* エンドポイントと機能
  * <b>エンドポイント</b>： `http://numbersapi.com/42/trivia (※数字 42 のトリビアを取得する場合)`
  * <b>機能</b>：数字に対してのトリビアを表示する。
* リクエストとレスポンスのフォーマット
  * <b>リクエスト</b><br>HTTPメソッド: GET<br>
`URL構造` http://numbersapi.com/{number}/{type}<br>
    `{number}` フォームに入力された数字が入る。APIの仕様では、具体的な数字の他に random（ランダムな数字）なども指定可能だが、今回はトリビアのみ表示する。<br>
    `{type}` 情報の種類を指定する。今回は `trivia` で固定している。<br> APIの仕様では、他に `math`（数学的なトリビア）、`date`（日付に関するトリビア）、`year`（年に関するトリビア）などが利用可能。
  * <b>レスポンス</b>：42 is the number of little squares forming the border of a standard Scrabble board.
---
### Q3-3. 感想
* 今回の課題で苦労したこと
  * Kadai5_2.htmlの出力結果にマーカーを引く処理を実装する処理が上手くいかずに時間がかかった。 \
  郵便番号APIで、どこに都道府県や町域の情報が入っているか分からず、見つけるのに苦労した。 \
  また、見つけた後もどの配列にどのような形式で入っているかが分からず、取得するのが大変だった。
* 演習を通して理解できたこと
  * APIでの情報の取得の仕方
* Web APIの利便性や課題など
  * ECサイトでの住所の自動入力にも使用されていると知って非常に便利だと感じた。\
  また、自分が普段使っている機能の仕組みが分かって楽しかった。\
APIは非常に便利な反面、セキュリティリスクがあるのが課題。
