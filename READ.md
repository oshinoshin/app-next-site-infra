## 初回実行
### ローカル環境に低下を実行
cd infrastructure/docker/node
docker run -d --name app-react-site node tail -f /dev/null

### コンテナ接続後にReactをインストール

docker ps -a
docker exec -it <container_id> /bin/bash

コンテナ内で実行
cd /frontend
npx create-next-app app-next-site
```
Ok to proceed? (y) y

✔ Would you like to use TypeScript? … No / Yes
✔ Would you like to use ESLint? … No / Yes
✔ Would you like to use Tailwind CSS? … No / Yes
✔ Would you like your code inside a `src/` directory? … No / Yes
✔ Would you like to use App Router? (recommended) … No / Yes
✔ Would you like to use Turbopack for `next dev`? … No / Yes
✔ Would you like to customize the import alias (`@/*` by default)? … No / Yes
Creating a new Next.js app in /frontend/app-next-site.
```

ローカル環境で実行
docker cp 51a33a10d4e9:/frontend/app-next-site ./


## 2回目以降およびclone時は以下の手順を実行
git cloneする

make up

