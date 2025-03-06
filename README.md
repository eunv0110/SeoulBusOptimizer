<div align="center">
  <img src="https://github.com/Jangrae/img/blob/master/bus.png?raw=true" width="700px" />
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white" />
  <img src="https://img.shields.io/badge/Matplotlib-3F4F75?style=for-the-badge&logo=matplotlib&logoColor=white" />
</p>

## 📋 프로젝트 개요

> ***"데이터로 그리는 더 나은 서울시 대중교통의 미래"***

본 프로젝트는 서울시 생활정보 데이터를 기반으로 대중교통 수요를 분석하여 버스 노선 추가가 필요한 지역을 선정하는 데이터 분석 프로젝트입니다. KT AIVLE School 1차 미니프로젝트로서, 공공 데이터를 활용해 유용한 교통 정책 수립에 도움이 될 수 있는 인사이트를 도출했습니다.

## 📊 데이터 소개

<table>
  <tr>
    <td><b>분석 기간</b></td>
    <td>2024년 8월 서울시 구별 데이터</td>
  </tr>
  <tr>
    <td><b>출처</b></td>
    <td>서울시 공공데이터포털</td>
  </tr>
  <tr>
    <td><b>활용 데이터</b></td>
    <td>
      • 서울시 구별 버스 승하차 이용 데이터<br>
      • 서울시 구별 생활 인구 데이터<br>
      • 서울시 구별 주민 등록 인구 데이터<br>
      • 서울시 구별 업종 등록 데이터
    </td>
  </tr>
</table>

## 🛠️ 기술 스택

<div>
  <table>
    <tr>
      <th colspan="2" align="center">분류</th>
      <th align="center">기술</th>
      <th align="center">용도</th>
    </tr>
    <tr>
      <td rowspan="5" width="10%">💻</td>
      <td width="20%"><b>언어</b></td>
      <td width="25%">Python</td>
      <td width="45%">전체 프로젝트 개발</td>
    </tr>
    <tr>
      <td rowspan="2"><b>데이터 처리</b></td>
      <td>Pandas</td>
      <td>데이터프레임 조작 및 전처리</td>
    </tr>
    <tr>
      <td>NumPy</td>
      <td>수치 연산 및 배열 처리</td>
    </tr>
    <tr>
      <td rowspan="2"><b>시각화</b></td>
      <td>Matplotlib</td>
      <td>기본 차트 및 그래프 생성</td>
    </tr>
    <tr>
      <td>Seaborn</td>
      <td>고급 통계 시각화</td>
    </tr>
    <tr>
      <td rowspan="2">🤖</td>
      <td><b>통계 분석</b></td>
      <td>SciPy</td>
      <td>상관관계 분석 및 가설 검정</td>
    </tr>
    <tr>
      <td><b>개발 환경</b></td>
      <td>Jupyter Notebook</td>
      <td>코드 작성 및 분석 문서화</td>
    </tr>
  </table>
</div>

## 📝 문제 정의

```
❓ 제공된 서울시 데이터를 분석하여 버스 노선 추가가 필요한 자치구(구 단위)를 선정하는 것
```

## 📊 분석 방법론

### 1️⃣ 데이터 수집 및 전처리
- 4개의 데이터셋(버스 정류장, 유동인구, 상권, 인구)을 '자치구' 기준으로 병합
- 결측치 처리 및 데이터 정제

### 2️⃣ 가설 수립
<div align="center">
<table>
  <tr>
    <th>가설 번호</th>
    <th>가설 내용</th>
  </tr>
  <tr>
    <td align="center">가설 1</td>
    <td>승객수 대비 노선수가 적은 자치구에 버스 노선 추가가 필요하다</td>
  </tr>
  <tr>
    <td align="center">가설 2</td>
    <td>혼잡도가 높은 곳에 노선 추가가 필요하다 -> 노선수가 적으면 혼잡도가 높을 것이다</td>
  </tr>
  <tr>
    <td align="center">가설 3</td>
    <td>이동인구 대비 - 인구가 적으면 이동시간이 길다</td>
  </tr>
  <tr>
    <td align="center">가설 4</td>
    <td>서비스업종과 교육시설의 분포도가 높은 지역이 대중교통, 버스를 더 자주 이용할 것이라 예상 → 더 많은 버스 노선이 필요할 것이다</td>
  </tr>
