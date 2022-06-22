#ゴミ分別情報検索WEBアプリ


#概要
自治体のオープンデータ（ゴミ分別情報）を活用し、分別情報の検索と詳細情報の表示ができるWEBサイトを作成しました。
本番サイトはhttp://kawasaki-rub.comにて公開しています。
フロントエンドはNuxt.js、バックエンドはRuby on Rails(APIモード)で作成しています。
docker-composeを活用し、dbコンテナ(postgresql)、frontコンテナ(Nuxt.js)、apiコンテナ(Rails)から構成しています。
詳細は開発環境用のdocker-compose.yml(sortapp配下のdocker-compose.dev.yml)をご確認ください。


#詳細
1. dbコンテナ
   docker-hubのpostgresのイメージから作成しています。

2. apiコンテナ
   apiフォルダ直下のDockerfileからビルドしたイメージより構築しています。
   現時点では、以下の２つの機能を持っています
　　①指定されたキーワードを含む分別情報の検索
　　　→類似語を含めるか含めないかを制御できます
　　②指定した分別情報のキーワード表示

3. frontコンテナ
   frontフォルダ直下のDockerfileからビルドしたイメージより構築しています。
   BootstrapVue及びCSSよりデザインしています。
   レスポンシブ対応も実施済みです。


#補足
ブランチは主にmasterとdevelopで使い分けています。
developが開発用でリリースできる状態になったものをmasterにマージしています。
