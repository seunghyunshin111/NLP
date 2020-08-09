# NLP Process

- 랭킹 분류로 '점수'를 통해 긍부정을 판단한다.
- 맞춤법 검사 정말 잘 안 된다.
- 어려운 프로젝트는 안 된다.
- 질의응답: 챗봇
- STT 데이터 
- NLP Process는 무조건 5단계
  - 데이터 컬렉션(크롤링)
  - 토크나이즈(Konlpy, Mecab, Khaii)
  - 임베딩(워드투벡, GloVe, FastText, BERT)
  - Similarity(Euclidean, Cosine, Jaccard): 얼마나 잘 임베딩이 되었는지 확인(선택인지만, 강사는 가장 중요하다고 생각)
  - Modeling(RNN< LSTM)
- Document(댓글 등 센텐스의 모음), Sentence문장, token(사과, 가 등으로 잘랐어.) Corpus(도큐먼트들의 모음; 말뭉치)
- 임베딩: 컴퓨터가 알아들을 수 있는 숫자로 변환



## 임베딩

- Representations
- 비정형 데이터를 정형 데이터로 바꾸는 작업
- 이후는 머신러닝 분석과 같아진다.
  - 조사, 특수문자, 숫자(특수문자의 경우 감성 분석 ㅡㅡ, - _-, 숫자가 중요한 데이터의 경우 주의. task마다 다를 수밖에 없다.)
- Stop Wording은 해야 한다.
  - 중요한 의미를 포함하지 않는 Word를 삭제하는 것
  - 조사, 접속사 등을 삭제하면 성능이 개선된다. (Feature Selection의 관점)
  - 쓸모없는 피쳐 넣으면 성능이 떨어진다.
- 도큐먼트->임베딩 (임베딩하는 경우 크게 2가지)
  - 워드 단위로 임베딩하는 경우 (cf. 센텐스로 임베딩하는 경우)
  - 도큐먼트 단위로 임베딩 하는 경우
- Bag of words
  - TDM (바이너리 TDM, 있으면 1, 없으면 0)
    - Row: Word, columns: document
    - 임베딩, 워드, 도큐먼트로 임베딩 하는 방법 모두를 합침
  - TF (갯수)
    - 위와 동일, Value: 갯수
- IDF: 희소한 값에 가중치를 더 준다.
- DF: 단어t가 등장하는Documents의 개수

<br>

## Similarity

- 코사인 유사도: 벡터

  -1 ~ 1 사이 값

  