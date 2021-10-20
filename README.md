# teamDemo
チーム開発用のデモリポジトリ



## はじめに

チームでコラボレートする手順を試すためのリポジトリです。いろいろ出てくるであろう問題になれることを目的としていますので、積極的に変なことをしてみてください（壊れたらみんなで直しましょう）。

Colaboratorを登録してしまうと普通のリポジトリと同じになってしまうので、あえて登録していません。基本的にはプルリクエストでのやり取りを体験することを目的にしたいと思います。

gitについては下記あたりを参考にしていただければと思いますが、すべてを使うわけではないので、軽くでいいと思います。add, commit, push, pull, branch, checkoutくらいのでとりあえずは進めるはずです。

（というかそれ以上は私もあんまりなので一緒に勉強しましょう）





##  ブランチ構成について

基本的には一番単純な**Github flow**での管理のデモをしたいと思います。

フローの内容について詳細は割愛しますが、参考URLを下記に示しますので適宜参照してください。



基本的なブランチの役割は2つです。

**master**: 常にプログラムの動作が確認されているブランチ。基本的にはPR～Mergeでしか更新されない。プッシュしないこと。

**features**: 実際に作業を行うブランチ。必ずmasterからブランチを切る。ブランチ名称はなんでもよい。



ちなみにほかにもGit flow, Gitlab flow, Git feature flowなどいろいろなブランチ構成が提案されています。比較の参考URLは下記です。



## ルール

### 1. masterブランチにはコミットしない

masterの更新は基本的にはプルリクエストmergeによってのみ行います。

### 2. 作業するときはまずブランチを切る

各自作業に当たってはまずfeaturesブランチ（名前を付けてください）を切ってチェックアウトして作業してください。

### 3. Folkはしない

プルリクエストはFolkしたリポジトリからもできますが、今回はより軽量な形の確認のためFolkはしない形式で作業を行ってみたいと思います。



## 環境

最低限gitが必要になります。Windows PCの場合は[git for windows](https://gitforwindows.org/)などをインストールしてください。なお組み込みでgitが使えるアプリケーションがある場合はそちらを使っていただいて構いませんが説明は基本的にコマンドで行います。

GUIでのGitクライアントアプリについては下記あたりが良いかと思います。

- [Git GUI](https://git-scm.com/book/ja/v2)
- [Sourcetree](https://www.atlassian.com/ja/software/sourcetree) (アカウント作成が必要？)
- [GitKraken](https://www.gitkraken.com/) (一部有料)



## 初回の動き

### 1. クローン
まずgithubからcloneしてください。

```shell
git clone http://172.16.116.6/inaba/teamDemo
```

> コマンド実行の場合、今いる階層にリポジトリがクローンされます。

### 2. ブランチの作成

自分の作業用のブランチを作成します。ここでは自分の名前にしましょう。

```shell
git branch feature/hogehoge
```



### 3.チェックアウトでブランチを切り替え

作業をするためにブランチを切り替えます。

```shell
git checkout feature/hogehoge
```



### 4. コーディング

ここで実際に作業をします。今回は指定ディレクトリ内に自分の名前のテキストファイルを作成しましょう。

```shell
teamDemo/
	├ member/
	│	├ hogehoge.txt # ここに「名前.txt」でテキストファイルを作成
	│	...
	...
	└ README.md
```



中身は下記としてください。

```shell
名前：hogehoge
グループ：hogehogeグループ
備考：なし
```

この状態でコミットします。

```shell
git add *
git commit -m "hogehoge"
```



### 5. プッシュ

github上のリポジトリにプッシュしましょう。クローンしてきているのでリモートのリポジトリはすでに登録済みです。下記でリモートの名称（origin）とURLが確認できます。

```shell
git remote -v
# origin http://172.16.116.6/inaba/teamDemo.git (fetch)
# origin http://172.16.116.6/inaba/teamDemo.git (push)
```

プッシュは下記で行います。

```shell
git push origin hogehoge
```



