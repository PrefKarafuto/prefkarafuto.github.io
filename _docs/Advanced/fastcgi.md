---
title: FastCGI
permalink: /docs/fastcgi/
---
## 導入について
大量の書き込みが予想される掲示板では、FastCGIの導入を検討してください。  
  
## サーバー側の設定（Apache）
必要に応じて、公式レポジトリ  
https://httpd.apache.org/download.cgi#mod_fcgid  
からFastCGIモジュールをダウンロードし、サーバーの公式ドキュメントに沿って各種設定を行ってください。  
   
  
設定例  
```apache
<Files "bbs.cgi">
AddHandler fcgid-script .cgi
</Files>
```
※.cgiの拡張子を変更せずにFastCGIとして動作するように設定してください。 

## Perl側の設定
FCGIモジュールが必要です。無い場合はCPANからインストールしてください。  
https://metacpan.org/pod/FCGI
  
以上の設定が正しく行われていれば、bbs.cgiがFastCGIとして動作します。  
ただし、外部への問い合わせを行う機能（Captcha,DNSBL,ProxyChecker等）が有効になっている場合、実行速度はAPIレイテンシに依存します。  
## 注意
必ず動作試験を行い、動作に問題がないことを確認した上で本番環境で有効化してください。