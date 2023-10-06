#### Groupby 속성 살펴보기 
groups 함수로 그룹 속성을 확인할 수 있음 
코딩 예시 
```
df_group = df.groupby(‘컬럼명‘)
df_group.groups
```
___
#### Groupby 내부 함수 사용하기

==그룹 데이터에 NaN 이 포함되어 있을 경우 이를 제외하여 연산함==
여러 개의 컬럼을 활용한 복수 그룹핑도 가능함
```
# 위 코드에 이어서 사용할 경우 
df_group.count() 
df_group.sum() 

# 한번에 사용할 경우 
df.groupby(‘컬럼명’).count()
df.groupby(‘컬럼명’).sum()

# 특정 컬럼의 데이터만 확인하고 싶을 경우 
df.groupby(‘컬럼명‘).count()[[‘컬럼명2’]]
```
그룹핑과 loc 를 활용하면 원하는 index 의 데이터만 가져올 수도 있다 
코딩 예시 
```
# loc 로 조회할 인덱스명을 튜플로 만들어서 조회가 가능함 
df.groupby([‘컬럼명1‘, ’컬럼명2‘]).count().loc[[(‘인덱스명1’, ‘인덱스명2’)]]
```

###### stacking 을 활용해서 colums 을 index 로 바꾸고 groupby 하는 법 예시
```
df.set_index([‘컬럼명1‘,’컬럼명2‘]).groupby(level=[0,1]).mean()
```

