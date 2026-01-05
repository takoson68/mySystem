Setup: clone and push to both remotes
=====================================

使用情境：在新環境（例如家裡筆電）要建立與目前相同的設定，讓 `git push` 同步到你的庫與原作者庫。

## 使用 HTTPS
```sh
git clone https://github.com/takoson68/mySystem.git
cd mySystem
git remote rename origin upstream
git remote add origin https://github.com/takoson68/mySystem.git
git remote set-url --push origin https://github.com/takoson68/mySystem.git
git remote set-url --add --push origin https://github.com/wdaweb/WebBackend_System-takoson68.git
git push origin main
git remote -v  # 檢查設定
```

## 使用 SSH（可選，若你偏好 SSH）
將上面的兩個 URL 改成 SSH 版：
```
git@github.com:takoson68/mySystem.git
git@github.com:wdaweb/WebBackend_System-takoson68.git
```

## 說明
- `origin`：用來 fetch/推送到你的庫，push 設定同時包含兩個 URL，所以 `git push` 會依序推到你的庫與原作者庫。
- `upstream`：保留原作者庫以便必要時 `git fetch upstream` 或 `git pull upstream main` 取得更新。
