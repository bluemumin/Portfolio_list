Portfolio_list
================
머신러닝, 딥러닝 프로젝트 포트폴리오 정리

(참여항목이 없을 경우, 전체 단독 제작 입니다.)

***
<h2>[#1. Competition - OTT 플랫폼 재구독 여부 분류] </h2> 

- 사용언어 / 핵심 라이브러리
 <p> Python(3.8) / Pandas, LightGBM </p>

- 목적 & 데이터 수집(제공)
 <p> - OTT 플랫폼의 신규 구독자의 3주간 시청 기록 활용, 가입 후 1개월 뒤 재구독 여부를 사전 분류함. <br/>
     - [그룹사 경진대회 데이터 제공](데이터 외부 유출 금지 -> 미 업로드, 관련 결과 삭제) </p>

- Summary
	<p>(1). Data Preprocessing <br/>
		- EDA (고객 결제 사항 + 시청 기록 데이터) <br/>
	        - 변수 내 항목 간소화 (결제 코드, 결제 등록 기기, 컨텐츠별 시청 기기) <br/>
		- 파생변수 생성 (최신 컨텐츠 시청 기간 그룹화, 유저 컨텐츠 시청 퍼센트, 결제 후, 마지막 시청일자 gap 계산) <br/>
		- Data Reduction (유저별 과도한 컨텐츠 시청 수, 최신 컨텐츠 과다 시청 수 절삭)</p>
	<p>(2). Model & Algorithms <br/>
		- LightGBM 1차, 2차 수행 --> 최적의 parameter 확인(gridsearch + 5-fold) --> 최적의 threshold 확인(5-fold)  <br/>
		- Xgboost, Randomforest 모델링 후, ensemble 수행 --> 예측률 저하로 최종 제외 <br/>
	<p>(3). Report & Review <br/>
	        - 최종 등수 : 27/248(팀) 기록 (1등과 f1-score 0.01 차이) <br/>
		- 긍정적 사항 : 유저의 컨텐츠 시청 퍼센트(시청 시간/컨텐츠 길이) 파생 변수 생성으로 모델 성능 향상 <br/>
	        - 피드백 : 결제 후, 마지막 시청일자 gap 파생변수 영향도 << 주차별 시청 시간 증가/감소 여부 <br/>
		- Futher Research : 해당 주차 드라마/영화 순위(외부 데이터) 활용한 인기 콘텐츠 선호도, <br/>
		&nbsp;+ (ott내 영화 추가 구매 여부, 코인 추가 거래 내역 등) 플랫폼 적극적 이용 수치 인사이트 개발 가능 예상 </p>
		
*보러가기: [ott 재구독 여부 분류](https://github.com/bluemumin/ott_subscription_exit_rate)*
		
***
<h2>[#2. Competition - 약물 독성 분류] </h2> 

- 사용언어 / 핵심 라이브러리
 <p> Python / Pandas, rdkit(분자구조 변환 라이브러리), LightGBM, sklearn </p>

- 목적 & 데이터 수집(제공)
 <p> - 신규 약 개발 시, 다양한 시물레이션 실행 및 비용 감축을 위해, 약물 분자 구조 약칭 데이터로 약물의 독성 여부 분류함 </br>
     - [사내 경진대회 데이터 제공](데이터 외부 유출 금지 -> 미 업로드, 관련 결과 삭제) </p>

- Summary
	<p>(1). Data Preprocessing <br/>
		- 데이터 도메인 공부 (SMILES CODE 공부, 분자구조 벡터화 방식, 약물 성분 컬럼 내용) <br/>
		- 파생변수 추가(분자 구조 벡터화 방식 2종 추가, rdkit 라이브러리 활용 변수 추가)</p>
	<p>(2). Model & Algorithms <br/>
		- LightGBM --> 10-fold + parameter 추가 설정 <br/>
		- 모델 성능 검증 --> binary cross entropy 대신 f1_score 함수 구현 후 LightGBM 성능 개선에 사용</p>
	<p>(3). Report & Review <br/>
		- 최종 등수 : 2등/ <br/>
		- 긍정적 사항 : 단일 LGBM 구조로, 앙상블 활용 수상작들과 f1_score가 차이 없는 모델 구현 <br/>
		- + 관련 도메인 없지만 충분한 리서치 후, 관련 라이브러리를 활용한 파생 변수 생성 <br/>
		- 피드백 : 데이터 부족 -> overfitting 상태 미 해결로 대회 종료 </p>

*보러가기: [약물 독성 분류](https://github.com/bluemumin/smiles_toxicity)*
		
***
<h2>[#3. Competition, Toy project - 야구 타자 OPS 예측] </h2> 

- 사용언어 / 핵심 라이브러리
 <p> Python / Pandas, matplotlib, seaborn, plotly, BeautifulSoup, sklearn </p>

- 목적 & 데이터 수집(제공)
 <p> - 현 시즌 타자 성적 기반, 다음 시즌의 타자들의 OPS(타자의 대표적 타격 지표) 성적 예측 </br>
     - [웹 페이지(사이트 명 : 스탯티즈) 크롤링] --> 현역 선수 연도별 타격 성적 + 개인 정보(나이, 연봉 등) </p>

- Summary
	<p>(1). Data Preprocessing <br/>
		- EDA (변수간 heatmap & 반응변수와의 barplot, boxplot & barplot, histogram & dot graph) <br/>
		- 목적, 파생변수 생성 (다음 시즌 OPS --> 반응변수 / 행운의 안타, 타자 속도 계수, 평균대비 기여율, 공 반발계수, 누적 연차 등)<br/>
		- Reduction & 변수 그룹화 (작은 타석수로 과도 or 과소로 나온 값 절단, 타석 위치 & 포지션 통합)</p>
	<p>(2). Model & Algorithms <br/>
		- RandomForestRegressor --> GridSearch 사용 후 MAE 계산 <br/>
		- xgboost Regressor, Linear Regression --> parameter 미설정 후, 메인 모델링 비교용으로 활용<br/>
		- 이전 2개년 결과 --> 누적 데이터 감소에 따른 영향 확인 및, 연도별 MAE 일정 여부 확인 </p>
	<p>(3). Report & Review <br/>
		- 최종 등수 : 모델링 18/93위 기록 / 시각화 1등 기록 <br/>
		- MAE 0.09로 타자의 OPS 성적을 1할 미만으로 예측하는 모델 구현(cf 예측변수 평균 범위 0.55~1.1) <br/>
		- 긍정적 사항 : 데이터 크롤링, EDA, 모델링까지 전체 process 단독 구현</br>
		- 피드백 : 직전 시즌 기록만이 아닌 더 이전 시즌의 기록, 누적 성적들도 활용 가능 했음<br/>
		- Futher Research : 이전 기록이 없는 신규 타자 --> 고등,대학 리그의 데이터 보유시, 추가 모델 구현 가능 </p>
		
*보러가기: [야구 타자 OPS 예측](https://github.com/bluemumin/baseball_ops_predict)*
		
***
<h2>[#4. Toy Project - 텔레마케팅 후, 정기예금 가입 여부 분류] </h2> 

- 참여 항목
 <p> 김경록(R, SAS 코드 작성 및 보고서 작성), 팀원(ppt 제작, 파생변수 아이디어 제공) </p>

- 사용언어 / 핵심 라이브러리
 <p> SAS, R / ggplot2, dplyr 등 </p>

- 목적 & 데이터 수집(제공)
 <p> - 텔레마케팅 성과 확인 및 개선을 위해, 고객 개인정보 및 전화 시간등을 활용하여 신규 정기예금의 가입 여부를 분류 </br>
     - [Kaggle 데이터] 포르투갈 은행 텔레 마케팅 성과 자료 </p>

- Summary
	<p>(1). Data Preprocessing <br/>
		- EDA (고객 개인 정보, 텔레마케팅 기록,) <br/>
		- 시각화 (독립변수 & 반응변수 누적 바 그래프, 핵심변수 histogram, boxplot   ) <br/>
		- 변수 변형 (나이 -> 나이대 그룹화, 직업군 통일화, date 정보 분리) <br/>
		- Reduction (과도한 은행 잔고, 비정상적 개인정보 제거) </p>
	<p>(2). Model & Algorithms <br/>
		- 이전 캠페인 참여/비참여에 따른 신규 참여율 많이 다름 --> 해당 변수 기준, 데이터 분리 후 모델 2개 생성 <br/>
		- 반응변수 불균형 --> 모델링 과정에서 데이터 비율별 가중치 별도 부여 <br/>
		- 로지스틱 회귀분석 --> 정확도 계산(이전 참여 : 73%, 이전 미 참여 : 64퍼) </p>
	<p>(3). Report & Review <br/>
		- 이전 캠페인 참여 여부 & 신규 정기예금 가입 여부 상관성 확인 후, 데이터 분리 --> 향상된 분류 모델 구축 <br/>
		- 다양한 시각화와 변수 변형을 통해서 Reduction 되어야될 데이터 확인 후 제거 <br/>
		- 피드백 : 데이터 불균형인 상황에서 최적의 threshold 찾는 과정 없이 단순 0.5로 수행 </p>
		
*보러가기: [텔레마케팅 통한 정기예금 가입 여부 분류](https://github.com/bluemumin/telemarketing_to_deposit_with_R)*
		
***
<h2>[#5. Toy Project - 와인 품질 분류] </h2> 

- 사용언어 / 핵심 라이브러리
 <p> Python / Pandas, matplotlib, seaborn, sklearn, LightGBM  </p>

- 목적 & 데이터 수집(제공)
 <p> - 와인 생산 중 더 좋은 품질의 와인을 생산하기 위해, 와인 성분 데이터로 와인의 품질 점수를 분류함</br>
     - [Kaggle 데이터] 레드 와인 성분 + 와인 품질 </p>
     
- Summary
	<p>(1). Data Preprocessing <br/>
		- EDA (독립변수 correlation plot, histogram, boxplot) <br/>
	        - binarization(와인품질 3~8점 / 5점 이하 -> low rank, 6점 이상 -> high rank) <br/>
		- Reduction (EDA 시각화 이후, 각 변수의 상위 5%의 이상치 값 제거)</p>
	<p>(2). Model & Algorithms <br/>
		- Logistic Regression, RandomForest, LightGBM <br/>
		  --> 기본 버전 및 paramter 개선을 통해 정확도, auc 개선 사항 확인 </p>
	<p>(3). Report & Review <br/>
		- 기본 버전 및 paramter 개선을 통해 정확도, auc 개선 사항 확인 <br/>
		- 전반적인 머신러닝 flow 학습 및 파이썬 기초 코딩 능력 습득 <br/>
		- 피드백 : 반응변수(와인 품질)에 대한 개선 방안 미 제시(ex - 변수 importance를 통한 변수 중요도 미 제시)</p>
		
*보러가기: [와인 품질 분류](https://github.com/bluemumin/wine_quality_classfication)*
