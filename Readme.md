# 概要
ELKStack(Elastic Search + Logstash + Kibana)をDocker Composeで起動するためのサンプルファイルです。docker composeとして起動するだけど、ELKStackを動かすことが可能です。

# 起動方法


### docker-coseの起動

プロジェクトフォルダでdocker-compose upを実行して、docker-composeを起動します。

```
~/elkstack$ docker-compose up -d
[+] Running 3/3
 ⠿ Container elkstack-kibana-1    Started                                                                          2.8s
 ⠿ Container elkstack-logstash-1  Started                                                                          1.9s
 ⠿ Container elkstack-es-1        Started 
```


### Kibanaにアクセス

ブラウザを起動して、ローカルのポート: 5601にアクセスします。

indexを設定することで、5秒間隔でHello from Logstashが記録されるのを確認することができます。

```
input {
  heartbeat {
    interval => 5
    message  => 'Hello from Logstash'
  }
}
```

![kibana](/images/kibana-gpu.png) 