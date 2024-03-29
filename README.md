# 국가별 유망품목 추천 모델(로직) 개발
제11회 산업통상자원부 공공데이터활용 BI 공모전 빅데이터 분석 과제

## 🖥️ 프로젝트 소개
[명칭]
품목별 對한국 의존도를 바탕으로 한 국가별 수출 유망 품목 추천 서비스 - 국가별 당해 수출실적이 없는 품목을 중심으로

[제안배경]
- 2023년 1월 무역 수지 적자가 사상 최대치를 기록하고, 경상수지가 11년 만에 처음으로 1월, 2월 두 달 연속 적자를 기록하는 상황에서, 상품/무역수지 및 경상수지 개선을 위해서 대외 수출 확대가 필수적인 상황이다. 따라서, 다양한 정보를 활용하여 수출에 더 유리한 국가에 품목을 판매한다면 더욱 효율적이고 효과적인 해결책이 될 수 있다.
- 현재 제공하는 KOTRA '트라이빅(TriBIG)' 서비스와 한국무협협회(KITA)에서는 'AI 빅데이터 맞춤 분석' 서비스에서 AI 수출 유망시장 추천을 제공하고 있다. 그러나, 이런 기존 서비스들은 원래 교역이 많은 주요국에 대한 정보를 요약 제공하거나, 현재 교약이 많은 국가를 모두 유망시장으로 상정하고 있다는 한계가 존재한다.

## ⏰ 기간
- 23.5.1 ~ 23.7.10
### 🧑‍🤝‍🧑 팀원
- 김성주, 이남선, 조규원

## 📜 프로젝트 설명
- 완전히 새로운 시장을 개척 및 선점하는 기회를 얻기 위해 유망시장의 정의를 '현재는 수출하지 않지만 향후에는 수출할 가능성이 높은 시장'으로 재정의하고, 변수 간 보이지 않는 상호작용까지 포착하여 추천할 수 있도록 개발된 추천시스템 모델을 사용하여 유망시장 추천이라는 주제에 보다 적합하도록 개발하였다.
- '품목별 對한국 의존도 변수'를 생성하여 국가별 수출 실적이 없는 품목을 중심으로 CF, FM 모델을 활용하여 추천서비스를 개발 및 제공하고자 하였다.

## 💽 사용 데이터
1) 인구
- 1960년 ~ 2023년까지의 데이터 중에서 2012~2022년의 데이터 활용
- 해당 데이터로 얻은 변수 : 인구, 인구 증가율
- 출처 : https://data.worldbank.org/indicator/SP.POP.TOTL?end=2022&start=2008
2) GDP
- 1960년 ~ 2023년까지의 데이터 중에서 2012~2022년의 데이터 활용
- 해당 데이터로 얻은 변수 : GDP, GDP 성장률
- 출처 : https://data.worldbank.org/indicator/NY.GDP.MKTP.CD
3) 품목별 국가별수출입실적
- 조회기간 : 2012년 ~ 2022년
- 국가명 : 국가 다중 선택으로 모든 나라의 데이터 수집
- 해당 데이터로 얻은 변수 : 국가명, 품목명, 품목코드(HS Code 2자리), 수출액
- 출처 : https://unipass.customs.go.kr/ets/index.do?menuId=ETS_MNU_00000107
4) 4개 통화(USD, EUR, JPY, CNY) 환율
- 조회일 : 연도별 체크, 2012년~2022년 평균 환율 데이터 수집
- 해당 데이터로 얻은 변수 : 4개 통화(USD, EUR, JPY, CNY)
- 출처 : https://spot.wooribank.com/pot/Dream?withyou=FXXRT0016
5) 유가(WTI)
- 2012년 ~ 2022년의 유가 데이터 모두 수집
- 해당 데이터로 얻은 변수 : 유가(WTI)
- 출처 : https://kr.investing.com/commodities/crude-oil-historical-data

## 📤 서비스 예시 화면
![prototype](https://github.com/seongjuu/kotra_recsys/assets/118152532/cb7caa3a-653b-469e-9408-7da6616b4037)
