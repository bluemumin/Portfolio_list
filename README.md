Portfolio_list
================
머신러닝, 딥러닝 프로젝트 포트폴리오 정리

***
<h2>[#1. Competition - wavve 재구독 여부 분류] </h2> 

- Background 
 <p> wavve 신규 구독자의 3주간 시청 기록 활용, 1개월 뒤 재구독 여부를 사전 분류함.(이후 이탈 방지 혜택 부여) </p>

- Summary
	<p>(1). Data Collection <br/>
		- 사내 경진대회 데이터 제공[Wavve] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (지점데이터 + 고객데이터 + 외부데이터) <br/>
		- Reduction (특성이 다른 지점 데이터  제거, missing value 포함한 고객데이터 제거)</p>
	<p>(3). Model & Algorithms <br/>
		- xgboost regression(지점 데이터) --> RMSE 작을 때 feature importance <br/>
		- xgboost classifier(고객 데이터) --> F1 높을 때 feature importance<br/>
		- Aggregation(고객데이터 --> 지점데이터) --> Clustering(Hierarchical, K-means, Gaussian mixture)</p>
	<p>(4). Report <br/>
		- 이탈에 영향을 주는 변수 목록 작성
		- 변수 특성이 비슷한 지점끼리 클러스터링한 결과 표 작성
	<p>(5). Review <br/>
		- 피드백 : 클러스터링보다 나은 방법이 있지 않았을까<br/>
		- Futher Research : 바뀌는 금융환경 ---> 모델링 반복 필요<br/>
		&nbsp;: 통폐합이 영향을 준 고객만을 대상으로 분석 모델을 구축해야 한다
		
*보러가기: [wavve 재구독 여부 분류](https://github.com/bluemumin/wavve-subscription-exit-rate)*
		
***
<h2>[#2. Competition - 약물 독성 분류] </h2> 

- Background 
 <p> 신규 약 개발 시, 다양한 시물레이션 실행 및 비용 감축을 위해, 약물 분자 구조 약칭 데이터로 약물의 독성 여부 분류함 </p>

- Summary
	<p>(1). Data Collection <br/>
		- 사내 경진대회 데이터 제공[SK바이오팜] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (지점데이터 + 고객데이터 + 외부데이터) <br/>
		- Reduction (특성이 다른 지점 데이터  제거, missing value 포함한 고객데이터 제거)</p>
	<p>(3). Model & Algorithms <br/>
		- xgboost regression(지점 데이터) --> RMSE 작을 때 feature importance <br/>
		- xgboost classifier(고객 데이터) --> F1 높을 때 feature importance<br/>
		- Aggregation(고객데이터 --> 지점데이터) --> Clustering(Hierarchical, K-means, Gaussian mixture)</p>
	<p>(4). Report <br/>
		- 이탈에 영향을 주는 변수 목록 작성
		- 변수 특성이 비슷한 지점끼리 클러스터링한 결과 표 작성
	<p>(5). Review <br/>
		- 피드백 : 클러스터링보다 나은 방법이 있지 않았을까<br/>
		- Futher Research : 바뀌는 금융환경 ---> 모델링 반복 필요<br/>
		&nbsp;: 통폐합이 영향을 준 고객만을 대상으로 분석 모델을 구축해야 한다
		
*보러가기: [약물 독성 분류](https://github.com/bluemumin/smiles_toxicity)*
		
***
<h2>[#3. Competition, Toy project - 야구 타자 OPS 예측] </h2> 

- Background 
 <p> 현 시즌 타자 성적 기반, 다음 시즌의 타자들의 OPS(타자의 대표적 타격 지표) 성적 예측 </p>

- Summary
	<p>(1). Data Collection <br/>
		- 선수 연도별 타격 성적 + 개인 정보(나이, 연봉 등) [스탯티즈] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (지점데이터 + 고객데이터 + 외부데이터) <br/>
		- Reduction (특성이 다른 지점 데이터  제거, missing value 포함한 고객데이터 제거)</p>
	<p>(3). Model & Algorithms <br/>
		- xgboost regression(지점 데이터) --> RMSE 작을 때 feature importance <br/>
		- xgboost classifier(고객 데이터) --> F1 높을 때 feature importance<br/>
		- Aggregation(고객데이터 --> 지점데이터) --> Clustering(Hierarchical, K-means, Gaussian mixture)</p>
	<p>(4). Report <br/>
		- 이탈에 영향을 주는 변수 목록 작성
		- 변수 특성이 비슷한 지점끼리 클러스터링한 결과 표 작성
	<p>(5). Review <br/>
		- 피드백 : 클러스터링보다 나은 방법이 있지 않았을까<br/>
		- Futher Research : 바뀌는 금융환경 ---> 모델링 반복 필요<br/>
		&nbsp;: 통폐합이 영향을 준 고객만을 대상으로 분석 모델을 구축해야 한다
		
*보러가기: [야구 타자 OPS 예측](https://github.com/bluemumin/dongguk_university_graduate_report_baseball_OPS_end)*
		
***
<h2>[#4. Toy Project - 텔레마케팅 정기예금 가입 여부 분류] </h2> 

- Background 
 <p> 텔레마케팅 성과 확인 및 개선을 위해, 고객 개인정보 및 전화 시간등을 활용하여 신규 정기예금의 가입 여부를 분류</p>

- Summary
	<p>(1). Data Collection <br/>
		- 선수 연도별 타격 성적 + 개인 정보(나이, 연봉 등) [스탯티즈] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (지점데이터 + 고객데이터 + 외부데이터) <br/>
		- Reduction (특성이 다른 지점 데이터  제거, missing value 포함한 고객데이터 제거)</p>
	<p>(3). Model & Algorithms <br/>
		- xgboost regression(지점 데이터) --> RMSE 작을 때 feature importance <br/>
		- xgboost classifier(고객 데이터) --> F1 높을 때 feature importance<br/>
		- Aggregation(고객데이터 --> 지점데이터) --> Clustering(Hierarchical, K-means, Gaussian mixture)</p>
	<p>(4). Report <br/>
		- 이탈에 영향을 주는 변수 목록 작성
		- 변수 특성이 비슷한 지점끼리 클러스터링한 결과 표 작성
	<p>(5). Review <br/>
		- 피드백 : 클러스터링보다 나은 방법이 있지 않았을까<br/>
		- Futher Research : 바뀌는 금융환경 ---> 모델링 반복 필요<br/>
		&nbsp;: 통폐합이 영향을 준 고객만을 대상으로 분석 모델을 구축해야 한다
		
*보러가기: [텔레마케팅 통한 정기예금 가입 여부 분류](https://github.com/bluemumin/data_mining_telephone_marketing_with_R)*
		
***
<h2>[#5. Toy Project - 와인 품질 분류] </h2> 

- Background 
 <p> 와인 생산 중 더 좋은 품질의 와인을 생산하기 위해, 와인 성분 데이터로 와인의 품질 점수를 분류함</p>

- Summary
	<p>(1). Data Collection <br/>
		- 선수 연도별 타격 성적 + 개인 정보(나이, 연봉 등) [스탯티즈] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (지점데이터 + 고객데이터 + 외부데이터) <br/>
		- Reduction (특성이 다른 지점 데이터  제거, missing value 포함한 고객데이터 제거)</p>
	<p>(3). Model & Algorithms <br/>
		- xgboost regression(지점 데이터) --> RMSE 작을 때 feature importance <br/>
		- xgboost classifier(고객 데이터) --> F1 높을 때 feature importance<br/>
		- Aggregation(고객데이터 --> 지점데이터) --> Clustering(Hierarchical, K-means, Gaussian mixture)</p>
	<p>(4). Report <br/>
		- 이탈에 영향을 주는 변수 목록 작성
		- 변수 특성이 비슷한 지점끼리 클러스터링한 결과 표 작성
	<p>(5). Review <br/>
		- 피드백 : 클러스터링보다 나은 방법이 있지 않았을까<br/>
		- Futher Research : 바뀌는 금융환경 ---> 모델링 반복 필요<br/>
		&nbsp;: 통폐합이 영향을 준 고객만을 대상으로 분석 모델을 구축해야 한다
		
*보러가기: [와인 품질 분류](https://github.com/bluemumin/baf_kaggle_wine_project_end)*
