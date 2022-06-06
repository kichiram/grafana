# grafanaのダッシュボード作成
#### 1. UIを起動
UIを開きます。
```
http://<ホスト名>:3030
```
![image](https://user-images.githubusercontent.com/91726058/172114323-97e72975-668f-4021-8a5b-92414f5658d2.png)
#### 2. ログイン
初期のusename/paswordはどちらも「admin」です。
新しいpasswordの入力を求められますが、「skip」で問題ありません。
#### 3. ダッシュボード作成
「作成（＋）」→「dashboard」をクリックします。
![image](https://user-images.githubusercontent.com/91726058/172120159-b1cd3c92-437d-493a-a5cc-7734f74de322.png)
#### 4. パネルを作成
「Add a new panel」を選択します。

![image](https://user-images.githubusercontent.com/91726058/172120333-b6ecd5da-e091-4452-9b0d-457b64b81680.png)
#### 5. グラフを作成
「Metrics browser」に「node:cpu_usage:irate_5m」を入力します。その他は初期値のまま右上の「Save」ボタンを押します。
![image](https://user-images.githubusercontent.com/91726058/172120644-bd226ae5-fdd3-4463-b6f5-b959d8905034.png)

「Dashboard name」の入力を求められるのでここでは「node info」と入力して「Save」ボタンを押します。
![image](https://user-images.githubusercontent.com/91726058/172121447-6d9f5edc-f15e-4d79-9136-422f70a9864d.png)

下記のように表示されればOKです。
![image](https://user-images.githubusercontent.com/91726058/172121798-832b6a98-11fd-4a3f-950b-7930168f1253.png)
