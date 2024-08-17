# sqldef-d1-test#

## wrangler login
https://zenn.dev/frog/articles/f77b80a0d78497

```
npm install
npm run dev
```

```
npm run deploy
```

```shell
$ npx wrangler d1 execute sqldef-d1-test --local --file schema.sql
# ローカルでのデータベースのパスを指定。どういう規則でこのファイル名になっているのか不明
$ DATABASE_URL=.wrangler/state/v3/d1/miniflare-D1DatabaseObject/05a8b7a56daafbba43ce15659636fddb73197bd6a7870857a2de1c0644138e6f.sqlite npx kysely-codegen

> npx
> kysely-codegen

• Loaded environment variables from .env file.
• No dialect specified. Assuming 'sqlite'.
• Introspecting database...
✓ Introspected 3 tables and generated ./node_modules/kysely-codegen/dist/db.d.ts in 33ms.
$ cat ./node_modules/kysely-codegen/dist/db.d.ts    
export interface _CfKV {
  key: string;
  value: Buffer | null;
}

export interface Posts {
  content: string;
  id: string | null;
  title: string;
  user_id: number;
}

export interface Users {
  id: string | null;
  nickname: string | null;
  password: string;
  username: string;
}

export interface DB {
  _cf_KV: _CfKV;
  posts: Posts;
  users: Users;
}
```
