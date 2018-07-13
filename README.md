# paper summary

This is the repositroy where I save summaries of papers I've ever read.\
I'm writing them in Japanese for a while, but I wanna try in English in the future.

## Gitの基本コマンド(memo)

```
# ネットなどからレポジトリー（プロジェクト）を取ってくる
$ git clone <urlなど>

# 今の状態を確認
$ git status 

# 現在のブランチから新しいブランチを作る（作るだけでブランチには入らない）
$ git branch <ブランチ名>

# ブランチに入る
$ git checkout <ブランチ名> 

# コミットするためのファイルを追加
$ git add <ファイル名> 

# コミットし，コミットのメッセージ(なんでもよし)を追加
$ git commit -m "<メッセージ>"

# ブランチでの変更をプッシュする
$ git push -u origin <ブランチ名> 

# ブランチの最新バージョンを取ってくる
$ git pull origin <ブランチ名> 
```
