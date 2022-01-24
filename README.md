Portfolio_list
================
머신러닝, 딥러닝 프로젝트 포트폴리오 정리

***
<h2>[#1. Project - 야구 타자 OPS 예측] </h2> 

- Background 
 <p> 현 시즌 타자 성적 기반, 다음 시즌의 타자들의 OPS(타자의 대표적 타격 지표) 성적을 예측 </p>

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
<h2>[#1. Project - 야구 타자 OPS 예측] </h2> 

- Background 
 <p> 현 시즌 타자 성적 기반, 다음 시즌의 타자들의 OPS(타자의 대표적 타격 지표) 성적을 예측 </p>

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
