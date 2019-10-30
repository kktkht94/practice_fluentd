# fluentd test
fluentd勉強用のイメージで、fluentd-uiが起動するようにした。

## 操作

起動

```bash
docker-compose up -d
```

```bash
docker-compose exec fluentd bash
```

fluentd-uiの情報

```
URL: http://localhost:9292
USER: admin
PASS: changeme
```

## コマンド

コマンド

```bash
$ echo 'test' | fluent-cat hoge
```

## やりたいこと
volumeを使ってログのディレクトリを共有しつつ監視する感じ。

## リンク
- [fluent/fluentd - Docker Hub](https://hub.docker.com/r/fluent/fluentd/)
- [fluent/fluentd-docker-image: Docker image for Fluentd](https://github.com/fluent/fluentd-docker-image)