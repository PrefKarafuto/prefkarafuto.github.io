---
title: 外部APIとの連携
permalink: /docs/external-api/
---
## Captcha 
Captchaを使ってBotからの書き込みを遮断できます。システム設定でサイトキーとシークレットキーを設定してください。

### ユーザー認証
ユーザー認証が有効である場合、最初の一回を通常ブラウザから認証して書き込めば、以降一定期間専ブラからでも書き込みが可能になります。投稿時にユーザー認証を求めるメッセージが出た場合、それに従って認証をしてください。掲示板がCaptcha必須に設定されている場合、専ブラからの投稿は出来ません。

### EX0chで使用できるCaptcha
+ [hCaptcha](https://www.hcaptcha.com/)
+ [reCAPTCHA v2](https://www.google.com/recaptcha/about/)
+ [Turnstile](https://www.cloudflare.com/ja-jp/products/turnstile/) 

#### Captchaを有効化してるのに認証しなくても書込み・ログインできる！
+ LWP::Protocol::https  
+ Net::SSLeay  
は入っていますか？モジュール不足やCaptchaそれ自体の構成ミス等でチェックが失敗した場合、無条件でパスするようになっています。

## プロキシチェック

## Imgur