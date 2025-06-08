# 📊 Bayesian Analysis of H1B Visa Approval Patterns (2022–2024)

This project investigates factors influencing the success of H1B visa petitions using a **hierarchical Bayesian model**. It evaluates how employer application volume, industry sector, and geographic location affect approval probabilities for both initial and continuing applications.

## 🔍 Objectives

1. Quantify the relationship between employer application volume and approval rates  
2. Identify industry sectors with high approval consistency  
3. Analyze geographic patterns in visa petition outcomes  
4. Compare trends in **initial vs continuing** applications  
5. Provide **probabilistic insights** for optimizing application strategies

## 🗂️ Data Description

- **Source**: USCIS H-1B Employer Data Hub (2022–2024)
- **Scope**: 102,865 employers
- **Variables**:
  - Approval counts (initial & continuing)
  - Application volume (binned)
  - NAICS industry codes
  - Employer location (state-level)

## 📈 Methodology

- **Model Type**: Hierarchical Bayesian logistic regression
- **Structure**:
  - Top-level: Volume category  
  - Nested levels: Industry and location effects  
  - Separate models for initial and continuing applications  
- **Priors**:
  - Standard normal for fixed effects  
  - Half-normal for variance components  
- **Implementation**: Stan (`rstan`) with 4 chains, 15,000 iterations each

## ✅ Results

- **Volume Effect**: Strong positive correlation between application volume and approval probability  
- **Industry Trends**: Information, Manufacturing, and Finance consistently show high approval rates  
- **Geographic Insights**: States like CA, IL, MI show strong performance, especially at high volumes  
- **Initial vs Continuing**:
  - Initial applications show more variance, especially for small employers  
  - Continuing applications show higher stability in success probability  

## 🎯 Implications

- **For Employers**:
  - Small employers should target strong industries (e.g., Healthcare, Construction)
  - Larger firms benefit from consistent approvals, especially in tech hubs

- **For Job Seekers**:
  - Larger employers (100+ apps) offer predictable outcomes
  - Industry choice (e.g., Information, Finance) and location significantly affect success

## ⚙️ Tools and Packages

- `R`, `rstan`, `bayesplot`, `ggplot2`, `dplyr`
- MCMC diagnostics and posterior predictive checks
- Density overlays, trace plots, and credible intervals

---

## 📎 Output

- Full PDF report: `451_FinalReport (3).pdf`  
- Includes EDA, modeling formulation, diagnostics, visualizations, and discussion

---

## 🧠 Citation & Resources

- USCIS H-1B Employer Data Hub: https://www.uscis.gov/data-reports/h-1b-employer-data-hub  
- Gelman et al. (2013). *Bayesian Data Analysis*  
- Kruschke (2014). *Doing Bayesian Data Analysis*  
- Stan Team: https://mc-stan.org/rstan/

---

*This project was completed as part of a graduate-level Bayesian statistics course at the University of Michigan.*

---

# 📊 H1B 비자 승인 패턴의 베이지안 분석 (2022–2024)

이 프로젝트는 H1B 비자 신청의 승인 여부에 영향을 미치는 요인을 **계층적 베이지안 모델(hierarchical Bayesian model)**을 통해 분석한 결과입니다. 고용주의 신청 규모, 산업 분야, 지역(주 단위)이 초기 및 갱신 신청 각각의 승인 확률에 어떤 영향을 미치는지를 평가하였습니다.

---

## 🔍 프로젝트 목표

1. 고용주의 신청 규모와 승인률 간의 관계 정량화  
2. 승인 일관성이 높은 산업군 식별  
3. 지역(주별) 승인 패턴 분석  
4. **초기 vs 갱신** 신청 간 승인 경향 비교  
5. 전략 수립을 위한 **확률 기반 인사이트 제공**

---

## 🗂️ 데이터 설명

- **출처**: USCIS H-1B Employer Data Hub (2022–2024)  
- **범위**: 102,865개 고용주  
- **주요 변수**:
  - 승인 건수 (초기 & 갱신)
  - 신청 건수 (구간화됨)
  - NAICS 산업 코드
  - 고용주 위치 (주 단위)

---

## 📈 분석 방법론

- **모델 종류**: 계층적 베이지안 로지스틱 회귀  
- **구조**:
  - 최상위 수준: 고용주 신청 규모 (구간별)  
  - 하위 수준: 산업 효과 + 지역 효과  
  - 초기 신청과 갱신 신청은 **별도로 모델링**  
- **사전 분포 (Priors)**:
  - 고정 효과: 표준 정규분포  
  - 분산 구성요소: Half-Normal 분포  
- **구현 도구**: Stan (`rstan`), 4개의 체인, 각 15,000 반복 샘플링  

---

## ✅ 주요 결과

- **규모 효과**: 신청 규모가 클수록 승인 확률이 높음  
- **산업 경향**: 정보통신, 제조업, 금융업의 승인률이 일관되게 높음  
- **지역 효과**: 캘리포니아(CA), 일리노이(IL), 미시간(MI) 등은 고신청 규모에서 높은 승인 성과  
- **초기 vs 갱신 신청**:
  - 초기 신청은 특히 소규모 고용주에서 변동성이 큼  
  - 갱신 신청은 비교적 안정적인 승인 확률을 보임  

---

## 🎯 실무 적용 시사점

### 👨‍💼 고용주에게:
- 소규모 기업은 의료, 건설 등 승인률이 높은 산업에 집중  
- 대규모 기업은 특히 테크 산업 중심지에서 안정적인 승인률 확보 가능  

### 👩‍💻 구직자에게:
- 연간 **100건 이상 신청하는 대형 고용주**는 예측 가능한 승인 경향  
- **산업 및 지역 선택**이 승인 결과에 중요한 영향  

---

## ⚙️ 사용 도구 및 패키지

- `R`, `rstan`, `bayesplot`, `ggplot2`, `dplyr`  
- MCMC 진단 도구 및 사후 예측검정 (Posterior Predictive Checks)  
- 밀도 중첩 그래프, 트레이스 플롯, 신뢰구간 시각화

---

## 📎 결과물

- 최종 보고서 (PDF): `451_FinalReport (3).pdf`  
- EDA, 모델 수식화, 진단 결과, 시각화, 해석 및 논의 포함

---

## 🧠 참고 자료 및 인용

- USCIS H-1B 데이터 허브: https://www.uscis.gov/data-reports/h-1b-employer-data-hub  
- Gelman et al. (2013). *Bayesian Data Analysis*  
- Kruschke (2014). *Doing Bayesian Data Analysis*  
- Stan 공식 문서: https://mc-stan.org/rstan/

---

*이 프로젝트는 미시간대학교(University of Michigan)의 베이지안 통계 수업의 일부로 수행되었습니다.*

