「忘れちゃっても実装できる仕組み」を作りたくて、基本的なgitコマンドをまとめました。

今後も長らくお世話になるものだと思うので、自分を含め他の人のお役に立てれば幸いです。

## init【リポジトリの準備】

### ディレクトリにリポジトリを作成.

```
$ git init
```

### ベアリポジトリの作成

```
$ git init --bare
```

### グループ書き込み権限を有効にする.

```
$ git init --shared
```

## remote 【リモートリポジトリの一覧】

### リモートリポジトリの一覧表示

```
$ git remote
```

### リモートリポジトリの追加

```
$ git remote add [username] [remote repository PATH]
```

### リモートリポジトリの名前変更

```
$ git remote rename [remoterepository] [new name]
```

### リモートリポジトリの情報を見る

```
$ git remote show [remote repository]
```

### リモートリポジトリで排除されたブランチをローカルからも削除

```
$ git remote prune [remote repository]
```

## fetch 【リモートリポジトリの情報のついかと更新】

### リモートリポジトリの最新情報を追加

```
$ git fetch [remote repository]
```

### リモートリポジトリの削除情報をローカルに更新

```
$ git fetch --prune
```

## branch【ブランチの操作】

### 現在のブランチの確認と、新しいブランチを作成

```
$ git branch &[new branch]
```
### すべてのブランチを確認

```
$ git branch -a
```

### リモートブランチを確認

```
$ git branch -r
```
### ブランチを削除

```
$ git branch -d [branch]
```
### ブランチの名前を変更

```
$ git branch -m [branch] [new branchname]
```
### 他のユーザーのブランチ、自分のブランチを関連付ける

```
$ git branch --set-upstream [my branch] [other branch]
```

## add 【インデックスに追加・登録する】
### ファイルやディレクトリをインデックスに登録.

```
$ git add [filename]
```

### すべての変更を含むワークツリーの内容をインデックスに追加.

```
$ git add -A
```

### 以前コミットしたことがあるファイルだけインデックスに追加.

```
$ git add -u
```


## commit【コミットの操作】

### インデックスに追加されたファイルをコミット

```
$ git commit
```

### コミットメッセージを添えてコミット

```
$ git commit -m “[comment]”
```
### 新規を除く変更されたファイルをインデックスに追加してコミット

```
$ git commit -a
```

###直前のコミットを修正

```
$ git commit --amend
```

## status ファイルの変更を表示

### 前回のコミットと比較してどのファイルが変更されたかを表示.

```
$ git status
```

## log 【コミットログの操作】

### コミットログを参照

```
$ git log
```

### コミットログの先頭７桁のコミットIDを表示

```
$ git log --oneline
```

### コミットログのHEADの位置を明示

```
$ git log --decorate
```

### コミットログを縦グラフで表示

```
$ git log --graph
```

### 指定した文字がコミットログに含まれるコミットを表示

```
$ git log --grep [filter]
```

## diff 【差異を表示】

### インデックスとワーキングツリーの差異を表示

```
$ git diff
```

### HEADとインデックスの差分を表示

```
$ git diff --cached
```

### コミット間の差異を表示

```
$ git diff [commit id 1] [commit id 2]
```

## checkout

### コミットされた過去のファイルを復元

```
$ git checkout [commit id] [filename]
```

### ブランチを変更

```
$ git checkout [branch]
```

### コンフリクトしたときに上方を指定してファイル内容を採用

```
$ git checkout --ours [filename]
```
### コンフリクトしたときに下方を指定してファイル内容を採用

```
$ git checkout --theirs [filename]
```

## show 【表示に関する操作】

### 最新のコミット内容を表示

```
$ git show
```

### タグを指定してコミット内容を表示

```
$ git show [tagname]
```

## reset 【やり直しなどの操作】

### インデックスを現在のHEADの状態にする

```
$ git reset [commit id]
```

### インデックスからファイルをアンステージ

```
$ git reset HEAD [filename]
```

### すべてをコミットIDの状態に戻す

```
$ git reset --hard [commit id]
```

### git reflogで確認した番号の状態に戻す

```
$ git reset --hard HEAD@{[number]}
```

### 直前の状態に戻す

```
$ git reset --hard ORIG_HEAD
```

## rm 【ファイルを削除】

