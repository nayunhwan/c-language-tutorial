# How to use Sublime Text

이번 챕터에서는 C언어를 사용하기 위한 `Sublime Text`에 대한 기본적인 사용 방법에 대해서 다룹니다.

본 문서에서는 통합 개발 환경\(IDE, Integrated Development Environment\) e.g. Visual Studio, Clio 등, 을 사용하지 않고 GCC 컴파일러와 텍스트 에디터\(Sublime Text\)를 사용하여 개발하는 것을 기본으로 합니다.

본 문서는 Mac OS를 기반으로하여 작성되었습니다. 따라서 Terminal 명령이나, 그래픽 인터페이스는 Windows와 다를 수 있습니다.

### Download

**Sublime Text: **[**https://www.sublimetext.com/**](https://www.sublimetext.com/)![](/assets/chapter1/sublime.png)

### Syntax Highlight

Sublime Text를 설치하였으면, Syntax Highlight를 사용하는 방법을 배워보도록 하겠습니다.

C언어로 Syntax Highlight를 하는 방법에는 여러가지 방법이 있습니다.

![](/assets/chapter1/defalut.png)

위 사진은 Syntax Highlight가 적용되지 않은 상태입니다. 일반 메모장과 같은 상태로, C언어 문법에 맞지 않게 아무런 강조표시가 없습니다.

1. **확장자를 .c 파일로 저장하기**![](/assets/chapter1/savetocfile.png)확장자를 .c파일로 저장한 상태입니다.  첫 번째 사진과는 다르게 C언어 문법에 맞춰서 색깔로 구문이 강조된 것을 확인 할 수 있습니다.
2. **Command Palette이용하기**![](/assets/chapter1/command.png)Command Palette는 Mac에서는 \(`Cmd` + `Shift` + `P`\), Windows에서는 \(`Ctrl` + `Shift` + `P`\) 단축키로 실행할 수 있습니다. Command Palette에서 `ssc` \(Set Syntax: C\)의 약자를 입력한 뒤, 선택을 해주면 C언어로 구문강조가 된 것을 확인 할 수 있습니다.
3. **언어 선택 창에서 선택하기**![](/assets/chapter1/select.png)마지막 방법은 언어 선택 창을 이용하는 방법입니다. 우측 하단에 Plain Text라고 써있는 부분 \(이미지 상에서는 C\)을 클릭하면 강조 구문을 할 수 있는 언어들의 리스트가 나오게 됩니다. 리스트 중 C를 선택하게 되면, C언어 맞춰서 구문 강조가 됩니다.


### Compile

다음으로는 컴파일을 하는 방법을 배워보도록 하겠습니다. Sublime Text는 컴파일 단축키를 지원합니다. Mac의 경우에는 \(Cmd + B\), Windows의 경우에는 \(Ctrl + B\)를 누르면 자동으로 컴파일이 이뤄지고, 컴파일 결과 값이 콘솔창에 출력됩니다.![](/assets/chapter1/compile.png)만약 컴파일 상에 오류가 있다면, 아래와 같이 오류가 있는 부분을 표시해 줍니다.![](/assets/chapter1/compile_error.png)정상적으로 컴파일이 완료 되었을 경우, .c파일의 이름과 동일한 실행파일이 생성되게 됩니다.![](/assets/chapter1/compile_done.png)

### Execute

이제 컴파일까지 마쳤으니, 파일을 실행시켜 보도록 하겠습니다. 기본적으로 .c로 컴파일된 파일은 일반적으로 실행시킬 수 없고 터미널 상에서 실행시킬 수 있습니다.

터미널에서 실행시키기 위해서는 몇가지 터미널 명령어를 알아야 합니다.

##### ls (List)

```
$ ls
```
> 맨 앞의 $ 표시는 이 코드가 터미널 쉘 상에 입력해야 한다는 뜻입니다.

> ls는 Mac OS와 Linux에서만 사용할 수 있는 명령어입니다. Windows에서는 없는 명령어이며, 비슷한 역할을 하는 명령어로는 dir 명령어가 있습니다.

![](/assets/chapter1/ls.png)

`ls` 명령어는 List의 약자압니다. ls를 입력하면, 현재 디렉토리 상에 있는 파일들을 보여줍니다.


##### mkdir (Make Directory)

```
$ mkdir 생성할_디렉토리_이름
```

![](/assets/chapter1/cd.png)

`mkdir` 명령어는 Make Directory의 약자입니다. mkdir명령어를 이용하여 새로운 폴더를 생성할 수 있습니다.


##### cd (Change Directory)

```
$ cd 이동할_디렉토리_이름
```

![](/assets/chapter1/cd.png)

`cd` 명령어는 Change Directory의 약자입니다. 예를 들어서, cd new_folder 라고 입력하면, new_folder로 이동합니다.

##### ./

```
$ ./실행할_파일_이름
```

![](/assets/chapter1/execute.png)

`./` 명령어는 파일을 실행시키는 명령어입니다. 예를 들어서 ./test 라고 입력하면, test파일이 실행됩니다. 앞서 코딩했던 `hello world`예제가 출력되는 모습을 확인 할 수 있습니다.
