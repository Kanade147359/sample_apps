[![Railsチュートリアル_バナー画像](http://yasslab.jp/img/header-railstutorial.png)](https://railstutorial.jp/)

# Rails チュートリアル sample_app コード集

[Railsチュートリアル](https://railstutorial.jp/)の各章が終わった状態を集めたリポジトリです。   

『Railsチュートリアルって何？』という方は[公式YouTubeチャンネル](https://www.youtube.com/channel/UCgSPCgA1ksSPKg1Jp99EEFw)をご参照ください :tv: :sparkles: 

<a href="https://www.youtube.com/channel/UCgSPCgA1ksSPKg1Jp99EEFw"><img src="https://i.gyazo.com/b1438c5a2a9174c7c9c0714287a72761.jpg" width="500px"></a>

Sample App の開発途中でエラーの原因がどうしても分からないときや、[Railsチュートリアル解説動画](https://railstutorial.jp/screencast)を視聴するときなどにご活用ください。（解説動画は[お試し視聴](https://railstutorial.jp/trial)もできます）

<a href="https://railstutorial.jp/trial"><img src="https://i.gyazo.com/aa8aab4e0428dee5ae91d236dcba5e8b.png" width="500px"></a>

<br>

## :open_file_folder: 各章とディレクトリ名の対応関係

対応しているRailsのバージョン毎にディレクトリを分けております。具体的な対応関係は次のとおりです。

- [Rails 7.0 対応](https://github.com/yasslab/sample_apps/tree/main/7_0) (第7版)
- [Rails 6.1 対応](https://github.com/yasslab/sample_apps/tree/main/6_1) (第6版)
- [Rails 6.0 対応](https://github.com/yasslab/sample_apps/tree/main/6_0) (第6版)
- [Rails 5.1 対応](https://github.com/yasslab/sample_apps/tree/main/5_1) (第4版)
- [Rails 5.0 対応](https://github.com/yasslab/sample_apps/tree/main/5_0) (第4版)
- [Rails 4.2 対応](https://github.com/yasslab/sample_apps/tree/main/4_2) (第3版)
- [Rails 4.0 対応](https://github.com/yasslab/sample_apps/tree/main/4_0) (第2版)

上記の各ディレクトリの中に **各章が終わった状態の** `sample_app` を置いています。例えば `6_1` ディレクトリの場合は、次のようになります。

- `ch01`: 第1章が終わった状態
- `ch02`: 第2章が終わった状態
- `ch03`: 第3章が終わった状態
- `ch04`: 第4章が終わった状態
- `ch05`: 第5章が終わった状態
- `ch06`: 第6章が終わった状態
- `ch07`: 第7章が終わった状態
- `ch08`: 第8章が終わった状態
- `ch09`: 第9章が終わった状態
- `ch10`: 第10章が終わった状態
- `ch11`: 第11章が終わった状態
- `ch12`: 第12章が終わった状態
- `ch13`: 第13章が終わった状態
- `ch14`: 第14章が終わった状態

なお、各章の[演習](https://railstutorial.jp/chapters/beginning#sec-exercises_rails_server)の結果や、[高度なセットアップ](https://railstutorial.jp/chapters/static_pages#sec-advanced_testing_setup)などは反映されておりません。

またオマケとして、完走者向けコンテンツ集「[読み物ガイド](https://railstutorial.jp/reading_guide)」にある「[Ruby/Railsのバージョンを上げてみよう](https://railstutorial.jp/reading_guide#exercise)」に着手したディレクトリ ([7_0](https://github.com/yasslab/sample_apps/tree/main/7_0)) も用意しています。アップグレードの練習をしたい場面などでご活用ください :gift: 

<br>


<br>

## :white_check_mark: 動作環境と注意事項
**本リポジトリにあるサンプルコードは [AWS Cloud9](https://aws.amazon.com/jp/cloud9/) 上で動作確認しています。** macOS や Windows などのローカル環境では下記の手順で動かないこともあります。あらかじめご了承ください。

:scroll: [開発環境（AWS Cloud9） - Railsチュートリアル](https://railstutorial.jp/chapters/beginning#sec-development_environment)

<br>

また**2022年9月より VS Code + Docker 環境でもチャレンジできる**ようになりました。詳細は下記の note 記事をご参照ください。

🐳 [devcontainerを使って開発してみよう - note](https://note.com/yasslab/n/n5dcbd7eb43c6)

<br>

## :wrench: アプリを動かす方法
版番号や章番号ごとにセットアップ方法は異なりますが、大まかな流れは基本的に同じです。例えば[Rails 6.0 対応](#open_file_folder-各章とディレクトリ名の対応関係)の第11章を動かす場合は次のようになります。

1. 本リポジトリをクローンし、該当のディレクトリへ移動します。
    ```
    $ git clone https://github.com/yasslab/sample_apps.git
    $ cd 6_0/ch11
    ```

2. 必要なパッケージをインストールし、`bundle install`（本番環境でのみ必要なgemはスキップ）します。
    ```
    $ yarn install --check-files
    $ yarn add jquery@3.4.1 bootstrap@3.4.1
    $ bundle install --without production
    ```

3. データベースを移行します。
    ```
    $ rails db:migrate
    ```

4. テストを実行して、正しく動作していることを確認します。
    ```
    $ rails test
    ```

5. サンプルユーザーをデータベースに`seed`して、アプリを実行する準備が整いました。
    ```
    $ rails db:seed
    $ rails server
    ```

無事にセットアップが完了できていれば、ブラウザから [localhost:3000](http://localhost:3000/) にアクセスするとトップ画面が表示されます。ログインページから以下のメールアドレスとパスワードを入力するとログインできます。

- メールアドレス: `example@railstutorial.org`
- パスワード: `foobar`

なお、第13章以降のSample Appを本番環境にデプロイする場合は、別途[Amazon S3のセットアップ](https://github.com/yasslab/sample_apps/blob/f797b502de9e033be5d14b5f34429e48ce453dea/6_0/ch13/config/storage.yml#L11-L14)が必要になります。

<br>

## :mortar_board: 関連リンク/関連レポジトリ

- 🎓 [Railsチュートリアル](https://railstutorial.jp)
- 🎓 [Railsチュートリアル電子書籍](https://railstutorial.jp/ebook) 📖
- 🎓 [Railsチュートリアル解説動画](https://railstutorial.jp/screencast) 📹
- 🎓 [Railsチュートリアル質問対応](https://railstutorial.jp/#learn-by) 💡
- 📕 [Railsガイド](https://railsguides.jp)
- 📕 [Railsガイド電子書籍](https://railsguides.jp/ebook) 📖
- 📕 [Railsガイド『Proプラン』](https://railsguides.jp/pro) 🔍
- 📕 [Railsガイド『Teamプラン』](https://railsguides.jp/pro) 🔍
- :octocat: [yasslab/railsguides.jp (公開リポジトリ)](https://github.com/yasslab/railsguides.jp)

<br>

## :octocat: 本リポジトリのライセンス

The [MIT License](https://ja.wikipedia.org/wiki/MIT_License)

Copyright &copy; [YassLab Inc.](https://yasslab.jp)

[![YassLab Logo](https://yasslab.jp/img/logos/800x200.png)](https://yasslab.jp)

<br>

## :octocat: Sample Appのライセンス

Ruby on Rails Tutorial: Learn Web Development with Rails.

All source code in the Ruby on Rails Tutorial is available jointly under the MIT License and the Beerware License.

Copyright &copy; [Michael Hartl](https://www.michaelhartl.com/)

