# local-proxy
Make a local-proxy in use nginx-proxy by Docker.


#### mkcertをインストール
```
$ brew install mkcert
$ brew install nss
```

#### 認証ファイルの生成
```
$ mkcert -install
$ mkcert "*.local.localhost"
```

生成した認証ファイルをリネームしてcertsフォルダに移動させます。
```
mv _wildcard.local.localhost.pem ./certs/_wildcard.local.localhost.crt
mv _wildcard.local.localhost-key.pem ./certs/_wildcard.local.localhost.key
```


#### Proxyを有効にする

```
$ docker-compose up -d
```

https://xxx.local.localhost でアクセス可能になります。