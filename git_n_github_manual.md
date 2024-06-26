<!-- Git & GitHub -->
# Git & GitHub Manual

### 개요:
1. 내 소스코드를 저장 (버전관리)
2. 소스코드 공유
3. 협업하는 공간


### Create a new repository on the command line:
```
echo "# first-project" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:jonghy92/first-project.git
git push -u origin main
```

### push an existing repository from the command line:
```
git remote add origin git@github.com:jonghy92/first-prjoect.git
git branch -M main
git push -u origin main
```

<br>
<br>

## 처음 github 사용시:
1. git install - (https://git-scm.com/download/win)
2. 회원가입
3. github에서 repository 초기 구축 
4. SSH --> id_rsa.pub --> public 키 설정
5. id_rsa 는 --> non-public 키 설정


### 초기 config 세팅:

1. `이름 기입`
> git config --global user.name "jhl"
1. `깃헛 가입했을때 이메일 기입`
> git config --global user.email "jonghy92@gmail.com"
1. `깃헙 config 정보 체크`
> git config --list

<br>

__비고:__ <br>
github을 처음 사용하면 repository를 웹사이트에서 만들어야 함. <br>
그리고 난 후, 'git remote add' 명령어로 repository 주소를 넣어주어 서로 연결시켜 주어야 remote 작업을 시작할 수 있음.


<br>
<br>


## I. 초기 Github 업데이트:
#### 1. 원하는 디렉토리로 이동 후:
> git init

#### 2. 파일 업로드
> git add .
> 
> git add index.html

#### 3. 파일들 상태 체크
> git status

#### 4. Commit - history log
> git commit -m "first commit"

#### 5. Branch 설정 (main)
> git branch -M main

#### 6. 연결고리 구축
> `git remote add origin git@github.com:[유저 명]/[레파지토리 명.git]`
>
> git remote add origin git@github.com:jonghy92/Markdown-Manual.git

#### 7. 연결고리 확인
> git remote -v
 
#### 8. Push - 작업 업로드
> git push origin main


<br>
<br>



## II. Github에 계속 업데이트 하는법
#### 1. 추가할 파일 더하기
> git add .


#### 2. 히스토리 만들기
> git commit -m "second commit"


#### 3. Github으로 올리기
> git push origin master



<br>
<br>



## III. Github로 팀 프로젝트 하는법:
__Github에서 repository 가져오기:__

<br>

#### 1. Github에서 소스코드 다운로드 (repository)
> git clone 주소 폴더이름
>
> git clone https://github.com/jonghy92/github-test.git

#### 2. Github에서 새로운 브렌치 (branch) 만들기
> `git checkout -b 브렌치이름` <br>
> git checkout -b test-branch


#### 3. 브렌치에 소스코드 업데이트
> git add.
>
> git commit -m "first commit"
>
> `git push origin 브렌치이름` <br>
> git push origin test-branch


#### 4. master|main 브렌치에 소스 가져오기 (pull)
> git pull origin master
>
> git pull origin main

#### 5. 브렌치끼리 이동하는 법
> `git checkout 브렌치이름`
>
> git checkout test-branch

<br>

__Note:__
```
1.
main | master 브렌치에 항상 최신 코드를 담게 되는데, 마스터 브렌치 사용자(관리자)는 항시 다른 브렌치에 업데이트를 확인하여 마스터 브렌치에 업데이트 및 관리를 해 주어야 함.  

2.
마스터 관리자가 브렌치 및 자신의 작업 코드를 업데이트 시:
    
    #1. 마스터 자기자신 코드 add:
        - git add .

    #2. 마스터 자기자신 코드 commit:
        - git commit -m "first master commit"

    #3. 마스터 코드 및 업데이트한 브랜치 코드 merge:
        - git pull origin master




```


<br>
<br>
