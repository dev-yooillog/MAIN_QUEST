# Hotel Booking Data Cleaning Project

### Project Overview
호텔 예약 데이터셋을 활용하여 데이터 분석의 전처리 과정인 **Data Cleaning**을 수행한 프로젝트입니다. 결측치 처리, 비논리적 데이터 제거, 중복 데이터 정제 등을 통해 데이터의 신뢰도를 높이는 데 집중했습니다.

### Tech Stack
- **Language:** Python
- **Library:** Pandas, Matplotlib, Seaborn
- **Environment:** Google Colab

### Data Cleaning Process & Results

#### 1. 데이터 파악 및 결측치(Missing Values) 처리
- **Children:** 결측치 4건을 0으로 대체.
- **Country:** 결측치 488건을 'Unknown'으로 대체하여 데이터 손실 최소화.
- **Agent/Company:** 예약 대행사 정보가 없는 경우 '0'으로 채우고 데이터 타입을 정수형(Int)으로 변환.

#### 2. 이상치(Outlier) 및 오류 데이터 제거
- **유령 예약 제거:** 성인, 아동, 영유아의 합계가 0명인 비정상 데이터 식별 및 제거.
- **비논리적 예약 제거:** 성인 없이 미성년자만 예약된 데이터 필터링.

#### 3. 중복 데이터(Duplicates) 처리
- 분석의 신뢰도를 높이기 위해 완전히 동일한 예약 내역 **31,976건**을 제거했습니다.

#### 4. Feature Engineering (파생 변수 생성)
- `total_guests`: 전체 투숙객 수 (adults + children + babies)
- `total_stay_days`: 총 숙박 일수 (weekend + week nights)
- `is_family`: 가족 단위 여행객 여부 (아이/영아 포함 시 1)

### Final Data Summary
| 단계 | 데이터 개수 (Rows) | 비고 |
| :--- | :--- | :--- |
| **Raw Data** | 119,390 | 원본 데이터 |
| **After Cleaning** | 118,987 | 이상치 제거 후 |
| **Final Cleaned** | **87,011** | **중복 제거 완료 (최종)** |

---
### Insights from Visualization
- 호텔 타입별 예약 및 취소 현황 분석 결과, City Hotel의 예약 및 취소 빈도가 더 높게 나타남을 확인했습니다.
- 월별 예약 추이를 통해 성수기와 비성수기의 트렌드를 파악했습니다.
