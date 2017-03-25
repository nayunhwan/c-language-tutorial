# How to use Git and Github

이번 챕터에서는 `Git`과 `Github`의 사용법에 대해서 다룹니다.

쉽게 이야기한다면, `git`은 프로그램의 버전을 관리하기 위해서 만들어진 툴이고, 이러한 `git`을 온라인 상에 업로드하여 프로젝트로 관리, 이슈 등록, 협업 등 다양한 활동을 할 수 있는 곳이 바로 `Github`입니다. `git`과 `Github`의 모든 기능을 설명하기에는 복잡하지만, 이번 챕터에서는 내가 파일을 `git`을 통해 버전관리를 할 수 있도록하는 기본 적인 명령어와, 만들어진 `git`을 가지고 `Github`에 업로드하여 코드를 백업하는 방법을 다룰 것입니다.

## Install Git

**Mac OS:** 기본적으로 설치되어 있음

**Windows:** <https://git-for-windows.github.io/>

기본적으로 `git`은 `Mac OS`환경에서는 기본적으로 설치되어있으며, `Windows`환경에서는 위의 링크를 통하여 설치하도록 합니다.
```
$ git
```
`git`이 정상적으로 설치되었다면, 터미널상에 `git`이라고 입력했을 때 `git`에 대한 기본적인 명령어들의 리스트가 나옵니다.

![](/assets/chapter2/git.png)

### 사용자 정보 설정
`git`을 설치하고나서 가장 먼저 해야할 일은 사용자 정보를 설정하는 일 입니다. 이 정보는 `commit`을 할 때 이 정보를 사용한다.

> Commit에 대한 이야기는 밑에서 다룰 예정이니 지금부터 너무 겁먹지 말자

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
