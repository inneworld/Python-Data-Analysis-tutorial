## NUMPY


### - import
```
import numpy as np
```

---


### - numpy 와 list
```
array = np.array([1,2,3])

이런식으로 list를 numpy로 바꿔줄 수 있다.

array.size , array.dtype, array[숫자] 이런식의 기능을 제공한다.
```
---


### - 배열 채우기

```
array = np.arange(4) 

이런식으로 하면 0 부터 3까지의 숫자를 배열에 채워준다.  


array = np.zeros((4,4), dtype = float)   

이런식으로 하면 4 * 4의크기에 실수형인 0으로 다 채워서 만들어준다.  



1로 채우고 싶으면  

array = np.ones((3,3), dtype = str) 

이런식으로 문자열형태도 가능하다.

​

random값을 채우고 싶으면, 

array = np.random.randint(0,10, (3,3))

이렇게 하면 랜덤한 10보다 작은 수 들을 랜덤으로 3 * 3 크기에 배열에 넣는다.



임의의 데이터 채우기
array = np.linspace(0,10,5)

이런식으로 하게 되면 , 0부터 10가지 데이터를 5개로 채우는 것

```
---


### - 배열 합치기

​
```
array1 = np.array([1,2,3])

array2 = np.array([4,5,6])

array 3 = np.concatenate([array1, array2])

이런식으로 concatenate함수를 이용해서 합칠 수 있다.

array 3 = np.concatenate([array1, array2], axis=0)

이렇게 하게 되면 합쳐질때 array1 아랫줄에 array2가 들어가게 된다.

```
---

### - 배열 형태 바꾸기 

​
```
배열이 한줄로 있는걸 두줄로 만드는 등 다양한 형태 바꿈이 가능하다

array 1 = np.array([1,2,3,4]) 

array 2 = array1.reshape((2,2))

이런식으로 하면 한줄로 들어있는 배열을 2*2모양으로 바꿀 수 있다.

```
---



### - 배열 나누기
```
left , right = np.split(array,[2] , axis =1)

이런식으로 해서 인덱스 2번을 기준으로 오른쪽과 왼쪽을 자를 수 있다.

​
```
---

### - 상수연산
```

배열에 인자에 한번에 더하거나 곱하는 연산이 가능하다

​

array = np.random.randomint(1,10,size=4).reshape(2,2)

result_array = array * 10

이런식으로 곱하기 가능

​

만약 4 * 4 이런식으로 2차원 배열과 1 * 4 이런식의 배열이 있다면

1 * 4 의 4개의 인자가 복사되어서 4*4 의 형태로 만들어진 뒤 , 연산을 수행한다.
```
---

### - 마스킹 연산
```
array1 = np.arange(16).reshape(4,4)

array2 = array1 < 10

​

이런식으로 array1에서 10보다 작은 값은 true로 채우고 아닌 값은 false로 채우게 할 수 있다.

대체로 이미지 처리에서 자주 활용된다고 한다.
```
---
### - 집계함수
```
집계 함수

array = np.arange(16).reshape(4,4)

​

print("최댓값:" , np.max(array))

print("최솟값:" , np.min(array))

print("합계:" , np.sum(array))

print("평균값:" , np.mean(array))

print("세로줄당 합계 :",np.sum(array,axis =0))

이런식으로 집계 가능
```
---

### - 저장 및 불러오기
```

array = np.arange(0,10)

np.save('saved.npy',array)

이런식으로 저장 가능하다.

​

불러오려면

result = np.load('saved.npy')

이런식으로 가져올 수 있다.

 ```

### - 정렬
```

array = np.array([5,9,10,3,1])

array.sort()

하면 오름차순정렬

array[::=1]이런식으로 역순으로 출력하면 내림차순 정렬 가능

​

열을 기준으로 정렬하려면

array.sort(axis=0)

즉 위에 있는 값이 아래있는값보다 더 작게 하는 것

```

​

### - 난수의 재연(난수는 실행시마다 계속 다름)
```
np.random.seed(7)이런식으로 실행할때마다 난수가 바뀌지 않게 해줄수 있다.

배열 객체 복사

array2 = array1.copy()

중복된 원소 제거

np.unique(array)

이런식으로 가능
​
```
---
