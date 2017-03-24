# Setup Development Environment

이번 챕터에서는 C언어를 사용하기 위한 개발 환경을 세팅하는 방법을 다룹니다.

본 문서에서는 통합 개발 환경\(IDE, Integrated Development Environment\) e.g. Visual Studio, Clio 등, 을 사용하지 않고 GCC 컴파일러와 텍스트 에디터\(Sublime Text\)를 사용하여 개발하는 것을 기본으로 합니다.

### Download

**Sublime Text: **[**https://www.sublimetext.com/**](https://www.sublimetext.com/)![](/assets/sublime.png)

### Syntax Highlight

Sublime Text를 설치하였으면, Syntax Highlight를 사용하는 방법을 배워보도록 하겠습니다.

C언어로 Syntax Highlight를 하는 방법에는 여러가지 방법이 있습니다.

![](/assets/defalut.png)

위 사진은 Syntax Highlight가 적용되지 않은 상태입니다. 일반 메모장과 같은 상태로, C언어 문법에 맞지 않게 아무런 강조표시가 없습니다.

1. **확장자를 .c 파일로 저장하기**![](/assets/savetocfile.png)확장자를 .c파일로 저장한 상태입니다.  첫 번째 사진과는 다르게 C언어 문법에 맞춰서 색깔로 구문이 강조된 것을 확인 할 수 있습니다.
2. **Command Palette이용하기**![](/assets/command.png)Command Palette는 Mac에서는 \(Cmd + Shift + P\), Windows에서는 \(Ctrl + Shift + P\) 단축키로 실행할 수 있습니다. Command Palette에서 ssc \(Set Syntax: C\)의 약자를 입력한 뒤, 선택을 해주면 C언어로 구문강조가 된 것을 확인 할 수 있습니다.
3. **언어 선택 창에서 선택하기 **![](/assets/select.png)마지막 방법은 언어 선택 창을 이용하는 방법입니다. 우측 하단에 Plain Text라고 써있는 부분 \(이미지 상에서는 C\)을 클릭하면 강조 구문을 할 수 있는 언어들의 리스트가 나오게 됩니다. 리스트 중 C를 선택하게 되면, C언어 맞춰서 구문 강조가 됩니다.

### Compile

다음으로는 컴파일을 하는 방법을 배워보도록 하겠습니다. Sublime Text는 컴파일 단축키를 지원합니다. Mac의 경우에는 \(Cmd + B\), Windows의 경우에는 \(Ctrl + B\)를 누르면 자동으로 컴파일이 이뤄지고, 컴파일 결과 값이 콘솔창에 출력됩니다.![](/assets/compile.png)

