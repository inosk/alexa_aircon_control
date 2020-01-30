# アレクサ、エアコンを付けて

を実現するlambda functionです。  
alex -> lambda -> ifttt(Webhook) -> irkit という経路で信号を送ります。

# デプロイ方法

github actinoを使っています。  
masterにpushするだけで自動デプロイします。

# 秘密情報の管理

github actionでつかうAWSのcredentialはgithub secretsで、  
lambdaの中で使うiftttのキーはAWS System Mangerのパラメータストアを使っています。

github secretsには以下のパラメータを設定してください。

- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY

AWS System Managerのパラメータストアには以下を設定してください。

- ifttt_key
  - iftttのAPIコールに必要な鍵文字列
- ifttt_aircon_on
  - airconをつけるWebhookの名前
- ifttt_aircon_off
  - airconを消すWebhookの名前

