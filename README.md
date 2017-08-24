# JagaJaga

## ポリシー ##
**A successful Git branching modelを基本ポリシーです。**

以下3つの構成で行う。hotfix,releaseなどは使わない。

* master : 本番orテスト環境にアップする用基本触らずアップ担当者のみがdevelopからマージ等を行う

* develop : 開発者全員がこれをもとに開発。これが常に最新の状態になるようにする。featureブランチから各自マージする。ちっちゃなマージならfeatureを作らずにマージOK。

* feature-xxx : xxxは開発対応名。ある程度まとまった開発の場合にこのブランチを作成。開発者は大体このブランチで開発する。定期的にコミットプッシュし、管理者に管理やソース確認をしてもらう。 


【参考URL】

* http://keijinsonyaban.blogspot.jp/2010/10/successful-git-branching-model.html

* http://www.backlog.jp/git-guide/stepup/stepup1_5.html

　（↑こっち分かりやすい）

* http://www.slideshare.net/add20/ss-11951387

　（実践向き）

**基本的にdevelopブランチから新しいフィーチャーブランチを作成してください。**


**developブランチは最新の状態を保ってください。**
**developへのマージは必ず--no-ffで**

マージがgitのログに残るのでマージ関係を汚さずにすむ

【参考】真ん中あたり 

* http://d.hatena.ne.jp/sinsoku/20111025/1319497900


**フィーチャー開発が一段落し、うごくことを確認したらdevelopへのマージを試みてください。**


## 一連の流れ ##

※現在developブランチにいるとして
```
#!shell
$git checkout -b feature-xxx

# feature-xxxの実装がきり付いた

$git add hoge
$git commit -m "hogeをfugaまで実装"
$git push origin feature-xxx

# feature-xxxの実装が完了

$git checkout  develop
$git merge --no-ff feature-xxx
$git push origin develop


# git branch -d feature-xxx は特に行わない（ブランチが消えてしまう。）
```
