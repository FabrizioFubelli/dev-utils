# docker-credential-pass 

 1.  Install `docker-credential-helpers`
 2.  check that docker-credential-pass work. To do this, run command `docker-credential-pass`. You should see: `Usage: docker-credential-pass <store|get|erase|list|version>`.
 3.  install `gpg` and `pass`: `apt install gpg pass`
 4.  `gpg --generate-key`. Enter your name, mail, etc. You will get gpg-id like `5BB54DF1XXXXXXXXF87XXXXXXXXXXXXXX945A`. Copy it to clipboard.
 5.  `pass init <(paste from clipboard)>`
 6.  `pass insert docker-credential-helpers/docker-pass-initialized-check` and set the next password: `pass is initialized`.
 7.  ` pass show docker-credential-helpers/docker-pass-initialized-check`. You should see `pass is initialized`.
 8.  `docker-credential-pass list`. You should see `{}` or another data. You shouldn\`t see error like `pass store is uninitialized`.
 9.  `nano ~/.docker/config.json`. Set in root node the next line "credsStore": "pass" save ctrl+o.
 10. after docker login and etc.
