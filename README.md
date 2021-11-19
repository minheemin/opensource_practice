# opensource_practice 
오픈소스 1번째 과제입니다.

## 쉘스크립트 명령어

**getopt**

명령어 라인에 입력으로 옵션이 조합으로 입력되는 경우가 있다.
예를 들면 ls –l 과 같이 옵션이 여러 개 붙여서 쓰는 경우가 많은데 이 경우에 스크립트 상에서는 처리가 되지 않는다. 
이럴 경우 유용한 명령어가 getopt 이다.

$getopt option optstring parameter
 optipn에 사용할 옵션들을 나열하고 콜론으로 구분을 해 준 다음 optstring에 사용할 옵션들과 파라메터를 정의해 주면 된다. 

**getopts**
getopt 명령어는 발견된 모든 처리 된 옵션 및 매개변수에 대해 하나의 출력을 생성하지만 이와 달리 getopts 명령은 기존 쉘에서 파라메터들을 순차적으로 처리 한다.

$getopts optstring variable
optstring에 유요한 옵션문자들을 나열한다.
그리고 이 옵션들이 파라메터값을 필요로 하는 경우 콜론으로 구분을 한다. 그리고 getopt 명령에서 –q옵션과 같이 에러 메시지를 없애기 위해 콜론으로 시작한다.

getopts 는 2개의 환경변수를 허용한다. 그 중 하나는 OPTARG 변수이고 이 변수는 옵션의 파라메터로 사용되는 값을 저장한다. OPTIND 변수는 파라메터 리스트에서 getopts가 떠난 위치를 저장해 준다.
이 변수 값을 사용해서 처리 후 다시 마지막 위치로 돌아와 다음 파라메터를 처리한다.


## 리눅스 명령어

**sed**

ed 명령어와 grep 명령어 기능의 일부를 합친 것이 sed(stream editor)명령어 이다.
sed 명령어도 grep 명령어와 같은 필터이지만 이 명령어는 파일을 수정할 수 있게 하는 반명 ed처럼 대화식 처리는 불가능 하다. sed 명령어는 1개의 라인을 읽어들여 표준 출력으로 출력한다.

sed는 각 라인을 읽을 때 마다 ed에서 사용하던 형식의 대치 작업을 실행한다. 일치하는 문자열이 있으면 그 문자열을 대치한 후 출력하고 일치하는 문자열이 없으면 그 라인을 수정되지 않고 그대로 출력된다.

이 sed 명령어가 ed보다 좋은 점은 은 라인들을 하나씩 읽고, 수정하고, 출력하기 때문에 기억장치 안의 버퍼를 사용하지 않는다는 것이다. 버퍼를 사용하지 않으면 파일의 크기에 제한 없이 작업을 할 수 있다. ed와 같이 버퍼를 사용하는 경우는 버퍼의 크기보다 큰 파일은 처리할 수 없으며 대개 버퍼의 크기는 1MB정도이다. 따라서 sed는 아주 큰 파일을 처리할 때 주로 사용된다.

sed 명령어를 호출하는 형식은 grep명령어와 같지만 완전한 형식의 대치 연산자를 사용한다는 점만이 다르다.

**1. 치환**
sed 's/addrass/address/' list.txt : addrass를 address로 바꾼다. 단, 원본파일을 바꾸지 않고 표준출력만 한다.

sed 's/\t/\ /' list.txt : 탭문자를 엔터로 변환

**2. 삭제**
sed '/TD/d' 1.html : TD 문자가 포함된 줄을 삭제하여 출력한다.
sed '/Src/!d' 1.html : Src 문자가 있는 줄만 지우지 않는다.
sed '1,2d' 1.html : 처음 1줄, 2줄을 지운다.
sed '/^$/d 1.html : 공백라인을 삭제하는 명령이다.


**awk**

텍스트 파일에서 특정 문자의 패턴을 추출하여 원하는 포맷으로 처리하는 명령어
필드단위로 패턴을 검색

**시용법**
awk [-f 프로그램 파일][-F 필드 구분자][“패턴{액션}”][처리할 파일명]

-f 프로그램 파일
: awk 유틸리티의 실행 액션이 저장된 프로그램 파일을 지정

-F 필드 구분자
:필드 구분자를 지정

“패턴{액션}”
:패턴이 일치하면 액션이 실행된다


