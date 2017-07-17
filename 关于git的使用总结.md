1. git init 初始化一个git repository，这个命令是在文件夹里加入了一个.git文件，里面是git管理的源文件；
2. git add 把这个文件夹里需要管理的文件，加入工作区；可以add 很多的文件。
3. git commit -m "sth" 将工作区的修改提交到repo。
4. git push origin master 将本地的repo 提交到远端，这个工作是要在你完成一个功能，或者修改玩一个bug后提交到远端的master（稳定版本），理论上完成一个工作就要push 一下；
5. git checkout -b dev 创建一个名为dev的分支，用来实现创意，或任务。
6. git merge -no-ff -m "sth" [branch-name] 合并分支，将分支checkout到master ，执行这句代码，将使用recursive strategy 将分支历史保留，然后合并分支。
7. git branch -d dev 此时dev 已经完成了他的历史任务，执行这句代码，将他删除，此时只剩下一个master分支；
8. git tag v1.0 -m "sth" 给此时的代码一个语义化的版本标签。
9. git push origin <tagname> 将标签提交到远程的repo。
10. **标签的管理** 忘了打标签：git tag v1.3 -m "sth" 版本号   可以给这个提交版本打一个标记。删除标签:
````
git tag -d  <tag-name>
git push origin :refs/tags/<tag-name>//如果tag 传入远端repo，执行这个可以删除远端的tag;
git push origin --tags //将本地的所有的已经存在的tag同步到远端repo;
````
11. git stash 将当前的分支任务存储，存储到 git stash list，用于解决当前的功能还未完成，直接合并会产生问题，而要解决突发的任务的时候。
12. git stash pop, git stash apply@{list里的数字}，git stash drop@{list里的数字}。紧急任务处理完了，回到之前的功能实现，调出存储；
13. git status 查看git工作状态；
14. git diff sth 差异分析；
15. git log 查看commit的信息；
16. git log --pretty=oneline; 使commit信息一行显示；
17. git reflog 命令历史；
18. git reset --hard HEAD^ 回退到上一个版本；
19. git reset --hard HEAD^^ 回退到上上个版本；
20. git checkout --file 撤回处于工作区的修改，回到最近的一次git commit 或者 git add;常用来恢复在工作区删除的问件；
21. git reset HEAD  filename ;撤回处于工作区的修改。从git add 撤回到工作区。
23. git log --graph --pretty=oneline --abbrev-commit; 使用图像查看log历史；
24. git rm file ;删除版本库中的文件。此时要commit一下来同步版本；
## 远程仓库操作：
1. git remote add origin git@github.com:redTerryCap/仓库名；代码执行，将与github.com:redTerryCap/test(repo名字)，建立关系，注意点，先要在GitHub上创建一个仓库，其次，不要在仓库初试化一个readme.md 文件，应该建立一个完全空的仓库，否则会出现无法建立连接的问题。
2. git clone git@github:redTerryCap/<repo-name>.git
执行代码，会在光标所在的文件夹，从远端复制一个代码仓库。里面会有一个.git 的文件夹以及，初试化来的一个readme.md，文件；
3. git ssh-keygen -t rsa -C "yourEmail@example.com" 以上这两种方式，都能建立连接。但是有一个前提，你要使用github 的代码托管服务，要将id_rsa.pub 这个公钥添加到ssh-key。执行上面一段代码，就能在本机产生一个ssh-keygen,要保证这个密码保存在有权限的用户下面。同时**使用第一中方式** 依托本地git仓库创建的托管仓库，需要将本地的repo，push上去，git push origin master ；代码与远端同步后，稳定的修改一定要及时的git push origin master;保证代码的安全；
### 自定义git 
1. git config --global user.name "your name",在全局定义用户名，也就是所有的git repo 都可以访问。
2. git config --global user.email "email@example.com";定义用户的email地址；
3. git config --global color.ui true; 自定义git-bush的颜色属性，可以让他看起来五彩缤纷；
4. **配置别名** git config --global alias.<缩写> 代码片段；
5. 牛B的别名配置 git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
特别的格式查看log；
### .gitignore 文件
1. .gitignore 文件是git status 的判断标准，加入到里面的文件，会被git 所忽略。
2. 如果一个文件被的类型被加入了 .gitignore 文件。此刻你又需要添加，git add -f <file-name>;
3. 可以通过 git check-ignore -v <file-name> 查看此文件是否在忽略名单中；

