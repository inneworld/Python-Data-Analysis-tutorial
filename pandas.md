## PANDAS 

### - import
```
import pandas as pd 

이런식으로 주로 사용
```
---
### - 시리즈
```
시리즈는 인덱스와 , 값이 있는 형태 (딕셔너리와 유사함)

array1 = {'apple':3, 'banana' : 4, 'berry':5}

amount = pd.Series(array1)

이런식으로 딕셔너리 형과 호환도 되고,

array = pd.Series(['사과', '바나나','당근'] , index = ['a','b','c'])

이런식으로 직접 사용도 가능하다.

```
---

### - data frame
```


두개의 딕셔너리 즉 두개의 시리즈를

인자로 하나로 합친 것 (excel과 비슷)

word = pd.Series(word_dict)

frequncey = pd.Series(frequncey_dict)

summary = pd.DataFrame({'word': word, 'frequency' : frequency})

이런식으로 딕셔너리를 인자로 합칠 수 있음

​
```
---

### - data frame 의 연산

```

데이터 프레임의 연산으로 두 시리즈를 합치거나 곱해서 새로운 시리즈를 만들 수도 있다.

amount = pd.Series(array1)

expensive = pd.Series(array2)

​

summary = pd.DataFrame({'expensive':expensive , 'amount' :amount})

score = summary ['expensive']* summary['amount']

summary['score'] = score

​


이런식으로 하면 expensive와 amount가 곱해진 값이 score에 들어가서 새로운 시리즈가 만들어진다.

summary를 출력하면

        expensive  amount  score

apple         300       3    900

banana        400       4   1600

berry         100       5    500

이런식으로 나온다.


```
---

### - 슬라이싱
```

이름을 기준으로 , index를 기준으로 둘다 슬라이싱이 가능하다

print(summary.loc['banana' : 'carrot' , 'expensive' : ])

이런식으로 banana부터 carrot까지 exepensive뒤에 있는인자들을 출력할수 있다.

data frame의 연산

새로운 값 넣을때 , 

시리즈이름.loc['index' , 'index'] = 5

이런식으로 변경

시리즈이름.loc['index'] = ['index' ,5,3]이런식으로 통채로 삽입도 가능

```
---


### - 엑셀로 내보내기 / 불러오기
```
시리즈이름.to_csv("summary.csv",encoding="utf-8-sing")

이런식으로 내보내고

saved= pd.read_csv("summary.csv",index_col=U)

이런식으로 불러오기 가능
```
---

### - null 처리

```

data frame이름.notnull

하면 null이 아닌것은 true로 출력,

.isnull하면 null값이 true로 출력된다.

그리고 .fillna('데이터 없음')

이런식으로 null값이라고 나오는대신 데이터 없음 이라는 문자열로 대체 할수 있다.

​
```
---

### - 시리즈 자료형의 연산

​
```
두가지 시리즈를 더하고 싶다면,

array = array1.add(array2, fill_value=0)

이런식으로 더해줄 수 있다.

```
---
### - 데이터 프레임 집계 하기
```

데이터 프레임의 집계 함수

array[1].sum이런식으로 각각의 시리즈의 총 합을 구할수도 있고,

array.sum이런식으로 전체 데이터 프레임의 총 합을 구할수도 있다.
```
---

### - 데이터 프레임의 정렬
```

summary = summary.sort_values('index', ascending=True)

이런식으로 특정인덱스에 대해서 정렬 가능하다

ascending부분을 False로 바꾸게 되면 내림차순 정렬 된다.
```
---
## - 데이터 프레임의 마스킹
```
df = pd.DataFrame(np.ramdom.randint(1,10,(2,2)),  index = [0,1] , columns=["A","B"])

print(df["A"] <=5)

이런식으로 각 컬럼의 원소가 5보다 작거나 같은지를 출력하는등 여러가지 마스킹을 할수 있다.
또한 data base query문법처럼
df.query("A<=5 and B <= 8") 이렇게도 사용할 수 있다.

```
---


