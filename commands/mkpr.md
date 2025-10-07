---
name: mkpr
description: ブランチとPRを新規作成する
---

1. ユーザに以下を聞いてください。
ブランチ名を入力してください。

例）feature/CLOUD-123

2. ユーザに以下を聞いてください。
PRのタイトルを入力してください。

例）CLOUD-123: webロールのCodeDeploy導入

3. 以下の順番でコマンドを実行してください。
$ git switch main
$ git pull origin main
$ git switch -c {ブランチ名}
$ git commit --allow-empty -m "開発開始"
$ git push origin {ブランチ名}
$ gh pr create --base main --head {ブランチ名} --title "{PRのタイトル}" --assignee @me --draft --body "$(cat .github/PULL_REQUEST_TEMPLATE.md)"
  * ただし、リポジトリ内に.github/PULL_REQUEST_TEMPLATE.mdがない場合は--fillオプションを使用してください。

# 注意点
コマンドの実行中にエラーが発生した場合、エラーの内容と原因をユーザに説明した上で対処法を提示してください。
