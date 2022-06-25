# ディレクトリ構成について

## .github

action に用いる yml ファイル

## docs

設計に関するメモ

## public

静的ファイル
ビルド時に配置された資産しか Next.js により配信されない

## src

実装に関するファイルを配置

### components

UI 部品
下記どちらも保有する
量が増えたら更にフォルダ階層を分けるか検討

- 共通化して利用できる
- [pages](#pages)に持たせるには大きすぎる故に別出しされた UI 部分

### hooks

React のカスタムフック
特定のコンポーネントに依存する場合、ファイル名称で関連が分かるようにする
例)`pages/invitation.ts`の hook->`hooks/invitation.hook.ts`

なお、hook であることを明示的にするため、ファイル内で宣言される hook 関数名は`useXXXXXX`とする
例)`hooks/invitation.hook.ts`->`useInvitation()`

### models

- [services](#services)が用いるビジネス側オリジナルの型定義
- API やり取りに用いられるデータ型定義
  - そのうち DTO として使うかも
- その他共通的に用いる interface としての型情報も含む

### pages

ファイル名が URL パスとなる、ページの原型

### pages/api

ファイル名が API ルーティングとなる
RESTful 原則を採用するため、オブジェクトごとに HTTP Method で処理内容を判断、コントロールする
API の`handler()`関数では、あくまで API のルーティングの役割であり、ビジネスロジックは[services](#services)が担当する

### repositories

DB など、データ層との接点を持つ
ユニットテスト時に mock 化される場合を意識してコンパクトな役割しか持たせないように

### services

ビジネスロジックを持つ
[repositories](#repositories)で取得したデータを、[models](#models)に定義された型で扱い、加工や受け渡しなどを担当

### styles

CSS 置き場
特定のコンポーネント限定 CSS としたい場合、`.module.css`拡張子とすること
See: <https://nextjs.org/docs/basic-features/built-in-css-support>

~~なお、SCSS が使用できるよう対応済み~~

ライブラリとして`tailwindcss`も利用可能であるため、基本はそちらを使用し、カバーできない部分の CSS を追加する

### utils

汎用的な処理(値の変換など)

## 参考

- [Next.js のディレクトリ構成を考えてみた](https://zenn.dev/mongolyy/articles/01f0a4375edb2e)
- [Nextjs プロジェクトのディレクトリ構成例をさらしてみる](https://qiita.com/kentt/items/c86782b481ec175a57e2)
