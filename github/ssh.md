sshの過程のログを出せる
```
ssh -vT nkshun
```

- .ssh/configの記載方法

```
#-------------------
Host git-nkshun
  HostName github.com
  IdentityFile ~/.ssh/id_rsa_
  User git
  # IdentityFileで指定した秘密鍵でのみ認証を試みる ※IdentityFile使う場合必須 これ書いてなくて下記エラー出てた
  IdentitiesOnly yes
  # Git でのファイル転送時に圧縮する
  Compression yes
```

```
$ git push origin main
ssh: Could not resolve hostname nkshun: nodename nor servname provided, or not known
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```
(参考)[https://zenn.dev/nikaera/articles/ssh-config-github]


