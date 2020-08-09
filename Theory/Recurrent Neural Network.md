# Recurrent Neural Network

- 1 to 1은 안 씀

- one to many

  - Feature map을 flatten 시키면 마지막 것을 씀
  - 피쳐맵을 임베딩 시키다는 느낌
  - 빨간색 상자: flatten 시킨 마지막 벡터로 볼 수 있음
  - 파란색 상자: 1번째 노드가 뭔지, 2, 3번 째가 뭔지 맞추는 것

- many to one

  - 빨간색 -> 파란색

    워드가 여러개 들어와서 -> 긍/부정 하나만 아웃풋을 내는 것

- Many to many

  - 한국어 3개 -> 영어 3개

- Many to many

  - 바로 뽑아 내는 것(방법 차이)

<br>

- Xt: input

- Ht-1: 전에 있는 것에서 전달한 애

- Ht-1 * Wh = X'

- Rnn: 셀마다 가중치를 주면, 가중치가 엄청 많아지는 것이 아닌가

  - 따라서 모든 셀에 Wx, Wh는 동일하다. 모든 시점에서 동일하다

  - 즉, 파라미터 쉐어링이라고 한다.

- Backpropagation Through Time(BPTT) 

  - RNN의 역전파가 시간을 거슬러 진행
  - 모든 셀의 Wx가 후져진다.

  

  

  

  

  

  