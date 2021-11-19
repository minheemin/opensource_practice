# opensource_practice 
오픈소스 1번째 과제입니다.

## 쉘스크립트 명령어

**getopt**

명령어 라인에 입력으로 옵션이 조합으로 입력되는 경우가 있다.
예를 들면 ls –l 과 같이 옵션이 여러 개 붙여서 쓰는 경우가 많은데 이 경우에 스크립트 상에서는 처리가 되지 않는다. 
이럴 경우 유용한 명령어가 getopt 이다.

$getopt option optstring parameter
 optipn에 사용할 옵션들을 나열하고 콜론으로 구분을 해 준 다음 optstring에 사용할 옵션들과 파라메터를 정의해 주면 된다. 

