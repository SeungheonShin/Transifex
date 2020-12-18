# Translation project of XBlocks
본 프로젝트에서는 번역 플랫폼 Transifex에 등록되어있는 XBlocks 프로젝트 전체를 영어에서 한국어(ko_KR)로 번역한다.

## 번역 방법
해당 프로젝트의 .po파일(GNU gettext 시스템 등에 사용되는 text-based 파일)을 다운로드 받아 텍스트 에디터로 수정 한 뒤,
번역한 파일을 업로드하여 프로젝트에 반영한다. 번역 할 때마다 상시 업데이트를 원칙으로 한다.

## 프로젝트 진행 전 번역 현황
<img src="https://user-images.githubusercontent.com/75475398/101598438-81cb5500-3a3b-11eb-8a65-5afe9756c4fe.PNG" width="70%" height="70%"> 
<img src="https://user-images.githubusercontent.com/75475398/101598444-82fc8200-3a3b-11eb-9b23-f93dbe245b62.PNG" width="70%" height="70%"> 

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
## Contact
신승헌 - gody8756@ajou.ac.kr

Project link: https://github.com/SeungheonShin/Transifex/


## Reference
* [PO file format - Transifex](https://docs.transifex.com/formats/gettext)
