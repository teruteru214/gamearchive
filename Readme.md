<img src="./assets/introduction.png">

GameArchiveは、ゲームエンターテイメントをより管理しやすくするための一体型データベースサービスです。

ユーザーはゲームの状況に応じて（例：クリア、プレイ中、積みゲー）、様々なゲーム情報を取得して保存することができます。取得したゲームは、画像、タイトル、評価値、ジャンル、プラットフォーム、外部サイトへのURLなど、多彩なデータとともに管理されます。また積みゲー防止のために取得した積みゲーのプレイを促す通知を公式チャンネルから定期的に受け取ることができます。

▼**サービス URL**

https://gamearchiveapp.com/

▼**告知ツイート**

https://twitter.com/teruteru1237/status/1710495531330592973

▼**紹介記事**

https://qiita.com/teruteru214/items/3520e2e67d3ca9b39749

<br>

---

![](https://img.shields.io/badge/Ruby-v3.1.2-red)
![](https://img.shields.io/badge/Rails-v6.1.7-red)
![](https://img.shields.io/badge/React-v18.2.0-blue)
![](https://img.shields.io/badge/TypeScript-v4.6.4-blue)
![](https://img.shields.io/badge/Mantine-v6.0.13-informational)
![](https://img.shields.io/badge/TailwindCSS-v3.3.2-9cf)

<br>

# サービス概要と使い方
GameArchiveはゲームをプレイ状況に合わせて取得して、管理するアプリです。ほとんどの機能はログインすることによって使える機能となっています。

## ①ゲーム取得
1.ゲームを検索します
2.ゲームを選んで、取得ボタンを押します。(ログインユーザーのみ)
3.プレイ状況(積みゲー、プレイ中、クリア)を選んで、実際にゲームを取得します(ログインユーザーのみ)
![ezgif.com-gif-maker (3).gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/1516027/ca78c62d-23a4-12fe-0ad2-b7d9d9f9e24a.gif)
取得されるゲームはIGDBAPIから取得されます。またさらにゲームの詳細を知りたい方のために、画像や詳細ボタンをクリックすればIGDBに遷移して、細かいゲーム情報を見ることができます。

## ②ゲームマネジメント
マネジメントページでは取得ゲームを用いてさまざまな管理ができます。ログインが必要です。
![ezgif.com-video-to-gif (4).gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/1516027/a058f68c-06fb-9e5e-55d6-8aa3abf8e507.gif)
- ゲームのプレイ状況の変更
- ゲームのお気に入り登録
- ゲームの削除
- ゲーム評価値による並び替え
- ゲームジャンルやプラットフォームによる絞り込み
これらの多種多様な管理が可能です。
## ③積みゲー通知機能
ログインしてLINEの友達登録をしたユーザーのみ使用可能です。
また積みゲー通知には積みゲー登録のゲームが必要です。
<table>
  <tr>
    <td style="background-color: white; width: 66%;">
    　　　　　<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/1516027/28b6c92a-abc2-11f9-69e0-9ef29be89fa3.gif" style="background-color: #C0C0C0;">
    </td>
    <td style="background-color: white; width: 33%;">
      <img src="https://i.gyazo.com/74982440cd853d77a56ddccf52a7f59e.png" style="background-color: #C0C0C0;">
    </td>
  </tr>
  <tr>
    <td style="background-color: white; 　width: 66%;">
      通知間隔を入力して、定期的に積みゲープレイを促す通知を送ることができます。(10と入力したら、10日ごとに通知が送られるようになります)
    </td>
    </td>
    <td style="background-color: white; width: 33%;">
      18時ごろに積みゲーが通知されます(選ばれる積みゲーはランダムです)
    </td>
  </tr>
</table>



---

<br>

## 主な使用技術

### フロントエンド

- [React](https://ja.reactjs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [TailwindCSS](https://tailwindcss.com/)
- [Mantine](https://mantine.dev/)

### バックエンド

- [Ruby on Rails（API モード）](https://rubyonrails.org/)

### インフラ

- [Fly.io](https://fly.io/)
- [AWS](https://aws.amazon.com/jp)
  - [Route53](https://aws.amazon.com/jp/route53/)
  - [CloudFront](https://aws.amazon.com/jp/cloudfront/)
  - [S3](https://aws.amazon.com/jp/s3/)
  - [Certificate Manager](https://aws.amazon.com/jp/certificate-manager/)
  - [Lambda@Edge](https://aws.amazon.com/jp/lambda/edge/)

### CI/CD

- [GitHub Actions](https://docs.github.com/ja/actions)

※フロント側は husky&lint-staged を用いて pre-commit 時に ESLint、Prettier を実行してコードの品質を保っています

### 環境構築

- [Docker](https://www.docker.com/)
- [docker-compose](https://docs.docker.jp/compose/toc.html)
- [Vite](https://ja.vitejs.dev/)

### 外部サービス

- [Firebase Authentication](https://firebase.google.com/docs/auth?hl=ja)
- [IGDB API](https://api-docs.igdb.com/#getting-started)
- [Cloud Translation API](https://cloud.google.com/translate/docs/overview?hl=ja)
- [LIFF](https://developers.line.biz/ja/docs/liff/overview/)
- [LINE Messaging API](https://developers.line.biz/ja/docs/messaging-api/overview/)

<br>

---

<br>

## インフラ構成図

[![Image from Gyazo](https://i.gyazo.com/871615fc58210a41e5aa2b03c60a021f.png)](https://gyazo.com/871615fc58210a41e5aa2b03c60a021f)

<br>

## ER 図

[![Image from Gyazo](https://i.gyazo.com/45bb8f1d9f9573667905c06496319a68.png)](https://gyazo.com/45bb8f1d9f9573667905c06496319a68)

<br>

## 画面遷移図

[Figma](https://www.figma.com/file/Q7spu5GNfKmQ4yPmKwGMDF/gamer_achirve?type=design&node-id=0-1&mode=design&t=wLfMSytfvp6mbMJh-0)

<br>

## コンポーネント設計
[Notion](https://teruteru214.notion.site/GameArchive-5c347f28f31649fb8f9f15d0afc81621?pvs=4)
