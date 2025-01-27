## DACON-The_number_of_diners_in_the_cafeteria_Prediction
[데이콘 구내식당 식수 인원 예측 AI 경진대회](https://dacon.io/competitions/official/235743/leaderboard)

- JBIG에서 멤버를 모아 도전했던 첫 데이콘 대회
- XG Boost , LightGBM, Randomforest, Kfold 등 다양한 모델들을 사용해보았지만 CatBoost의 성능이 가장 좋았다

## ROLE
- `황산하` : 파라미터 튜닝 및 전처리 
- `고경수` : 전처리 및 모델링
- `김동완` : 모델링 및 변수 선택
--------------

### Feature Engneering
- 월(중식), 월(석식) : 일자 파생변수
- 요일, 요일(석식) : 요일 파생변수
- 일 : 일자 파생변수
- 식사가능자수 : 본사정원수 파생변수
- 본사출장자수 : 기본변수
- 본사시간외근무명령서승인건수 : 기본변수
- 공휴일전후 : 임의로 추가 ( 더미화 하여 이용 )

* 기상청의 체감기온, 기온등의 변수도 사용해보았지만, 성능이 좋지않아 제외하였다.
** 월, 요일 별로 특별하게 식수인원이 많은 월과 요일이 있는듯한 양상을 보여 월과 요일에 순위를 부여하여서 사용하였다.

-------
### Kernel PCA
- 좀 더 유의미한 `Feature Selection`을 위해 kenel pca를 진행했으나 유의미한 결과를 얻지 못햇다.
- 아무래도 예측해야하는 과제의 특성상 변수를 제거하니 정확도가 더 떨어진 것으로 예상 
---------
\+
- 한동안 Public 점수로 1등을 유지하다가, 5등까지 떨어졌다.
- 7/23 Private 점수가 공개되자 최종발표된 순위는 51/220. 과적합되었던 것으로 예상
- 대회를 시작하면서부터 주어진 `메뉴`데이터를 처리하고 싶었는데 NLP의 오류로 인해 실패했다. 가상환경 새로 팠는데..
- 첫 대회치고는 나쁘지않은 결과지만, 아쉬움이 남았다. 

![image](https://user-images.githubusercontent.com/73769046/126861455-a9f49fc6-1c03-40ab-ab5b-ab55d918a59f.png)

![image](https://user-images.githubusercontent.com/73769046/126861439-1069c3ee-a3d7-4122-a577-ba24b1c06759.png)
-------
