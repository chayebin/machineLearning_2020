### <머신러닝 - 교통사고 및 인구수 데이터 분석을 활용한 교통사고 위험도 예측>
​
​
# 0. 목차 
> [1. 목적](#1-목적)  
> [2. 프로젝트](#2-프로젝트)  
> [3. 시각화](#3-시각화)   
> [4. 모델](#4-모델)     
> [5. 결론](#5-결론)   

​
​
# 1. 목적  
> * 교통사고에 대한 심각성 인지
> * 시각화된 데이터 제공
> * 위험도 예측과 사전 예방

​
​
# 2. 프로젝트
### 2.1. 프로젝트 소개
> * 교통사고 및 인구수 데이터 분석을 활용한 교통사고 위험도 예측
> * 2020.07.03 ~ 2020.08.31(348H) - 최종 프로젝트는 3주간 진행
> * 공공데이터 포털, 국가 통계 포털에서  교통사고와 관련된 데이터를 추출하여 도로 형태, 도시 여부, 인구수 등의 영향을 줄 수 있는 컬럼만을 조합하여 위험도를 예측하고자 함. 예측한 정보를 도상에 시각적으로 표현함으로써 국내 교통사고의 위험성을 인식시키고, 사전에 예방하도록 안내하는 서비스 제공

​
​
### 2.2. 프로젝트 진행 과정
> 1. 데이터 수집
>    * [공공데이터 포털](https://www.data.go.kr/)
>    * [교통사고분석시스템](http://taas.koroad.or.kr/)
>    * [KOSIS 국가통계포털](https://kosis.kr/index/index.do)
>    
> 2. 데이터 전처리
>    * 데이터 생성
>    * 결측치 확인
>    * 데이터 범주화
>    
> 3. 시각화
>    * 요일별, 주야별 교통사고 사상자 수
>    * 사상자별 비율
>    * 발생지시도별 사고건수
>    * 발생지시도별 전국 평균과의 위험도 차이
>    * 1/2당사자별 사고건수
>    * 1당사자 * 2당사자별 사고건수
>    * 수집한 교통사고 지점 경,위도 시각화
>    
> 4. 최적의 모델 탐색
>     * KNN
>     * Decison Tree
>     * Logistic Regression
>     * RandomForest
>     * AdaBoost
>     * GredientBoost
>     * Sequential

​
​
### 2.3. 개발 환경
> * 툴 : Anaconda – Jupyter Notebook
> * 언어 : Python(Pandas, Numpy, Sklearn, Seaborn)

​
​ 
# 3. 시각화
* 요일별, 주야별 교통사고 사상자 수(야간 > 주간, 평일 > 주말)
![image](https://user-images.githubusercontent.com/82797757/121136410-982e5e00-c870-11eb-97d9-96943c2b6973.png)
* 사상자별 비율 (사상자가 0인 사고 데이터는 없음)
![image](https://user-images.githubusercontent.com/82797757/121137003-36babf00-c871-11eb-9814-204e9f2247e1.png)
* 발생지시도별 사고건수
![image](https://user-images.githubusercontent.com/82797757/121137251-6ec20200-c871-11eb-826a-ca4a0948d555.png)
* 발생지시도별 전국 평균과의 위험도차이
![image](https://user-images.githubusercontent.com/82797757/121137321-80a3a500-c871-11eb-94cf-f0a3de4c92fd.png)
* 1/2당사자별 사고건수 (가해자는 승용차가, 피해자는 보행자가 많음)
![image](https://user-images.githubusercontent.com/82797757/121137421-94e7a200-c871-11eb-81fe-a18e25c0f560.png)
* 1당사자 X 2당사자별 사고건수 (승용차 * 보행자 사고가 월등히 높음)
![image](https://user-images.githubusercontent.com/82797757/121137574-c1032300-c871-11eb-8e1d-2561f756fe19.png)
* 수집한 교통사고 지점 경,위도 시각화 (수도권 지역과 광역시 부근에 사고가 많이 일어남)
![image](https://user-images.githubusercontent.com/82797757/121137665-db3d0100-c871-11eb-8f3a-075464b89d83.png)


​
​ 
# 4. 모델
* 초기데이터   
![image](https://user-images.githubusercontent.com/82797757/121138431-a54c4c80-c872-11eb-9125-6107f1651d55.png)
* 도시여부 추가   
![image](https://user-images.githubusercontent.com/82797757/121138546-c7de6580-c872-11eb-84e9-51a1c0144455.png)
* 인구수 추가   
![image](https://user-images.githubusercontent.com/82797757/121138576-cdd44680-c872-11eb-96ba-66294aac5061.png)
* 인구수 범주화   
![image](https://user-images.githubusercontent.com/82797757/121138593-d2006400-c872-11eb-87aa-b8e0a017bdc2.png)
* 사고 피해 정도    
![image](https://user-images.githubusercontent.com/82797757/121138882-1c81e080-c873-11eb-8825-f6f5f52ef1c1.png)

​
​ 
# 5. 결론 
### 가장 높은 정확도를 가진 GredientBoost로 선택
~~~
훈련 근사도   : 0.914
테스트 근사도 : 0.914
~~~
### 교통사고 위험도 시각화 (초록 = 안전, 주황 = 주의, 빨강 = 위험)
![image](https://user-images.githubusercontent.com/82797757/121139118-610d7c00-c873-11eb-85c2-288544d87547.png)
![image](https://user-images.githubusercontent.com/82797757/121139131-65d23000-c873-11eb-82d6-73f58e67700f.png)


