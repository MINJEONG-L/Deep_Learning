# CNN  Convolutional Neural Network  
: 구역구역 잘라서 특징을 잡는다.   
- 이미지 분류에서 자주 사용  
- 가중치(parameter, filter, kernel) 공유  
- Convolution 은 feature 추출을 위해 , pooling 은 펼치기 위해(Convolution, Pooling layer - feature extraction)  
- Fully-connected layer - classification  
- Generally, it consist of convolution layer, pooling layer and fully-connected layer.  
-풀링으로 대표값 찾음  
자르고 마이너스값 버리고 대표값 찾고 자르고 마이너스값 버리고 자르고 마이너스값 버리고..대표긊 찾고  
필터는 그 부분의 대표값을 찾겠다는 의미가 있음  
이미지 자체에서 특징을 찾는게 아니라 결과값 즉 오차를 보고 특징을 찾겠다  
필터의 각각의 자리에는 w가 있음  
5x5x3 필터에는 75개의 가중치가 있음 w75x75 + b 까지 가는 것  
하나의 스칼라 값으로 바뀌는 것  
75개의 가중치를 가지고 전체 이미지를 특징을 추출 할때 weight bias 를 사용함  
필터 이동할때마다 가중치 바뀌지 x  
이동을 하는 회수만큼 스칼라 값이 쌓일 것임  
나온 결과도 이미지 처럼 가로 세로가 생기느 거임 필터를 거치면 깊이가 1인 결과물
depth는 무조건 1이 나옴  
얼마나 큰필터, 이동을 얼마나햇는지에 다라 새로운 이미지가 나오고 깊이는 무조건 1  
가로와 세로는 각각 몇일까?

