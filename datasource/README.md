# grafanaのデータソースについて
[公式ドキュメント](https://grafana.com/docs/grafana/latest/datasources/)
#### 1. UIを起動
UIを開きます。
```
http://<ホスト名>:3030
```
![image](https://user-images.githubusercontent.com/91726058/172114323-97e72975-668f-4021-8a5b-92414f5658d2.png)
#### 2. ログイン
初期のusename/paswordはどちらも「admin」です。
新しいpasswordの入力を求められますが、「skip」で問題ありません。
#### 3. データソースを開く
「設定（歯車）」→「data sources」をクリックします。
![image](https://user-images.githubusercontent.com/91726058/172114219-24d02c23-70df-4dcf-af9e-4ca63afc6a42.png)
#### 4. prometheusをデータソースに追加
「add deta source」ボタンを押します。
![image](https://user-images.githubusercontent.com/91726058/172115543-ff33b71d-4c4f-43c0-b291-54b97427d268.png)

「prometheus」を選択します。
![image](https://user-images.githubusercontent.com/91726058/172115869-4a8bbc2e-a66f-4dbf-acbf-8f6e60dcd6f6.png)

「URL」に ```http://localhost:9090``` を入力します
![image](https://user-images.githubusercontent.com/91726058/172116405-83a7f3f0-1135-49a8-ba8f-b6d216e3db46.png)

その他は初期値のまま最下部の「Save & test」ボタンを押します。
![image](https://user-images.githubusercontent.com/91726058/172116630-9e814b9e-30f1-4bd1-8e03-e367083507e8.png)
上記のように「Data source is working」と表示されればOKです。
