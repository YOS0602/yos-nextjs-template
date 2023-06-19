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

> yos-nextjs-template@0.1.0 dev
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

# 依存ライブラリのアップデートについて

## 最新バージョンを確認

```terminal
% npm outdated

Package                           Current   Wanted   Latest  Location                                       Depended by
@testing-library/jest-dom          5.16.4   5.16.5   5.16.5  node_modules/@testing-library/jest-dom         yos-nextjs-template
@testing-library/react             13.3.0   13.4.0   13.4.0  node_modules/@testing-library/react            yos-nextjs-template
@types/node                        18.0.0   18.0.0  18.7.23  node_modules/@types/node                       yos-nextjs-template
@types/react                      18.0.14  18.0.14  18.0.21  node_modules/@types/react                      yos-nextjs-template
@types/react-dom                   18.0.5   18.0.5   18.0.6  node_modules/@types/react-dom                  yos-nextjs-template
@typescript-eslint/eslint-plugin   5.28.0   5.38.1   5.38.1  node_modules/@typescript-eslint/eslint-plugin  yos-nextjs-template
@typescript-eslint/parser          5.28.0   5.38.1   5.38.1  node_modules/@typescript-eslint/parser         yos-nextjs-template
autoprefixer                       10.4.7  10.4.12  10.4.12  node_modules/autoprefixer                      yos-nextjs-template
eslint                             8.18.0   8.18.0   8.24.0  node_modules/eslint                            yos-nextjs-template
eslint-config-next                 12.1.6   12.1.6   12.3.1  node_modules/eslint-config-next                yos-nextjs-template
jest                               28.1.1   28.1.3   29.1.2  node_modules/jest                              yos-nextjs-template
jest-environment-jsdom             28.1.1   28.1.3   29.1.2  node_modules/jest-environment-jsdom            yos-nextjs-template
next                               12.1.6   12.1.6   12.3.1  node_modules/next                              yos-nextjs-template
postcss                            8.4.14   8.4.17   8.4.17  node_modules/postcss                           yos-nextjs-template
tailwindcss                         3.1.3    3.1.8    3.1.8  node_modules/tailwindcss                       yos-nextjs-template
typescript                          4.7.4    4.7.4    4.8.4  node_modules/typescript                        yos-nextjs-template
```

## マイナーバージョンのアップデート

```terminal
npm update
```

ただし、`package.json`において`~`や`^`指定があるバージョンに関しては、その枠を越えないようにしかアップデートされない模様

参照: [package.json内のバージョン番号の書き方](https://overworker.hatenablog.jp/entry/2021/07/10/000535)

## ライブラリのアップデート

### `npm-check-updates`のグローバルインストール

```terminal
% npm i -g npm-check-updates

# マイナーバージョンのアップデートに止める場合
% ncu -u --target minor

# メジャーバージョンもアップデートする場合
% ncu -u
```

## 参考

- [npmで管理しているライブラリのバージョンアップ手順まとめ](https://zenn.dev/yoshii0110/articles/820187fd237b44)
- [【npm】パッケージのupdate方法を紹介します](https://www.fenet.jp/infla/column/technology/%E3%80%90npm%E3%80%91%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%AEupdate%E6%96%B9%E6%B3%95%E3%82%92%E7%B4%B9%E4%BB%8B%E3%81%97%E3%81%BE%E3%81%99/)
- [「npm audit」って何？って時に少し調べた時のノート](https://overworker.hatenablog.jp/entry/2020/10/18/234904)
