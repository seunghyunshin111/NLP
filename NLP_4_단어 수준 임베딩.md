## 단어 수준 임베딩

- 예측prediction 기반 모델
  - NPLM, Word2Vec, FastText
- 가중 임베딩Weighted Embedding
  - 단어 임베딩을 문장 수준으로 확장하는 방법

<br>

- ### NPLM

  - Neural Probabilistic Language Model
  - 자연어 처리 분야에 임베딩 개념을 널리 퍼뜨리는 데 일조한 선구자적 모델

  <br>

  ## 기존 언어 모델의 단점

  - 학습 데이터에 존재하지 않는 n-gram이 포함된 문장이 나타날 확률 값을 0으로 부여

  - 물론 백오프back-off나 스무딩smoothing으로 이런 문제를 일부 보완할 수 있지만 완전한 것은 아님
  - 문장의 장기 의존성long-term dependency을 포착해내기 어렵다. (Ex. n-gram의 n을 5 이상으로 길게 설정할 수 없다. n이 커질수록 그 등장 확률이 0인 단어 시퀀스가 기하급수적으로 늘어난다.)
  - 단어/문장 간 유사도를 계산할 수 없다.

  <br>

- ### NPLM은 이러한 기존 언어 모델의 한계를 극복한 언어 모델이라는 점에서 의의가 있다.

- ### NPLM 자체로 단어 임베딩 역할을 수행할 수 있다.

<br>

- ### Word2Vec

  - Milolov et al. (2013a)이 제안한 CBOW와 Skip-gram 모델. 이 두 모델을 근간으로 하되 네거티브 샘플링negative sampling 등 학습 최적화 기법을 제안한 내용이 핵심
  - **CBOW**는 주변에 있는 문맥 단어context word들을 가지고 타깃 단어target word 하나를 맞추는 과정에서 학습된다.
  - CBOW 쌍 pair: {문맥 단어 4개, 타깃 단어}

  <br>

  - **Skip-gram 모델**은 타깃 단어를 가지고 주변 문맥 단어가 무엇일지 예측하는 과정에서 학습된다.
  - Skip-gram의 학습 데이터: {타깃 단어, 타깃 직전 두 번째 단어}, {타깃 단어, 타깃 직전 단어}, {타깃 단어, 타깃 다음 단어}, {타깃 단어, 타깃 다음 두 번째 단어} 이렇게 4개쌍이 된다.
  - Skip-gram이 같은 말뭉치로도 더 많은 학습 데이터를 확보할 수 있어, 임베딩 품질이 CBOW보다 좋은 경향이 있다.

<br>

- ### Skip-gram 모델을 중심으로 한 "Word2Vec" 기법

  - 포지티즈 샘플positive sample: 타깃 단어(t)와 그 주변에 실제로 등장한 문맥 단어(c) 쌍을 가리킨다.
  - 네거티브 샘플negative sample: 타깃 단어와 그 주변에 등장하지 않은 단어(말뭉치 전체에서 랜덤 추출) 쌍을 의미한다.
  - 윈도우window를 2로 설정: 포지티브 샘플을 만들 때 타깃 단어 앞뒤 두 개씩만 고려한다는 뜻

  <br>

- ## FastText

  - 각 단어를 문자character 단위 n-gram으로 표현한다. 이 밖의 내용은 Word2Vec와 같다.

