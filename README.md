회사 업무에 도움이 되는 pcre_regex 정규표현식 정리를 합니다.
```
PCRE는 "Perl-Compatible Regular Expressions"의 약어로,
강력한 정규 표현식을 지원하는 프로그래밍 언어인 Perl의 기능을 다른 프로그래밍 언어나 도구에서도 사용할 수 있게 해주는 라이브러리를 의미합니다.
정규 표현식은 특정 패턴을 표현하는데 사용되며, 텍스트 처리, 검색, 추출, 치환 등 다양한 작업에 유용합니다. 
```
snort rule 에서 PCRE 를 사용하고 확인하는데요
복잡한 규칙이 많이 있어 검증을 하기 위해 특정 사이트들을 주로 이용합니다.

정규표현식 자체가 CRLF를 허용하지 않아서 한줄에 다적어야 한다.
```
CRLF 란CR :
Carriage Return (\r) : 현재 라인에서 커서의 위치를 가장 앞으로 옮기는 동작을 의미합니다
LF : Line Feed (\n) :  약자로 커서의 위치는 그대로 두고 종이를 한 라인 위로 올리는 동작을 의미합니다.

이 방식(CR + LF)은 타자기 이후 컴퓨터에서도 줄바꿈을 의미할 때도 사용되었으나,
줄바꿈을 할 때 굳이 2 byte 를 사용할 필요가 없기에 메모리/Storage 절약을 위해 CR 혹은 LF 만 사용하기도 하였다.
대표적으로 Microsoft 사의 Windows 는 CRLF (\r\n) 을 기본으로 사용하는
반면  Unix/Linux 에서는 LF (\n) 만으로 줄바꿈을 하고 있다. (Mac 의 초기 버전, 9 버전 이하는 CR (\r) 을 줄바꿈으로 사용)
좀 더 명확히 얘기하자면 해당 시스템에서 사용하는 default (기본) 방식이 그렇다는 것이지 반드시 해당 시스템에서는 해당 방식을 사용해야한다는 것은 아니다.
아래와 같이 application에서 적절히 처리할 수 있다. 
```
주로 프로그래밍 언어나 문서편집기 등에서 쓰이는 것 같은데 회사에서 snort 룰 설정에 정규표현식하는 업무가 필수적이라 꼭 알아둬야한다..

