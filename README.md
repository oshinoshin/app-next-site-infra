## 初回実行

1.  ローカル環境にて以下コマンドを実行  
    `cd app-next-site-infra/docker/node`  
    ` docker run -d --name app-react-site node tail -f /dev/null`

2.  コンテナ接続後に React と Next.js をインストール  
    2-1. ローカル環境で以下のコマンドを実施し、コンテナ接続  
    `docker ps -a`  
    `docker exec -it <container_id> /bin/bash`

    2-2. コンテナ内で実行して React と Next.js をインストール

    `cd /app-next-site`  
    `npx create-next-app app-next-site`

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

    2-3. ローカル環境で実行し、コンテナ内に配置したソースをローカル環境へコピーする  
    `docker cp 51a33a10d4e9:/frontend/app-next-site ./`

## 2 回目以降および clone 時は以下の手順を実行

1. 以下の階層構造になるように `git clone` する

```
tree -L 1
.
├── app-next-site
└── app-next-site-infra
```

2. コンテナ起動  
   `make up`

3. ブラウザで以下の URL にアクセスする  
   http://localhost:3000

## コマンド集

-   コンテナ起動  
    `make up`
-   コンテナ停止  
    `make down`
