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

![image](https://user-images.githubusercontent.com/82145878/180107908-b855ec8d-6b48-4b88-bae6-9dcaf764f3e1.png)  

Stride 값에 따라 다름  
작은 구역의 특징을 찾으려는 건지에 따라 stride 값이 다름  
Output size:  
((N – F)/stride) + 1  

e.g. N = 7, F = 3:  
Stride 1 => (7 – 3) / 1 + 1 = 5    
Stride 2 => (7 – 3) / 2 + 1 = 3  
Stride 4 => (7 – 3) / 4 + 1 = 2   

## padding  
패딩하면 여기가 모서리구나 알 수 잇음
패딩을 씌우고 필터링을 한번하게되면은 7 7 -> 9 9 
9 - 3 / 1 + 1 = 7  
7 7 일때는 몇번만해도 더이상 필터링 못하게 된다
convolution 레이어도 일종의 히든 레이어 은닉층으로 여기기도 함  

![image](https://user-images.githubusercontent.com/82145878/180108577-6c531591-5473-4583-bfca-055ef8767e57.png)  


Conv2D 에 이미지 shape 맞춰서 넣어주기  
이미지넣으려면 2d layer 넣기  

§ strides=(1, 1),  디폴트가 가로 세로 1 칸씩 move  

제일 오른쪽 (안)쪾에 나오는 값이 가로 길이  
그다음이 세로  
그다음 개수  

가로세로를 조합한게 
