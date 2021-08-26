## 자연어 처리

> [konlpy사이트](https://konlpy.org/ko/latest/)

### NLP란 무엇인가요?

NLP (Natural Language Processing, 자연어처리)는 텍스트에서 의미있는 정보를 분석, 추출하고 이해하는 일련의 기술집합입니다.

우리 일상에도 다양한 NLP 응용사례가 있습니다. 가령:

- 텍스트 요약 (ex: [Summly](http://www.summly.com/index.html))
- 대화 시스템 (ex: [Apple Siri](https://www.apple.com/ios/siri/))
- 기계 번역 (ex: [Google Translate](http://translate.google.com/))

그리고 물론, 검색엔진과 같은 정보검색 시스템 등이 있습니다. NLP의 기초에 대해 더 자세히 알기 위해서는 아래 책들을 참고하시기 바랍니다.

- Jurafsky et al., [Speech and Language Processing](https://www.goodreads.com/book/show/908048), 2nd Edition, 2008.
- Manning and Schutze, [Foundations of Statistical Natural Language Processing](https://www.goodreads.com/book/show/776349), 1999.

KoNLPy는 여러분이 한국어 텍스트를 이용하여 기초적인 NLP 작업을 수행하는데 도움을 드릴 것입니다. 영어 텍스트를 다루는 것에 관심 있으신 경우, [NLTK](http://nltk.org/) 를 참고해주시기 바랍니다.

### 이제 무엇을 준비하면 되나요?

KoNLPy를 사용하기 전에 다음의 몇 가지 준비가 필요합니다.

1. 언어에 대한 깊은 관심과 한국어에 대한 어느 정도의 이해
2. 기본적인 파이썬 프로그래밍 방법 [[1\]](https://konlpy.org/ko/latest/start/#id3)
3. 좋은 텍스트 에디터와 터미널 (또는 파이썬 IDE) [[2\]](https://konlpy.org/ko/latest/start/#id4)
4. [파이썬이 설치된 컴퓨터](https://wiki.python.org/moin/BeginnersGuide/Download)
5. 파이썬 패키지 매니저 [pip](https://pypi.python.org/pypi/pip)

준비되셨나요? 이제 시작해봅시다.



## 환경 준비

* 파이썬 버전 확인
* jdk 설치
* C:\Program Files\Java\jdk1.8.0_301 로 복사
* 환경변수에서 JAVA_HOME 설정

* 파이참 프로젝트 만들기
* jpype 복사 붙여넣기
* pip install .\JPype1-1.1.2-cp38-cp38-win_amd64.whl
* pip install konlpy
