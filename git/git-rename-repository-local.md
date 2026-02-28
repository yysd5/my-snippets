---
Title: Update local repository after GitHub rename
Description: |
  GitHubでのリポジトリ名称変更後に、ローカルリポジトリのリモートURLを更新する手順。
Tags:
  - git
  - github
---

GitHub上でリポジトリ名を変更した際、ローカルでの作業。

```bash
# 1. 現在のリモートURLを確認
git remote -v

# 2. 新しいリポジトリURLを設定 (originを想定)
# <new-url> は GitHub の Code ボタンから取得できる URL
git remote set-url origin <new-url>

# 3. 正しく設定されたか確認
git remote -v

# 4. (任意) GitHubとの通信を確認
git remote show origin
```
