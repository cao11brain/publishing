### Binning 
##### cut
bins 에 구간을 지정해주고, label 에 각 라벨의 값을 지정해준다
==구간 지정값과 범주의 개수는 1개 차이가 있다==
```
df[‘bining컬럼명‘] = pd.cut(df[‘컬럼명’]), 
   bins = [0, q1, q3, df[‘컬럼명‘].max()],    # 구간의 값을 넣어준다
   labels = [‘low’, ‘mid’, ’high’])   # 새롭게 지정된 범주의 값을 지정해준다
```
##### qcut
```
df[‘bining컬럼명’] = pd.qcut(df[‘컬럼명‘], 3,  # 구간의 개수를 그냥 지정해주면 된다
   labels = [‘low’, ‘mid’, ‘high’])
```
___
### Scaling
##### Standardization 
단순 표준화 계산 수식으로 만들어준다. 숫자형 변수에 대해서만 필터 걸어서 살펴본다. 
```
df = df_fix[[‘A’, ‘B’]]   # 숫자형 변수인 A, B 컬럼에 대해서만 실행할 경우, 
df = df - df.mean()/df.std()
```
##### Normalization
함수를 호출해서 사용한다 
==fit_transform 방식은 그냥 외우자. 저렇게 쓰면 된다==
```
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler() 
normalization_df = df.copy()
normalization_df[:] = scaler.fit_transform(normalization_df[:])
```
### One Hot Encoding
```
df_encoded = pd.get_dummies(df, columns = [‘컬럼명’])

또는 대상 컬럼이 여러 개일 경우 별도로 정의해서 할 수도 있다 

sample = [‘컬럼명1‘, ’컬럼명2‘]
df_encoded = pd.get_dummies(df, columns = sample)
```
