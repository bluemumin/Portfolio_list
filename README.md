Portfolio_list
================
머신러닝, 딥러닝 프로젝트 포트폴리오 정리

(참여항목이 없을 경우, 전체 단독 제작 입니다.)

***
<h2>[#1. Competition - wavve 재구독 여부 분류] </h2> 

- 사용언어 / 핵심 라이브러리
 <p> python(3.8) / Pandas, LightGBM </p>

- Background 
 <p> wavve 신규 구독자의 3주간 시청 기록 활용, 1개월 뒤 재구독 여부를 사전 분류함.(이후 이탈 방지 혜택 부여) </p>

- Summary
	<p>(1). Data Collection <br/>
		- 그룹사 경진대회 데이터 제공[Wavve](데이터 외부 유출 금지로 미 업로드 및 관련 결과 삭제) </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (고객 결제 사항 + 시청 기록 데이터) <br/>
	        - 변수 내 항목 간소화 (결제 코드, 결제 등록 기기, 컨텐츠별 시청 기기) <br/>
		- 파생변수 생성 (최신 컨텐츠 시청 기간 그룹화, 유저 컨텐츠 시청 퍼센트, 결제 후, 마지막 시청일자 gap 계산) <br/>
		- Reduction (유저별 과도한 컨텐츠 시청 수, 최신 컨텐츠 과다 시청 수 절삭)</p>
	<p>(3). Model & Algorithms <br/>
		- LightGBM 1차, 2차 수행 --> 최적의 parameter 확인(gridsearch + 5-fold) --> 최적의 threshold 확인(5-fold)  <br/>
		- Xgboost, Randomforest 모델링 후, ensemble 수행 --> 예측률 저하로 최종 제외 <br/>
	<p>(4). Report <br/>
		- LightGBM 결과 기반, 재구독 여부에 효과적인 변수 list 작성 <br/>
	        - 최종 등수 27/248(팀) 기록 (1등과 f1-score 0.01 차이) <br/>
		- 두 평가 기준인 f1-score와 accuracy의 차이가 없는 균형적 모델 작성</p>
	<p>(5). Review <br/>
		- 긍정적 사항 : 유저의 컨텐츠 시청 퍼센트(시청 시간/컨텐츠 길이) 파생 변수가 모델 개선에 효과적 <br/>
	        - 피드백 : 결제 후, 마지막 시청일자 gap보다, 1주차별 시청 시간의 증가/감소 여부가 더 효과적임을 예상함 <br/>
		- Futher Research : 해당 주차 드라마/영화 순위(외부 데이터) 활용한 인기 콘텐츠 선호도, <br/>
		&nbsp;+ (wavve내 영화 추가 구매 여부, 코인 추가 거래 내역 등) 플랫폼 적극적 이용 수치 인사이트 개발 가능 예상 </p>
		
*보러가기: [wavve 재구독 여부 분류](https://github.com/bluemumin/wavve_subscription_exit_rate)*
		
***
<h2>[#2. Competition - 약물 독성 분류] </h2> 

- Background 
 <p> 신규 약 개발 시, 다양한 시물레이션 실행 및 비용 감축을 위해, 약물 분자 구조 약칭 데이터로 약물의 독성 여부 분류함 </p>

- Summary
	<p>(1). Data Collection <br/>
		- 사내 경진대회 데이터 제공[SK바이오팜](데이터 외부 유출 금지로 미 업로드 및 관련 결과 삭제) </p>
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

- 사용언어 / 핵심 라이브러리
 <p> python / Pandas, matplotlib, seaborn, plotly, BeautifulSoup, sklearn </p>

- Background 
 <p> 현 시즌 타자 성적 기반, 다음 시즌의 타자들의 OPS(타자의 대표적 타격 지표) 성적 예측 </p>

- Summary
	<p>(1). Data Collection <br/>
		- 현역 선수 연도별 타격 성적 + 개인 정보(나이, 연봉 등) [스탯티즈] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (변수간 heatmap & 반응변수와의 barplot, boxplot & barplot, histogram & dot graph) <br/>
		- 목적, 파생변수 생성 (다음 시즌 OPS --> 반응변수 / 행운의 안타, 타자 속도 계수, 평균대비 기여율, 공 반발계수, 누적 연차 등)<br/>
		- Reduction & 변수 그룹화 (작은 타석수로 과도 or 과소로 나온 값 절단, 타석 위치 & 포지션 통합)</p>
	<p>(3). Model & Algorithms <br/>
		- RandomForestRegressor --> GridSearch 사용 후 MAE 계산 <br/>
		- xgboost Regressor, Linear Regression --> parameter 미설정 후, 메인 모델링 비교용으로 활용<br/>
		- 이전 2개년 결과 --> 누적 데이터 감소에 따른 영향 확인 및, 연도별 MAE 일정 여부 확인 </p>
	<p>(4). Report <br/>
		- 평균 MAE 0.09로 타자의 OPS 성적을 1할 미만의 값으로 예측하는 모델 구현 완료 (cf 최저/고 범위 0.55~1.1) <br/>
		- 다음 시즌의 타자 성적 예측 목표를 두고 데이터 크롤링, EDA, 모델링까지 전체 process 구현 완료 </p>
	<p>(5). Review <br/>
		- 피드백 : 직전 시즌 기록만이 아닌 더 이전 시즌의 기록, 누적 성적들도 활용 가능 예상함<br/>
		- Futher Research : 이전 기록이 없는 신규 타자 --> 고등,대학 리그의 데이터로 추가 모델 구현<br/>
		- 모델링 18/93위 기록, 시각화 1등 기록 <br/>
		&nbsp;+ 스탯티즈 사이트 개편시, 크롤링 코드가 중단이 되므로, 코드 재활용시 개선 작업 필요 </p>
		
*보러가기: [야구 타자 OPS 예측](https://github.com/bluemumin/baseball_ops_predict)*
		
***
<h2>[#4. Toy Project - 텔레마케팅 정기예금 가입 여부 분류] </h2> 

- 참여 항목
 <p> 김경록(R, SAS 코드 작성 및 보고서 작성), 팀원(ppt 제작, 파생변수 아이디어 제공) </p>

- 사용언어 / 핵심 라이브러리
 <p> SAS, R / ggplot2, dplyr 등 </p>

- Background 
 <p> 텔레마케팅 성과 확인 및 개선을 위해, 고객 개인정보 및 전화 시간등을 활용하여 신규 정기예금의 가입 여부를 분류</p>

- Summary
	<p>(1). Data Collection <br/>
		- 포르투갈 은행 텔레 마케팅 성과 자료 [kaggle] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (고객 개인 정보, 텔레마케팅 기록,) <br/>
		- 시각화 (독립변수 & 반응변수 누적 바 그래프, 핵심변수 histogram, boxplot   ) <br/>
		- 변수 변형 (나이 -> 나이대 그룹화, 직업군 통일화, date 정보 분리) <br/>
		- Reduction (과도한 은행 잔고, 비정상적 개인정보 제거) </p>
	<p>(3). Model & Algorithms <br/>
		- 이전 캠페인 참여/비참여에 따른 신규 참여율 많이 다름 --> 해당 변수 기준, 데이터 분리 후 모델 2개 생성 <br/>
		- 반응변수 불균형 --> 모델링 과정에서 데이터 비율별 가중치 별도 부여 <br/>
		- 로지스틱 회귀분석 --> 정확도 계산(이전 참여 : 73%, 이전 미 참여 : 64퍼) </p>
	<p>(4). Report & Review <br/>
		- 이전 캠페인 참여 여부 & 신규 정기예금 가입 여부 상관성 확인 후, 데이터 분리 --> 향상된 분류 모델 구축 <br/>
		- 다양한 시각화와 변수 변형을 통해서 Reduction 되어야될 데이터 확인 후 제거 <br/>
		- 피드백 : 데이터 불균형인 상황에서 최적의 threshold 찾는 과정 없이 단순 0.5로 수행 </p>
		
*보러가기: [텔레마케팅 통한 정기예금 가입 여부 분류](https://github.com/bluemumin/telemarketing_to_deposit_with_R)*
		
***
<h2>[#5. Toy Project - 와인 품질 분류] </h2> 

- 사용언어 / 핵심 라이브러리
 <p> python / Pandas, matplotlib, seaborn, sklearn, LightGBM  </p>

- Background 
 <p> 와인 생산 중 더 좋은 품질의 와인을 생산하기 위해, 와인 성분 데이터로 와인의 품질 점수를 분류함</p>

- Summary
	<p>(1). Data Collection <br/>
		- 레드 와인 성분 + 와인 품질 [kaggle] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (독립변수 correlation plot, histogram, boxplot) <br/>
	        - binarization(와인품질 3~8점 / 5점 이하 -> low rank, 6점 이상 -> high rank) <br/>
		- Reduction (EDA 시각화 이후, 각 변수의 상위 5%의 이상치 값 제거)</p>
	<p>(3). Model & Algorithms <br/>
		- Logistic Regression, RandomForest, LightGBM <br/>
		  --> 기본 버전 및 paramter 개선을 통해 정확도, auc 개선 사항 확인 </p>
	<p>(4). Report & Review <br/>
		- 기본 버전 및 paramter 개선을 통해 정확도, auc 개선 사항 확인 <br/>
		- 전반적인 머신러닝 flow 학습 및 파이썬 기초 코딩 능력 습득 <br/>
		- 피드백 : 반응변수(와인 품질)에 대한 개선 방안 미 제시(ex - 변수 importance를 통한 변수 중요도 미 제시)<p/>
		
*보러가기: [와인 품질 분류](https://github.com/bluemumin/baf_kaggle_wine_project)*

***
<h2>[#6. Toy Project - 배달 통화 건수 데이터 활용, 신규 창업 추천] </h2> 

- 참여 항목
 <p> 김경록(R, SAS 코드 작성 및 보고서 작성), 팀원(ppt 제작, 파생변수 아이디어 제공) </p>

- 사용언어 / 핵심 라이브러리
 <p> python / Pandas, matplotlib, seaborn, sklearn, LightGBM  </p>

- Background 
 <p> 지역, 배달 주문 통화 건수 데이터를 활용한, 신규 창업시 최적의 업종, busy time, 휴무일 컨설팅 모델 구축</p>

- Summary
	<p>(1). Data Collection <br/>
		- 레드 와인 성분 + 와인 품질 [kaggle] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (독립변수 correlation plot, histogram, boxplot) <br/>
	        - binarization(와인품질 3~8점 / 5점 이하 -> low rank, 6점 이상 -> high rank) <br/>
		- Reduction (EDA 시각화 이후, 각 변수의 상위 5%의 이상치 값 제거)</p>
	<p>(3). Model & Algorithms <br/>
		- Logistic Regression, RandomForest, LightGBM <br/>
		  --> 기본 버전 및 paramter 개선을 통해 정확도, auc 개선 사항 확인 </p>
	<p>(4). Report & Review <br/>
		- 기본 버전 및 paramter 개선을 통해 정확도, auc 개선 사항 확인 <br/>
		- 전반적인 머신러닝 flow 학습 및 파이썬 기초 코딩 능력 습득 <br/>
		- 피드백 : 반응변수(와인 품질)에 대한 개선 방안 미 제시(ex - 변수 importance를 통한 변수 중요도 미 제시)<p/>
		
*보러가기: [와인 품질 분류](https://github.com/bluemumin/baf_kaggle_wine_project)*
