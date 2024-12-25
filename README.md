# 準備

git clone https://github.com/glionsec/bloodhound.git

cd bloodhound

# 起動

docker-compose up

# 注意事項

起動させたあとに初期パスワードが出てくるのでメモするのを忘れないこと

burpと競合するのを避けるため8081番ポートに変更しているので注意

# PlumHoundの実行方法

まずコンテナに入る

```
sudo docker compose exec plumhound /bin/bash
```

コンテナ内でタスクを実行する

```
python3 PlumHound.py -x tasks/default.tasks -s "bolt://graph-db:7687" -p ${NEO4J_SECRET:-bloodhoundcommunityedition}
```
