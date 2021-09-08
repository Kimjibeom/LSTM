# LSTM

LSTM
- LSTM (Long Short Term Memory)는 기존의 RNN이 출력과 먼 위치에 있는 정보를 기억할 수 없다는 단점을 보완하여 장/단기 기억을 가능하게 설계한 신경망의 구조를 말합니다. 주로 시계열 처리나, 자연어 처리에 사용된다.

LSTM cell
- LSTM도 RNN과 같은 체인 구조로 되어 있지만, 반복 모듈은 단순한 한 개의 tanh layer가 아닌 4개의 layer가 서로 정보를 주고받는 구조로 되어 있습니다. LSTM 셀에서는 상태(state)가 크게 두 개의 벡터로 나누어집니다. ht를 단기 상태(short-term state),  ct를 장기 상태(long-term state)라고 볼 수 있습니다.

1. Cell state
  - Cell state는 정보가 바뀌지 않고 그대로 흐르도록 하는 역할입니다.
![LSTM3-chain](https://user-images.githubusercontent.com/73589723/132471353-29d9498d-0df2-42b5-959f-49544463c723.png)

2. Forget gate (삭제 게이트)
  - Forget gate는 cell state에서 sigmoid layer를 거쳐 어떤 정보를 버릴 것인지 정합니다.
![LSTM3-focus-f](https://user-images.githubusercontent.com/73589723/132472103-fef363c8-38c1-4427-b20f-77620ead0195.png)

3. Input gate (입력 게이트)
  - Input gate는 앞으로 들어오는 새로운 정보 중 어떤 것을 cell state에 저장할 것인지를 정합니다. 먼저 sigmoid layer를 거처 어떤 값을 업데이트할 것인지를 정한 후 tanh layer에서 새로운 후보 Vector를 만듭니다.
![LSTM3-focus-i](https://user-images.githubusercontent.com/73589723/132472270-9c24f93d-42b3-40d3-bcb5-2d5d5c594c22.png)

4. Cell state update
  - 이전 gate에서 버릴 정보들과 업데이트할 정보들을 정했다면, Cell state update 과정에서 업데이트를 진행합니다.
![LSTM3-focus-C](https://user-images.githubusercontent.com/73589723/132472462-dfd686e6-20ee-45a7-83c1-f9f340688c8f.png)

5. Output gate (출력 게이트)
  - Output gate는 어떤 정보를 output으로 내보낼지 정하게 됩니다. 먼저 sigmoid layer에 input data를 넣어 output 정보를 정한 후 Cell state를 tanh layer에 넣어 sigmoid layer의 output과 곱하여 output으로 내보냅니다.
![LSTM3-focus-o](https://user-images.githubusercontent.com/73589723/132472593-8c7e4d4d-5111-44c7-bf30-13cbeaccfaaa.png)
