# deep learning  



w 값은 똑같이 쓰는데 
alpha 는 하이퍼 파라미터 ==> learning rate오 ㅏ다름
즉 제약의 크기라고 ㅎㄹ 수 잇음

전첵 작아지려면 alpha 값을 키우면 w는 0에 수렴할 수 밖ㅇ없음
어느정도 가다가 멈춘거나 마찬가지 실제로는 ㅇ
그러나 w가 0에 수렴한채로.. 멈축거랑 비슷
alpha 가 0이되면 규제가 없는것과 마찬가지 
그냥 rss가 최소가 되는 점을 찾는것과같음



다항회귀에서 1-10차수까지 늘리면서 학습
1차수 일때 람다를 0-5까지 바꾸면서 하이퍼파라ㅣㅁ터 ㄴ튜닝
: 편향 분산을 줄여나가면서 

w값이 주어들면서 전체적으로 평평하게.... 윙래로 움직이는 값이 줄어드들음 
 
 w가 크다는 것은 결과값에 많은 영향  
 
알팓값을 높이니까 ㄴnox 값의 순서가 바뀌었따. ==> 
nox 데이터가 잘못들어왓다
아웃라이어가 많다거나 편향된 데잍거ㅏ 많다거나
다른 계쑤와 상관관계...가 잘못잡혓거나알
nox 값이 의미가 없게 되버림..   
분포가 많은 쪽으로 수렴  
nox의 중요도가 (가중치가) 떨어짐  
뒤바뀐 순서가 나오면 그 설명변수를 잘 보기  


ㄹ쏘 : 최소의 절대치로 줄이는 것  
norm == distance  
l1 norm 맨하탄 거리
l2 norm 유클리드  

규제르 키운마늠 0에 가까운 거리고 오게 되는 거임  
맨하탄 = 마름모 
유클리드 = 원형



ㅣ1dms a많이 키우다보면   
등고선ㅇ 0에 가까워지는 쪽으로 기울어진 모양으로 내려옫 보면
가장 먼저 선을 접하는 점이 

멀어질수록 분포가 많은 쪽으로 가는 거임  
==> 비율이 바뀔수잇음  가중치가 바뀜  
분포가 많은 쪽으로 w값을 줄여나가다 보면 점점더 영에 한없이 수렴하고 수렴할때 라인을 접하는데 그 접하는 라인이 해당 알파값을 줬을때 최적의 w값임  


결합하면
l1 l2중에 어디에 더 가중치를 둘건지'/??
엘라스틱 norm  


찌그러진 원 = 한쪽으로 치우짐  

극단적으로 갔을때 중요도가 없는 변수를 삭제하는 Featuere Selection 
정말 중요한 피쳐만 골라내는 용도  


l2 norm 은 어떻게 해도 한쪼이 작아지진 않음  
l1은 삭제 가능  


![image](https://user-images.githubusercontent.com/82145878/179431234-2fb7856d-7463-45c5-ad06-05ee2ff5ae2e.png)  
![image](https://user-images.githubusercontent.com/82145878/179431287-f88d9110-1e0b-4acc-89db-33cd7d791d5a.png)  

  
  
  
sigmoid function (Logistic regression )
0과 1로 수렴  



Decision Tree Regression  
  
  
가상으 축을 새로 만들어서 여기에 투영  
축에다가 각각의 데이터를 투영 => 이 축이 최적의 축이 되고 
하나의 더 좋은 축을 설명하게도미ㅕㄴ 다중공선성해결  
어케 컴퓨터가 자동으로 찾냐? ==> 주성분분석  

차원이 4개 -> 벡터도 4개
근데 2개로 줄이고 싶음  
가상의 축 -> 데이터들이 모임  

딥러닝.... : 차원을 줄엿다 늘렷다 반복  
학습에 의한 w값으로 차즈러 가는 과정  
뭐래?  


# 신경망을 위한 데이터 표현  
1) 스칼라(0D 텐서)  
 - 넘파이에서 float32나 float64 타입의 숫자가 스칼라 텐서  
 ```python
 import numpy as np  
 x = np.array(12)  
 x 
 x.ndim
 ```  
 
2) 벡터(1D 텐서) 
 ```python
 x = np.array([12,3,6,14,7])
 x
 x.ndim
 ```  
 
