# Translation project of XBlocks
본 프로젝트에서는 번역 플랫폼 Transifex에 등록되어있는 [XBlocks 프로젝트](https://www.transifex.com/open-edx/xblocks/dashboard/) 전체를 영어에서 한국어(ko_KR)로 번역한다.

## 번역 방법
해당 프로젝트의 .po파일(GNU gettext 시스템 등에 사용되는 text-based 파일)을 다운로드 받아 텍스트 에디터로 수정 한 뒤,
번역한 파일을 업로드하여 프로젝트에 반영한다. 번역 할 때마다 상시 업데이트를 원칙으로 한다.

## 프로젝트 진행 전 번역 현황
<img src="https://user-images.githubusercontent.com/75475398/101598438-81cb5500-3a3b-11eb-8a65-5afe9756c4fe.PNG" width="70%" height="70%"> 
<img src="https://user-images.githubusercontent.com/75475398/101598444-82fc8200-3a3b-11eb-9b23-f93dbe245b62.PNG" width="70%" height="70%"> 

총 876 string, 6288 word로 구성된 프로젝트이다. 본 프로젝트를 진행하기 전 716개의 번역되지 않은 한국어 string이 존재했으며, 이 중 166개의 string은 평가받지 않은 상태였다.

## PO File 문법
본 프로젝트는 .po 파일 형식을 사용하여 진행된다. PO 파일 작성에 사용되는  기초적인 문법은 다음과 같다.
```
#: src/main.py:340      #.1
msgid "plural"          #.2
msgid_plural "plurals"  #.3
msgstr[0] "1 plural"    #.4
msgstr[1] "%d plurals"  #.5
```
1번 줄은 번역할 문자열이 담긴 경로를 포함한다. 2번째 줄에서 "plural"이라는 문자열에 대해 번역함을 알 수 있으며, 3번째 줄은 "plural"에 대한 복수형 문자열인 "plurals"도 같이 번역해야 함을 알 수 있다.

4, 5번째 줄은 각각 단일, 복수형에 대한 번역 문자열을 포함한다. 주의할 점은 이 때 수를 나타내는 부분, 즉 1, %d와 같은 부분 이외의 부분이 정확히 일치하게 번역 된다면 두 개의 msgstr이 아닌 하나의 msgstr[0]으로 작성해야 한다. 이를 코드 형식으로 나타내보면 다음과 같다.
```
msgid "You answered 1 question incorrectly.\n"
msgid_plural "You answered %(incorrect_answers)s questions incorrectly.\n"
msgstr[0] "당신은 %(incorrect_answers)s개의 문제를 틀렸습니다.\n"
```
위와 같이 작성하지 않고 두 개의 msgstr로 작성한다면 Transifex 웹으로 파일을 업로드 할 때 복수형을 인식하지 못하는 오류가 생긴다. 따라서 이 부분에 유의하여 복수형 번역을 진행해야 한다.

## 용어사전(Glossary)
TTA 정보통신 용어사전, KS용어사전, 국립국어원 대사전에 등록된 단어들을 이용해 번역한다. 문맥 상 추가적인 다른 번역이 필요할 경우, 오픈소스SW 공용 논의 파일에
단어를 등록하여 논의한다.

* [TTA정보통신용어사전](http://word.tta.or.kr/main.do)
* [KS용어사전](https://standard.go.kr/KSCI/dictionary/getDictionaryList.do?menuId=60401&topMenuId=558&upperMenuId=558)
* [국립국어원대사전](https://stdict.korean.go.kr/main/main.do)
* [오픈소스SW 논의 파일](https://docs.google.com/spreadsheets/d/1Pxd9y3i8nQHrVwfhQPu-YgTATxsXnGr00-B1Hc5H0lY/edit?usp=sharing)

프로젝트 진행에 지속적으로 참고해야할 단어들은 [standrad_translation.txt](https://github.com/SeungheonShin/Transifex-XBlocks/blob/main/standard_translation.txt) 파일에 기록하여 이후 번역에 참고한다.

## 번역 규칙
본 프로젝트는 다음과 같이 정한 규칙을 따라 번역하며, 예외적인 부분(문맥 상 특수한 다른 뜻이 필요할 경우 등) 발생 시 commit comment에 작성 후 예외 항목에서 추가적인 규칙을 다룬다.


* 평서문: 해당 API(XBlocks)가 학습을 위해 만들어진 교육 플랫폼에 사용되므로 이를 고려하여 경어체(~합니다, ~하세요)로 번역한다. 
```
msgid "Drag the items onto the image above."
msgstr "사진 위로 항목을 끌어다 놓으세요."
```
* 의문문: 경어체(~합니까?)를 사용한다.
```
msgid "Display the title to the learner?"
msgstr "학습자에게 제목을 표시합니까?"
```
* 명령문: 특정 행동에 대한 설명을 할 때 명령문이 사용되므로 '~하기'로 번역하여 사용자가 자연스럽게 이해할 수 있도록 한다.
```
msgid "Show Answer"
msgstr "정답 보기"
```
## 번역 규칙-예외
* 문장이 마침표로 끝나지 않는 경우 경어체가 아닌 '~함' 또는 명사로 번역한다.
```
msgid "Correctly placed in: {zone_title}"
msgstr "{zone_title}에 알맞게 배치되어 있음"
```
* 문장이 어떤 기능에 대한 설명인 경우 마침표로 끝나지 않더라도 '~합니다'라고 번역하여 사용자가 설명을 자연스럽게 이해하도록 한다.
```
msgid "Toggles if numeric values are displayed"
msgstr "숫자로 된 값이 표시되는 지의 여부를 전환합니다"
```
## 프로젝트 진행 후 결과

## 문제점
Transifex 시스템 특성 상 Admins, Project Maintainers, Language Coordinators, Reviewers 만이 번역에 대한 평가에 관여할 수 있다. 따라서 원래 프로젝트의 목적 중 하나였던 166개의 미평가 string에 대한 평가를 진행하지 못했다. 후에 관리자에게서 reviewer 권한을 습득한다면 다시 진행할 수 있을 것이다.

## Contact
신승헌 - gody8756@ajou.ac.kr

Project link: https://github.com/SeungheonShin/Transifex/

XBlocks-Transifex: https://www.transifex.com/open-edx/xblocks/dashboard/

## Reference
* [PO file format - Transifex](https://docs.transifex.com/formats/gettext)