</table>
</div>

### 3️⃣ 단변량 분석
- 구별 승객수 합계 및 노선수 분석
- 구별 혼잡도 산출 및 분석
- 구별 서비스업 분포도 분석

### 4️⃣ 이변량 분석
- 상관관계 분석을 통해 변수 간의 관계 파악
- 피어슨 상관계수를 이용한 유의성 검정 (유의수준: 5%)

## 🔍 주요 분석 결과

### ✅ 가설 1: 승객수 대비 노선수 분석
<div align="center">
<div style="display: flex; justify-content: center; flex-wrap: wrap;">
  <img width="32%" alt="승객수 대비 노선수 분석 1" src="https://github.com/user-attachments/assets/32944348-8163-4cd1-af9b-3f794cf0b5ba" />
  <img width="32%" alt="승객수 대비 노선수 분석 2" src="https://github.com/user-attachments/assets/f99963c3-87f9-4164-b657-ff9ebb28bf1f" />
  <img width="32%" alt="승객수 대비 노선수 분석 3" src="https://github.com/user-attachments/assets/0e014774-5093-4c69-9aae-1f7cd0a582c8" />
</div>
</div>

- 노선수와 승차/하차 총 승객수 간 **강한 양의 상관관계** 발견
- 버스 노선이 많을수록 승객수도 비례하여 증가하는 경향
- 승차_노선비율 기준 상위 지역: **강동구, 송파구, 관악구**

### ✅ 가설 2: 혼잡도와 노선수 관계
- 혼잡도와 노선수 간의 상관계수: **0.4219**
- p-value: **0.0356** (유의수준 5% 기준 유의함)
- 결론: 노선수가 적으면 혼잡도가 높을 것이라는 가설은 **기각됨**

### ✅ 가설 3: 이동인구와 이동시간 관계
- 이동인구 평균과 평균 이동 시간 상관계수: **0.52**
- p-value: **0.0073** (유의수준 5% 기준 유의함)
- 결론: 인구가 적으면 이동시간이 길다는 가설은 **기각됨**

### ✅ 가설 4: 서비스업종/교육시설 분포도와 버스 이용
<div align="center">
<img width="1184" alt="스크린샷 2025-02-28 오후 11 53 54" src="https://github.com/user-attachments/assets/5b648fe2-f115-4160-918e-eee24ba6e8aa" />
</div>

- 서비스업종과 교육시설의 합계와 평균 승하차 인원 간 **유의미한 상관관계** 발견
- 서비스업/교육시설 비율이 높은 지역: **종로구, 용산구, 서초구, 마포구, 영등포구**

## 💡 결론 및 제언

<div align="center">
<table>
  <tr>
    <th>우선순위</th>
    <th>추천 지역</th>
    <th>근거</th>
  </tr>
  <tr>
    <td align="center">1순위</td>
    <td><b>강동구, 송파구, 관악구</b></td>
    <td>승객수 대비 노선수가 적어 수요 대비 공급이 부족함</td>
  </tr>
  <tr>
    <td align="center">2순위</td>
    <td><b>종로구, 용산구, 서초구, 마포구</b></td>
    <td>서비스업종과 교육시설 분포도가 높아 잠재적 수요가 큼</td>
  </tr>
</table>
</div>

## 📈 상관관계 히트맵

<div align="center">
<img width="717" alt="스크린샷 2025-02-28 오후 11 39 24" src="https://github.com/user-attachments/assets/f4ec8995-8d40-40a8-8c33-47f01b0cac1b" />
</div>

## 📝 프로젝트 배운 점

- 공공 데이터를 활용한 **실제 문제 해결 방식** 학습
- **데이터 기반 의사결정**의 중요성 체득
- 통계적 가설 검정을 통한 **데이터 분석 경험**
- 다양한 데이터셋을 통합하여 **인사이트 도출**하는 능력 향상

## 👨‍💻 참여자 
<div align="center">
  <table>
    <tr>
      <td align="center"><b>구종한</b></td>
      <td align="center"><b>김효연</b></td>
      <td align="center"><b>박지성</b></td>
      <td align="center"><b>조강윤</b></td>
      <td align="center"><b>최재영</b></td>
      <td align="center"><b>황은비</b></td>
    </tr>
  </table>
</div>
