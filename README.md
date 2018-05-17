# django-my-project

## db初期設定
`docker-commpose up -d` で構築した後、プロジェクトルートで以下マイグレーション実施

```
docker-compose run web ./manage.py makemigrations
docker-compose run web ./manage.py migrate
docker-compose run web ./manage.py shell -c "from django.contrib.auth.models import User; User.objects.create_superuser('admin', 'admin@localhost', 'admin')"
```

http://localhost:8000
http://localhost:8000/_admin

上記でアクセス確認

