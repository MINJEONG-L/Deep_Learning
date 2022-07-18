# 변수명 자동화 globals() 함수  
```python
for i in range(1,10):
  globals()['hello{}'.format(i)] = a
```  

- globals()를 제일 앞에 붙여준 뒤, 리스트 형태처럼 보이는 [] 를 바로 뒤에 붙여주고 그 안에 변수명을 문자열 포맷팅하듯이 써주면 된다.  
- globals()[] 안에서는 문자열 포맷팅의 방식으로 작동  

```python
for i in range(1,10):
globals()['ax{}'.format(i)] = plt.subplot(3,3,i)
globals()['ax{}'.format(i)].set_title('train_image:{}'.format(train_labels[i-1]))
sns.heatmap(train_images[i-1], cbar = False, ax = globals()['ax{}'.format(i)])
```  

# matplotlib.pyplot 모듈의 subplot() 함수  
: 여러 개의 그래프를 하나의 그림에 나타내도록함  

```python
plt.subplot(row, column, index)
```  
![image](https://user-images.githubusercontent.com/82145878/179509837-dc548db3-c5c1-4f47-b5b3-ab3fbfd33fed.png)  

