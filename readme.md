# git 깃허브 제대로 배우기(기본 마스터편, 실무에서 글리자 말자)

## git config
* git config --global core.editor "code"
  * vscode IDE로 기본 에디터로 사용
* git config --global core.editor "code --wait"
  * Editor에서 수정 완료되면 터미널에서 명령어 입력 가능
* git config --global -e
* git config --global user.name "kojk"
* git config --global user.email "mujikea@gmail.com"
* git config --global core.autocrlf true
  * git config --glocal core.autocrlf input
* git config user.name
  * git config user.email
  * git config core.autocrlf
* git config --h
## git init
* git init 
  * .git 폴터 생성
* rm -rf .git
## git workflow 
* local area
  * working directory
    * command 
      * checkout -> .git history 언제든 해당 버전 파일을 working directory로 불러올 수 있다 
  * staging area
    * command 
      * commit -> .git 등록
  * .git Directory
    * command
      * push -> remote area로 파일 등록
      * pull -> remote area의 파일을 불러온다.
* remote area
## git file status
* working directory
  * untracked
    * command
      * git add filename
  * tracked
    * unmodified
    * modified
      * staging area로 옮겨갈 수 있다
## 실습
1. 3개 파일 생성
  * echo "hello world" > a.txt
  * echo "hello world" > b.txt
  * echo "hello world" > c.txt
2. git status
3. git add a.txt
  * git add <filename>...
  * git add *
4. git status
5. echo "kojk" >> a.txt : 파일 내용 변경 -> tracked modified 상태롤 변경
6. git status
7. git add a.txt : staging area로 다시 등록
8. git restore --staged a.txt
  * git restore a.txt : working directory 수정된 내용을 되될린다.
9.  git rm --cached *
10. git status
11. rm a.txt
12. git status
13. git add . : 삭제된 파일은 제외하고 starting area 영역으로 등록
14. echo *.log > .gitignore
15. git status
16. echo add >> c.txt
17. git status
18. git diff
19. cat c.txt
20. git diff --staged
  *  변경 사항이 많을 경우 : "q"를 입력하면 내용 확인에서 바로 빠져나옴
21. git diff --cached
22. git commit
23. git log
  * git log --oneline --all --graph
24. git commit -m "second commit"
25. git commit -am "third commit" : working directory and starting 모든 파일 commited
26. git remote add origin https://github.com/mujikea/git_dev.git
27. git push -u origin master
28. git checkout master
  * git checkout -b main : branch 생성하고 이동
  * git checkout -b exp
29. git checkout master
30. git merge exp
31. 

