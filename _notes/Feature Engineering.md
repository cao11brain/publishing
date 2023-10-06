정의 : 데이터를 분석하거나 AI 알고리즘 적용을 위해 데이터의 도메인 지식을 활용해 변수를 가공해 데이터를 비교적 명료하게 만드는 것 
유의사항 : 데이터를 가공하는 것과 수정은 다르다. 수정하면 안된다
___
### Binning
연속형 변수를 범주형 변수로 만드는 방법 
1. 구간값을 지정하는 방식 : cut()
```
pd.cut(df, bins =[…, …, …], labels=[‘value’, value])
```
2. 구간의 개수를 지정하는 방식 : qcut()
```
pd.qcut(df, Number, labels=[value,value, …]) 
   # Number 로 나눌 값의 개수를 정해준다
```
___
### Scaling 
숫자 데이터간의 상대적 크기 차이를 제거하는 방법
##### 1. 정규분포로 만드는 것 
- standardScaler() : 평균 0, 분산 1 인 정규분포로 만듬 
##### 2. 중앙값과 4분위값을 사용하는 것 - 이상치 영향을 덜 받음
- RobustScaler() : 평균, 분산 대신 - ==이상치 영향을 덜 받음==
##### 3. 모든 값을 0~1 사이에 위치하도록 함
- MinMaxScaler() : 모든 특성이 0~1 사이에 위치하도록 함. ==분류보다 회귀분석에 유용함 ==
	`from sklearn.preprocessing import MinMaxScalar
	`scaler = MinMaxScalar()
	`df[:] = scaler.fit_transform(df[:]) 
##### 4. 각 특성의 절대값이 0~1 사이가 되도록 함
- MaxAbsScaler() : 절대값이 0~1 사이에, 즉 -1~1 사이에 위치하도록 함
___
### One Hot Encoding 
머신러닝/딥러닝은 수치형 데이터만 가능해서 수치형으로 변환이 필요
값(Value) 를 Colums 로 변환하고 Colums 별로 Value 를 0 또는 1로 바꾸어 수치형으로 바꾼다
___
### [[(실습) Feature Engineering|실습 바로가기]]
