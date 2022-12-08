author: 三浦一樹
summary: 説明文
id: docs
categories: codelab,markdown
environments: Web
status: Draft
feedback link: https://github.com/miura-bd/lambda-ci-cd-handson/issues

# Lambda CI/CD ハンズオン

## はじめに

Duration: 0:05:00

### はじめに

#### 色々な選択肢

![技術コンポーネント](./img/overview.png)

- repository
  - CodeCommit
  - GitHub
- framework
  - AWS SAM
  - serverless framework
- deploy
  - CodeBuild
- IDE
  - AWS Cloud9
  - Visual Studio Code

組み合わせは色々ありますが、今回は以下のものを使用します

- repository
  - CodeCommit
- framework
  - AWS SAM
- deploy
  - CodeBuild
- IDE
  - AWS Cloud9


## 今回構築するもの

Duration: 0:05:00

- AWS Lambda を構築します

Positive
: This will appear in a positive info box.

Negative
: This will appear in a negative info box.

<aside class="positive">
This will appear in a positive info box.
</aside>

<aside class="negative">
This will appear in a negative info box.
</aside>

<button>
  [Download SDK](https://www.google.com)
</button>

## CodeCommit の準備

Duration: 0:05:00
### リポジトリの作成（コンソールから実施）

リポジトリ名を以下で作成

lambda-cicd-hands-on
### HTTPS(GRC)でクローンするコマンドをコピー

<aside class="positive">
python と git-remote-codecommit が必要ですが、今回使用する Cloud9 は最初から入っているので、そのまま使えます
</aside>

## Cloud9 の準備（コンソールから操作）

Duration: 0:05:00

スクショどーんでオープン


### CodeCommit へのファーストコミットの作成

作成した CodeCommit リポジトリに対して、ファイルを追加してみましょう。

CodeCommit でHTTPS(GRC)をコピー

Cloud9 の画面下部にのターミナルにコピーして実行

```console
git clone codecommit::ap-northeast-1://lambda-cicd-hands-on
```

git のユーザを指定します。
これをやっておかないと途中で怒られます

```console
git config --global user.name "Your Name"
git config --global user.email you@example.com
```
上記を自分のものに書き換えて実行してください


レスポンス

```console
Cloning into 'lambda-cicd-hands-on'...
warning: You appear to have cloned an empty repository.
```

空のディレクトリがコピーされるので、そのディレクトリに移動します

```console
cd lambda-cicd-hands-on
```

試しに、AWS上の CodeCommit に追加するファイルを作成します

```console
touch test.md
```

Cloud9 で 作成されたファイルに追記してみましょう

```markdown
# test
ちゃんとpushができるかテスト。
```

git のステージエリアにファイルを追加します

```console
git add test.md
```

ステージに登録されているか、確認してみましょう

```console
git status
```

レスポンス
```console
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   test.md

```


変更したファイルを コミットします

```console
git commit -m "ファーストコミット"
```

CodeCommit に追加します

```console
git push
```

AWS コンソールで CodeCommit を開いて、ファイルが追加されていることを確認しましょう

## AWS SAM の準備

Duration: 0:05:00

Cloud9 には SAM CLI がプリインストールされているので、特に作業は必要ありません。

Cloud9 のコンソールで以下のコマンドを実行し確認してみましょう。

```console
sam --version
```

レスポンス
```console
SAM CLI, version 1.57.0
```

## AWS CodeBuild の準備

Duration: 0:05:00

## 複数環境の構築

Duration: 0:05:00

## お掃除

Duration: 0:05:00