# Project_Uri
### 1900년도 초반부터 한국전쟁 이전까지의 소설 텍스트 자료를 기계학습을 통한 디지털 방법론으로 분석하여 우리말 표현 '우리'에 대한 연구의 새로운 방향을 제시

### 논문 링크
#### 멀리서 읽는 “우리”― Word2Vec, N-gram을 이용한 근대 소설 텍스트 분석
https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002758341

## 1. 코드설명
### 데이터 수집
1900년대 초반부터 한국전쟁 이전까지의 소설(신소설, 소설, 평론 등) 텍스트를 **위키문헌**에서 수집  
위키데이터 https://dumps.wikimedia.org/kowikisource/

### 1) 전처리
#### xml 파싱
위키문헌에서 xml형식의 파일로 수집한 데이터에서 제목과 텍스트만 추출하는 Parsing 진행
wikiextractor https://github.com/attardi/wikiextractor
#### 문장 분리
분석 정확도를 위해문단 형태로 분리된 위키문헌의 텍스트를 kss 한글 문장 분리기를 통해 문장 단위로 분리
kss 한글 문장 분리기 https://docs.likejazz.com/kss/
#### 형태소 분석
텍스트 중에 다의어나 동음이의어를 품사로 구분하여 정확한 분석을 하기 위한 형태소 분석을 진행
키위 형태소 분석기  https://github.com/bab2min/Kiwi


### 2) N-Gram
N-gram은 일종의 연어로 연속으로 출현하는 음절들을 분석하여 '우리'라는 단어가 어떤 단어와 빈번하게 쓰이는지 확인
NLTK_collocation https://www.nltk.org/howto/collocations.html

### 3) Word2Vec

Gensim https://radimrehurek.com/gensim/models/word2vec.html

### 2. 기술 통계량

|시대|작품 수|문장 수|'우리' 포함 문장|'저희'포함 문장|
|---|:---:|:---:|:---:|:---:|
|전체|585|312,131|6,473|327|
|E1(~1919)|33|28,803|673|32|
|E2(1920~1945)|524|236,120|4,690|219|
|E3(1945~)|28|47,208|1,110|76|

#### 시대 분류
##### E1 : 1919년 이전의 소설(산문) 작품
##### E2 : 1919년부터 1945년까지의 소설(산문) 작품
##### E3 : 1945년 이후의 소설(산문) 작품

### 3. 저자

- 서재현 (성균관대학교 유학동양한국철학과 박사과정)
- 김병준 (성균관대학교 인터랙션사이언스학과 박사수료, https://github.com/ByungjunKim)
- 김민우 (성균관대학교 인간AI인터랙션융합전공 석사과정)
- 박소정 (성균관대학교 유학동양한국철학과 교수)
