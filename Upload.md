```console
$ git branch
$ git add .
$ git commit -m "Update website content"
$ git push origin master
```

- git branch 可以看有哪些分支
- git add . 可以將所有檔案（有更新、沒更新）放至暫存區
- git commit -m "Update website content" 告訴git要提交哪些文件
- git push origin master 指定本地 master 分支進行推送，如果存在 master 分支即合併，不存在即新增