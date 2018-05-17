# django-my-project

## 環境
| 項目 | Version |
|:---:|:---:|
|docker|18.03.1-ce|
|docker-compose|1.21.1, build 5a3f1a|
|python|3.6.5|
|django|2.0.5|
|Mysql|5.7.22|
|nginx|1.13.12|
|PyMySQL|0.8.1|
|nWSGI|2.0.17|

## db初期設定
`docker-compose up -d` で構築した後、プロジェクトルートで以下マイグレーション実施

```
docker-compose run web ./manage.py makemigrations
docker-compose run web ./manage.py migrate
docker-compose run web ./manage.py shell -c "from django.contrib.auth.models import User; User.objects.create_superuser('admin', 'admin@localhost', 'admin')"
```

http://localhost:8000

http://localhost:8000/_admin

上記でアクセス確認

