# Getting Started

1. 依存モジュールインストール
1. 開発サーバ起動

```sh
npm i

npm run dev
```

[http://localhost:3000](http://localhost:3000)にアクセス

## Next.js の特徴

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

# 環境構築

## 依存モジュールインストール

[Getting Started](#getting-started)参照

## .vscode/settings.json

共通で設定してほしい項目は以下。後はお好きにどうぞ。

```json
{
  // デフォルトのフォーマッタを prettier に設定
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  // ファイル保存時、prettier による自動フォーマット
  "editor.formatOnSave": true,
  // ファイル保存時、ESLint による自動フォーマット
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  },
  "editor.wordWrap": "on",
  "[prisma]": {
    "editor.defaultFormatter": "Prisma.prisma"
  }
}
```

## サーバ起動

```terminal
$ npm run dev

> momoyoshi-next@0.1.0 dev
> NODE_OPTIONS='--inspect' next dev

Debugger listening on ws://127.0.0.1:9229/3dc510a5-5eed-48a9-b8ba-332e9f37849f
For help, see: https://nodejs.org/en/docs/inspector
ready - started server on 0.0.0.0:3000, url: http://localhost:3000
```

## デバッガ起動

- VSCode の「実行とデバッグ」タブ表示
- 「Next.js Client Side Debugger Settings」を選択してデバッグ開始
- 「Next.js Server Side Debugger Settings」を選択してデバッグ開始

コールスタックのペインに、実行中タスクが 2 つあれば OK

## 参考

[【Next.js】 これでできる! VSCode を使ったデバッグ環境構築と基本的なデバッガの使い方](https://qiita.com/dtakkiy/items/056867930e66f3489211#%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E3%82%B5%E3%82%A4%E3%83%89%E3%81%AE%E3%83%87%E3%83%90%E3%83%83%E3%82%AC%E3%81%AE%E8%B5%B7%E5%8B%95)
