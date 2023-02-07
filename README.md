# クロスアカウントでのCodePipeline

1. cf-template-01-prod.yamlを、本番環境（CodeCommitが無い環境）で実行
2. cf-template-02-dev.yamlを、開発環境（CodeCommitが有る環境）で実行
    1. パラメーターとして、01で作成したものを利用するので、それを使用する。
3. 開発環境に作成されたCodeCommitのリポジトリにファイルをプッシュ
    1. サンプルとして、site/index.html
4. cf-template-03-prod.yamlを、本番環境（CodeCommitが無い環境）で実行
    1. パラメーターとして、01で作成したものを利用するので、それを使用する。
    2. Apacheの起動がうまく行ってないので、EC2にインスタンスコネクトで入り起動する
5. cf-template-04-prod.yamlを、本番環境（CodeCommitが無い環境）で実行
    1. パラメーターとして、01、02で作成したものを利用するので、それを使用する。

## TODO

- [ ] ロールのアクションは、適当なので見直したい
- [ ] EC2作成時に、Apacheの起動がされていないので解消する