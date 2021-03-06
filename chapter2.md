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

이미지 우측 상단에 보면 `+` 기호의 버튼이 있는데, 그 버튼을 클릭한 뒤 `New Repository`까지 클릭합니다.

![](/assets/chapter2/create_repo.png)

`Repository Name`에는 해당 프로젝트 제목을 기입합니다. 이 프로젝트 제목이 나중에는 이 `Repository`로 접속하는 URL로 사용되니, 깔끔한 제목으로 선정해주는 편이 좋습니다. (추후에 Rename 가능) Description에는 간단한 설명을 추가적으로 작성합니다.

`Github`는 public Repository에 대해서는 얼마든지 무료지만, 자신만 보고싶은 private Repository는 과금을 해야합니다. 우리는 여기서 public한 Repository로 체크를 한 뒤, **Initialize this repository with a README** 체크박스에 체크를 해주시기 바랍니다.

> README는 나중에 만들어도 되지만, README를 기본적으로 생성할 경우에는 바로 Repository를 Clone할 수 있어 간편합니다.

![](/assets/chapter2/test.png)

자 첫 Repository가 완성되었습니다. 이제 이 Repository를 로컬 환경과 온라인 환경을 연결하는 방법을 배워보도록 하겠습니다.


## Install git :: git 설치하기

**Mac OS:** 기본적으로 설치 되어 있음

**Windows:** <https://git-for-windows.github.io/>

기본적으로 `git`은 `Mac OS`환경에서는 기본적으로 설치되어있으며, `Windows`환경에서는 위의 링크를 통하여 설치하도록 합니다.
```
$ git
```
`git`이 정상적으로 설치되었다면, 터미널상에 `git`이라고 입력했을 때 `git`에 대한 기본적인 명령어들의 리스트가 나오게 됩니다.

![](/assets/chapter2/git.png)

### git conifg :: 사용자 정보 설정
`git`을 설치하고나서 가장 먼저 해야할 일은 사용자 정보를 설정하는 일 입니다. 이 정보는 `commit`을 할 때 사용됩니다.

> Commit에 대한 이야기는 밑에서 다룰 예정이니, 너무 겁먹지는 말자.

```
$ git config --global user.name "nayunhwan"
$ git config --global user.email youremail@example.com
```

위와 같이 앞서 만들어놓은 `Github`계정 정보와 동일하게 일치시켜주면 됩니다.

### git clone :: Github으로 부터 로컬로 복사하기
아까 위에서 `Github`를 통해 만든 Repository를 `clone` 해보도록 하겠습니다. clone하는 방법은 매우 간단합니다.

```
$ git clone github_repository_url
```

![](/assets/chapter2/git.png)

이렇게 하면 해당 url에 있는 Repository의 파일들이 로컬로 복사됩니다.

### Github에 로컬 파일들 업로드하기
로컬 환경에 있는 것을 원격 저장소(e.g. Github)로 업로드 하는 것을 `push` 한다고 합니다. 그리고 `push` 이전에는 어떤 파일들의 변화를 추가 할지를 명령하는 `add`, 그리고 현재 버전의 기록을 남기는 작업인 `commit`명령어가 있습니다.

이 명령어들의 작업 순서대로 나열해보면, `add` -> `commit` -> `push` 순으로 이뤄지게 됩니다.

예를 들어서 Readme.md 파일을 수정한다고 가정합니다.

![](/assets/chapter2/before.png)

![](/assets/chapter2/after.png)

위와 같이 수정 한 뒤,

```
$ git add .
$ git commit -m "First Commit Message"
$ git push origin master
```
> add 뒤에 . (온점)은 해당 디렉토리의 하위 디렉토리 파일들까지 모두 변경사항을 감지해서 추가하겠다는 이야기 입니다. 만약, 하나의 파일의 변경사항만 추가하고 싶다면 add 뒤에 파일 이름을 붙여주면 됩니다.

![](/assets/chapter2/push.png)

이렇게 업로드가 정상적으로 되면, 성공한 것입니다. 이제 `Github`의 Repository로 돌아가면, 수정된 내역이 제대로 반영된 것을 확인 할 수 있습니다.

![](/assets/chapter2/result.png)
