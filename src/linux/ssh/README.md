# Transferring SSH files to another system

It's merely copying both `id_rsa` and `id_rsa.pub` to another systems `~/.ssh` folder. 
But make sure `.ssh` folder has `700` permission. `id_rsa.pub` has `644` and `id_rsa` has
`600`

```sh
sudo chmod 700 ~/.ssh
sudo chmod 644 ~/.ssh/id_rsa.pub 
sudo chmod 600 ~/.ssh/id_rsa
```