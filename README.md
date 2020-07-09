# タスク遂行時のGit操作
git cloneしたあと以下のステップで修正してください。

## 1.リモートのdevelopブランチをローカルに反映する

```bash
git checkout -b develop origin/develop
```
※一度作ったら今後は不要

## 2.featureブランチを作成する
```bash
git checkout -b feature/[task]
```
※developブランチ参照中に行うこと
※[task]は自分のタスク名をつけること

## 3.色々修正してコミットする
修正後、単体テストまで完了したら次のステップへ。

## 4.developブランチをpull
```bash
git checkout develop
git pull origin develop
```

## 5.featureブランチにdevelopブランチをマージ
```bash
git checkout feature/[task]
git merge develop
```
※コンフリクトしたら修正してコミットしてください。

## 6.developブランチにfeatureブランチをマージ
```bash
git checkout develop
git merge feature/[task]
```

## 7.developブランチをpush
```bash
git push -u origin develop
```

<br>

# リリース方法
developブランチで結合（システム）テストが終わったら次のステップへ。

## 1.masterブランチにdevelopブランチをマージする
```bash
git checkout master
git merge develop
```

## 2.masterの変更をリモートにpush
```bash
git push -u origin master
```
