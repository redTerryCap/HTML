1. git config --global alias.st status
2. git config --global alias.co checkout
3. git config --global alias.ci commit
4. git config --global alias.br branch
5. git config --global alias.unstage "reset HEAD"
6. git config --global alias.last "git -1"  
7. git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
8. 如果配置以上别名，那么这些东西将会出现在每个.git/config 中；