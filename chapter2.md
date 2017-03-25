# How to use Git and Github

이번 챕터에서는 `Git`과 `Github`의 사용법에 대해서 다룹니다.

쉽게 이야기한다면, `git`은 프로그램의 버전을 관리하기 위해서 만들어진 툴이고, 이러한 `git`을 온라인 상에 업로드하여 프로젝트로 관리, 이슈 등록, 협업 등 다양한 활동을 할 수 있는 곳이 바로 `Github`입니다. `git`과 `Github`의 모든 기능을 설명하기에는 복잡하지만, 이번 챕터에서는 내가 파일을 `git`을 통해 버전관리를 할 수 있도록하는 기본 적인 명령어와, 만들어진 `git`을 가지고 `Github`에 업로드하여 코드를 백업하는 방법을 다룰 것입니다.

## Sign Up for Github

Github Link: <https://github.com>

앞으로 개발자라면 혹은 컴퓨터 공학도라면, 컴퓨터 공학도가 아닐지라도 SW쪽으로 진출할 생각이 있다면 이 Github이라는 서비스는 앞으로 계속 자주 보게 될 것이다.

![](/assets/chapter2/github.png)

미리 가입을 해두고, 빨리 이 환경에 익숙해지는 편이 앞으로 프로젝트를 진행하는 데 있어서 많은 도움이 될 것이다.
웹서비스 내에 있는 `Sign up for Github` 버튼을 이용해 간단히 가입할 수 있다.

## Create New Repository

`Github`에 가입하고 나서 가장 먼저 할 수 있는 일은 바로 새로운 `Repository`를 생성하는 것 입니다. 쉽게 이야기하면, 하나의 프로젝트 폴더를 생성한다고 이해하는 편이 쉬울 겁니다. 저 Repository가 앞으로 여러분이 힘들게 짠 코드들이 백업될 공간이고, 추후에는 다른 사람들과 협업할 수 있도록 도와주는 공간입니다.

![](/assets/chapter2/new_repo.png)

## Install git

**Mac OS:** 기본적으로 설치되어 있음

**Windows:** <https://git-for-windows.github.io/>

기본적으로 `git`은 `Mac OS`환경에서는 기본적으로 설치되어있으며, `Windows`환경에서는 위의 링크를 통하여 설치하도록 합니다.
```
$ git
```
`git`이 정상적으로 설치되었다면, 터미널상에 `git`이라고 입력했을 때 `git`에 대한 기본적인 명령어들의 리스트가 나오게 됩니다.

![](/assets/chapter2/git.png)

### git conifg 사용자 정보 설정
`git`을 설치하고나서 가장 먼저 해야할 일은 사용자 정보를 설정하는 일 입니다. 이 정보는 `commit`을 할 때 이 정보를 사용한다.

> Commit에 대한 이야기는 밑에서 다룰 예정이니, 너무 겁먹지는 말자.

```
$ git config --global user.name "nayunhwan"
$ git config --global user.email youremail@example.com
```

위와 같이 앞서 만들어놓은 `Github`계정 정보와 동일하게 일치시켜주면 된다.