### ワークツリーとインデックスからファイルを削除

```
$ git rm [filename]
```

### インデックスのファイルを削除

```
$ git rm --cached [filename]
```

## mv 【ファイル名を変更】

### インデックスとワークツリーに同ファイル存在時、ファイル名を変更

```
$ git mv [filename 1] [filename 2]
```

## revert / rebase 【コミットの取り消し】

### コミットIDのコミットを取り消す

```
$ git revert [commit id]
```

## rebase

### コミットIDから古い順にコミットを表示

- コミットの行を消すとコミットの取り消し
- 先頭のpickをほかのものに置き換えるとコミットメッセージなどの編集が可能

```
$ git rebase -i [commit id]
```

### 直前のgit rebaseの編集を中止

```
$ git rebase --abort
```

### git rebaseの変更を適応

```
$ git rebase --continue
```

## clone 【リポジトリをコピー】

### リポジトリをコピー

```
$ git clone [repository PATH] [new repository PATH]
```

## push 【リモートリポジトリに変更を書き込む】

リモートリポジトリに変更を書き込む.

```
$ git push [remote repository PATH] [branch]
```

### リモートリポジトリにすべてのタグをアップロード

```
$ git push [remote repository] --tags
```

### リモートリポジトリに指定したタグをアップロード

```
$ git push [remote repository] [tagname]
```
### 指定したブランチ,もしくはタグをリモートリポジトリから削除

```
$ git push [remote repository] :[branch or tagname]
```

## pull

### リモートリポジトリの変更を取り込む

```
$ git pull [remote repository PATH] [branch]
```


## merge 【ブランチ同士をマージ】

現在のブランチをほかのブランチとマージ

```
$ git merge [branch]
```

## tag

タグの一覧を表示

```
$ git tag
```
### タグとそのメッセージ[行数指定]の一覧を表示する(行数指定なしの場合１行)

```
$ git tag -n[number]@
```
### タグを,フィルターをかけて表示する.

```
$ git tag -l [filter]
```
### 現在のコミットIDにタグを関連付けする.

```
$ git tag [tagname]
```
### コミットIDを指定してタグを関連付けする.

```
$ git tag [tagname] [commit id]
```

### 現在のコミットIDにメッセージ付きのタグを関連付けする.

```
$ git tag -a [tagname]
```


### 指定したタグを削除する.

```
$ git tag -d [tagname]
```


## stash

### 現在の状態を保存する.

```
$ git stash
```


### メッセージ付きで現在の状態を保存する.

```
$ git stash save “[message]”
```


### 保存した状態の一覧を表示する.

```
$ git stash list
```


### 最新の保存状態を復元する.

```
$ git stash pop
```


### 番号を指定して保存状態を復元する.

```
$ git stash pop stash@{[numbar]}
```


### 保存状態をリストに残したまま最新の保存状態を復元する.

```
$ git stash apply
```


### 保存状態をリストに残したまま指定した番号の保存状態を復元する.

```
$ git stash apply stash@{[number]}
```


### 保存状態を削除する.

```
$ git stash drop stash@{[number]}
```


### 保存状態をすべて削除する.

```
$ git stash clear
```


## reflog

### 過去にHEADが指していたコミット一覧をを表示する.

```
$ git reflog
```


### ブランチを指定して過去にHEADが指していたコミット一覧を表示する.

```
$ git reflog [branch]
```


## cherry-pick

### 別のブランチのコミットを現在のブランチにコピーする.

```
$ git cherry-pick [commit id]
```


## config

### 使用されるリポジトリの設定を表示する.

```
$ git config -l
```

### ユーザ名の設定.

```
$ git config --global user.name [username]
```


### メールアドレスの設定.

```
$ git config --global user.email [email address]
```



### 出力結果を色づけする.

```
$ git config --global color.ui auto
```
### まとめ

テーブルにすべきか、コードにすべきか悩みましたが、とりあえずコピペ出来る校舎にしてみましたがいかがでしょうか。

とりあえず最初は

1. リモートリポジトリをクローン
2. ブランチを切って作業
3. 変更してコミット
4. コミットメッセージを添えてプッシュ
5. レビューを受けて修正
6. マージして1にもどる

という開発の基本的な流れができるようになりましょう！

長文お疲れさまでした！
