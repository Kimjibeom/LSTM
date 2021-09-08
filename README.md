# LSTM

LSTM
- LSTM (Long Short Term Memory)는 기존의 RNN이 출력과 먼 위치에 있는 정보를 기억할 수 없다는 단점을 보완하여 장/단기 기억을 가능하게 설계한 신경망의 구조를 말합니다. 주로 시계열 처리나, 자연어 처리에 사용된다.

LSTM cell
- LSTM도 RNN과 같은 체인 구조로 되어 있지만, 반복 모듈은 단순한 한 개의 tanh layer가 아닌 4개의 layer가 서로 정보를 주고받는 구조로 되어 있습니다. LSTM 셀에서는 상태(state)가 크게 두 개의 벡터로 나누어집니다. ht를 단기 상태(short-term state),  ct를 장기 상태(long-term state)라고 볼 수 있습니다.

1. Cell state
  - Cell state는 정보가 바뀌지 않고 그대로 흐르도록 하는 역할입니다.
![LSTM3-chain](https://user-images.githubusercontent.com/73589723/132471353-29d9498d-0df2-42b5-959f-49544463c723.png)

