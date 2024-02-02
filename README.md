gitskills
=========

first try on github, thanks to this website http://www.liaoxuefeng.com/

useful commonds

git init /* build a new repository @ local machine

git add  /* add files to buffer 

git commit /* add files to repository

git status

git diff



git remote add origin git@github.com: ZJLi2013/localgit.git 
/* local repository linked to github remote repository

git push (-u) origin master  /* push local files to github(remote) repository

git clone git@github.com:ZJLi2013/remotegit.git 
/* clone files from github to local repository


finally, "Fork" niunius' hithub


## 2024-Feb-2

1. 查看某个分支最新的commit 

git log -n 1 [--oneline] my-branch 

2. 查看某个分支上所有的commits

git branch --contains commitID

3. 比较文件版本

git diff commitA commitB -- path/to/file

4. 查找指定 commit ID 对应的提交

git show commitID

5. 如何管理项目依赖包 

通常做法： 编辑一个requirements.txt 或 创建一个 conda 环境文件 mmdet3d.yaml
way-1: 在安装了mmdet3d 的环境中运行：  pip freeze > requirements.txt 
way-2: 
conda create --name mmdet3d python=3.8
conda activate mmdet3d
...
conda env export --no-builds > mmdet3d.yml 

6. 查看项目中依赖包的版本兼容性

way-1: 使用pip-compile 生成一个满足所有依赖关系且包含已锁定版本的rquirements.txt
    pip install pip-tools
    echo "scikit-image==1.19.3" >> requirements.in 
    pip-compile --upgrade-package mmdet3d requirements.in > requirements.update.txt 

way-2: 使用pipdeptree 可视化项目的依赖树， 
    pip install pipdeptree
    pipdeptree --package=mmdet3d 