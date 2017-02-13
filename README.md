Git 스터디(2017. 02. 09 ~ )
===============

# 1. Git 최초 설정
## 1.1. Git 설정 파일
Git을 설치하고 나면 Git의 사용 환경을 적절하게 설정해 주어야 한다. 환경설정은 한 컴퓨터에서 한 번만 하면 된다. 설정한 내용은 Git을 업그레이드해도 유지된다. 언제든지 변경 가능하다.

'git config'라는 도구로 설정 내용을 확인하고 변경할 수 있다. Git은 이 설정에 따라 동작한다.

1. /etc/gitconfig 파일: 시스템의 모든 사용자와 모든 저장소에 적용되는 설정

	`git config --system 옵션으로 읽고 쓰기 가능`

2. ~/.gitconfig, ~/.config/git/config 파일: 특정 사용자에게만 적용되는 설정

	`git config --global 옵션으로 읽고 쓰기 가능`

3. .git/config: 이 파일은 Git 디렉토리에 있고 특정 저장소(혹은 현재 작업중인 프로젝트)에만 적용

각 설정은 역순으로 우선시 된다. 그래서 '.git/config'가 '/etc/gitconfig'보다 우선 적용된다.

## 1.2. 사용자 정보
Git을 설치하고 나서 가장 먼저 해야 하는 것은 사용자 이름과 이메일 주소를 설정하는 것이다. Git은 커밋할 때마다 이 정보를 사용한다. 한 번 커밋한 후에는 정보를 변경할 수 없다.

````
$ git config --global user.name "Enter The User Name(KimHyeongJae)"
$ git config --global user.email "Enter The User Email(sirius6321@naver.com)"
````

다시 말하자면 --global 옵션으로 설정하는 것은 딱 한 번만 하면 된다. 해당 시스템에서 해당 사용자가 사용할 때는 이 정보를 사용한다. 만약 프로젝트마다 다른 이름과 이메일 주소를 사용하고 싶으면 `--global` 옵션을 빼고 명령을 생행한다.

## 1.3. 설정 확인
`$ git config --list` 명령을 실행하면 설정한 모든 것을 보여준다.

````
$ git config --list
user.name=KinHyeongJae
user.email=sirius6321@naver.com
color.status=auto
color.branch=auto
color.interactive=auto
coor.diff=auto
...
````

# 2. Git의 기초
## 2.1. add
`$ git add <filename> <options>`
### 2.1.1 option
1. -n | --dry-run

	`add할 파일이 존재하는지 여부 확인, 실제로 add는 실행되지 않는다.`

2. -v | --verbose

	`?`

3. -f | --force

	`ignore 파일까지 모두 add가 실행된다.`

4. -e | --edit

	`해당 파일이 편집상태가 되며 편집된 상태로 add가 실행된다. 기존 파일 기준으로 diff가 발생한다.`

5. -u | --update

	`modified 된 파일만 add가 실행된다. newfile은 add가 실행되지 않는다.`