3) 행렬(2D 텐서)  
 ```python
 x = np.array([[5, 78, 2, 34, 0],
             [6, 79, 3, 35, 1], 
              [7, 80, 4, 36, 2]])
 x
 x.ndim
 ```  
 
 4) 3D 텐서  
  ![image](https://user-images.githubusercontent.com/82145878/179446395-9f7ecde3-6835-42a6-a51a-380003c287ba.png)  
  
 5) 고차원 텐서  
  ![image](https://user-images.githubusercontent.com/82145878/179446487-8c6fb851-eaae-4bbd-9962-6616de11f561.png)  

 ![image](https://user-images.githubusercontent.com/82145878/179445779-a77c91e2-27d5-4792-8fd5-e47c180350ce.png)  
 
 
 로지스틱회귀-ㅅ그모이드 함수  
 
 
 
 # Back propagation  
 
 
 ![image](https://user-images.githubusercontent.com/82145878/179665255-d50a2240-59ad-4de5-aaff-402e3880a1db.png)  
 
 경사하강법의 momentum  : 로컬미니멈에서 빠져나와 글로벌 미니멈으로 갈 수 잇게해줌  
 Adam 쓰자
 tf.keras.optimizers.Adam(...)  
 
 
 연속적인 값 - 회귀
 이진분류 가능한것 - 분류  
 
 
 
 
 딥러닝에서 활성화함수를 꼭 써야하는 이유  
  - 중간 레이어의 역할이 없음  
  - 즉 딥러닝이 없는 것과 같음  


활성화함수  
- 활성화함수는 출력값을 결정하는 함수  
- 비선형 함수여야한다 : 비선형층  
- 중간층==은닉층==히든레이어층만 활성화함수를 쓰고있긴 한데
- 인풋레이어가 아닌데도 안쓰는 거 Flatten dropout callback embedding(선형) 층 등등...  
- 자연어 의 임베딩층은 선형층  
- 최초의 활성화함수 : step function  
- 이게 다듬어 진게 시그모이드  
- relu function, leaky relu function  
- 죽은 렐루 : 0 이 되면 경사가 없어지니까.. 문제가 됨 0은 좀 쓰지말자 해서 양수는 가지고 ㄱ나ㅡㄴ데 음수를 기울기를 살짝 준거 0.01 정도 (음수로 들어왔을때 0이 아니라 저정도 기울기를 줌)  
- 이진분류 : sigmoid 다중분류 : softmax
- gradient vanishing  -> activation='relu' 
- gradient exploding  -> gradient clipping for rnn 기울기 값을 자르는 것
- Adam = optimizers.Adam(lr=0.0001,clipnorm = 1)  
- from tensorflow.keras import optimizers  

왜 돌릴때마다 성능, 학습속도가 다를까? random 한 파라미터
weight초기화에서 문제가 있었던 것  
랜덤하게 준 웨이트가 0이면 업데이트를 할 수 없고 똑같은 웨이트를 줘도 업데이트가 같아서 안댐  


Greedy Layer Wise Training  

 
 VQA
 * functionaL API란?  
  - 중급, 고급  
  - 각 레이어를 함수로서 정의  
  - 반드시 입력층을 정의   
  - sequential API (초급)은 여러 층을 공유하거나 다양한 종류의 입력과 출력을 사용  
  ```python
  from tensorflow.keras import optimizers
  from tensorflow.keras.models import Model
  from tensorflow.keras.layers import Input, Dense
  import tensorflow as tf 
  
  inputs = Input(shape=(10,))
  hidden1 = Dense(16, activation='relu')(inputs)
  hidden2 = Dense(16, activation='relu')(hidden1)
  output = Dense(1, activation='sigmoid')(hidden2)
  model = Model(inputs = inputs, outputs = output)
  #functional 사용이라면 병렬로 사용한다는 것 
  sgd = optiizers.SGD(lr=0.01)
  model.compile(optimizer = sgd, loss = 'mse', metrics = ['mse'])
  hist = model.fit(X,y,epochs = 300)   #층 쌓는 것 외에 compile, fit은 다 동일 
  ```    
  
  ![image](https://user-images.githubusercontent.com/82145878/179901106-2c54ca30-0a51-48bd-9ebc-e5adcd356e70.png)  
  ```python
  from tensorflow.keras.models import Model
  from tensorflow.keras.layers import Input, Dense, concatenate
  
  inputa = Input(shape = (2,))
  inputb = Input(shape = (4,))
  
  x = Dense(4, activation='relu')(inputa)
  x = Dense(2,activation='relu')(x)
  x = Model(inputs = inputa, outputs = x)
  y = Dense(4,activation='relu')(inputb)
  y = Dense(2,activation = 'relu')(y)
  y = Dense(2,activation='relu')(y)
  y = Model(inputs= inputb, outputs = y)
  result = concatenate([x.output, y.output])
  z = Dense(2,activation='relu')(result)
  z = Dense(1, activation='linear')(z)

  model = Model(inputs=[x.input, y.input], outputs = z)#실제 모델의 시작을 적어줘야함 
```  
![image](https://user-images.githubusercontent.com/82145878/179901275-7e9ea52a-b5a7-41bd-b826-dd5581375897.png)  

![image](https://user-images.githubusercontent.com/82145878/179901935-f6f9a2d5-f110-4225-8800-9b5581db32a2.png)  






![image](https://user-images.githubusercontent.com/82145878/179904906-5123b259-5a3f-4389-9eb5-4b670d80110a.png)  

# Xavier Initialization  
w = np.random.randn(n_input, n_output) / sqar(n_input)
n_input  인풋노드의 개수
n_output 아웃풋노드의 개수 




  
  
  
한번 경사하강을 할때마다 얼마나 경사하강 할 것인지 learing rate 클수록 팍팍 빨리내려감 0을 못찾고 내려갈 수도잇어서 
좀 줄임

그런데 배치 정규화는 좀 상관없음 
학습ㅎㄹ때마다 정규분포가 틀어져잇다가 학습하면 맞추고 학습하면 맞추고 
자체적으로 커버가 되서 안정적으로 모델을 만들수 잇다  

BN + SIGMOID OR TANH ==> OAY GOOD
==> learning rate 를 높일 수 잇고 속도를 높일 수 잇다  
실제로 predict 할때 레이어는 빼야함  
학습을 위한 것임  
그리고 BN는 구조땜에 not for RNN
배치가 들어오는 대로 웨이트를 계싼하는 것이 안맞음  
분포가 많은 거을 가지고 평균, 분ㅅㄴㅇㄹ 내야지 
RNN에서는 Layer Nomalization 을 한다  

model.add(BatchNomalization())
model.add(LayerNormalization())  <== RNN  


과적합 방지
- 데이터 양을 늘린다 : 추가수집, 증식, augmentation, bak Traslation 등
- weight의 수를 줄인다 : 노드, 레이어의 수를 데이터셋에 비해 많이 했을 때 (학습 good 예측 bad ==> 노드 수 줄이기)  **늘린다고 성능 무조건 좋아지는 것 x**  
- Regularization 적용  : L1, L2, l1+l2  (머신러닝 회귀에서 사용햇던것처럼)  
- dropout


![image](https://user-images.githubusercontent.com/82145878/179926605-60b72664-77f2-443b-8f69-f17219e2a8a1.png)  

  
