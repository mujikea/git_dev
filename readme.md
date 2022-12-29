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
1. git branch -M main
2. file creation
  * echo "hello world" > a.txt
  * echo "hello world" > b.txt
  * echo "hello world" > c.txt
1. git status
2. git add a.txt
  * git add <filename>...
  * git add *
1. git status
2. echo "kojk" >> a.txt : 파일 내용 변경 -> tracked modified 상태롤 변경
3. git status
4. git add a.txt : staging area로 다시 등록
5. git restore --staged a.txt
  * git restore a.txt : working directory 수정된 내용을 되될린다.
1.  git rm --cached *
2.  git status
3.  rm a.txt
4.  git status
5.  git add . : 삭제된 파일은 제외하고 starting area 영역으로 등록
6.  echo *.log > .gitignore
7.  git status
8.  echo add >> c.txt
9.  git status
10. git diff
11. cat c.txt
12. git diff --staged
  *  변경 사항이 많을 경우 : "q"를 입력하면 내용 확인에서 바로 빠져나옴
1.  git diff --cached
2.  git commit
3.  git log
  * git log --oneline --all --graph
1.  git commit -m "second commit"
2.  git commit -am "third commit" : working directory and staging 모든 파일 commited
3.  git remote add origin https://github.com/mujikea/git_dev.git
4.  git push -u origin main
5.  git checkout main
  * git checkout -b dev : branch 생성하고 이동
    * git branch dev
    * git switch dev
  * git checkout -b exp
1.  git checkout main
    * git switch main
2.  git merge exp
3.  git reset --hard <commit_id>
4.  git cherry-pick <commit_id> : 부분 벙합 commit_id에 해당하는 내용만 벙합
5.  git status 
6.  중복된 코드가 있을 경우 수정하고
7.  git add <filename>
8.  git cherry-pick --continue
9.  git reset --hard <commit_id>
10. git rebase exp
11. 머지가 줄기가 아닌 하나의 라인으로 변경된 사항의 시점을 알 수 있다
12. 중복된 코드가 있을 경우 사용자 머지
13. git rebase --continue
14. git branch --list
15. git branch dev
16. git checkout dev
17. git push origin --delete dev
    * git branch -d dev
    * git push origin dev
## git 리모트 변경
1. git pull origin main
2. git add .
3. git commit -m "clean push"
4. git push oring main
5. git remote remove origin
6. git remote add origin https://github.com/리모트레파지토리
7. git push -u origin --all
8. git push -u origin --tags
9. 