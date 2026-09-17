# 운동 기록 관리 - CRUD Frontend Service

## Service Topic
운동 기록을 관리하는 CRUD 서비스. 날짜별 운동 종목, 시간, 칼로리 등을 기록하고 목록으로 확인할 수 있다.

---

## Data Fields

| 필드 | 타입 | 설명 |
|------|------|------|
| id | number | 레코드 고유 번호 |
| date | string (date) | 운동한 날짜 (YYYY-MM-DD) |
| sport | string | 운동 종목 (러닝, 수영, 헬스 등) |
| time | number | 운동 시간 (분 단위, 1~300) |
| cal | number | 소모 칼로리 (kcal) |
| intensity | string | 운동 강도 (낮음 / 보통 / 높음) |
| memo | string | 메모 (100자 이내, 선택) |
| done | boolean | 목표 달성 여부 |

---

## List Page (index.html)

테이블에 표시하는 필드 (6개):

- 번호 (id)
- 날짜 (date)
- 종목 (sport) - 클릭 시 view.html로 이동
- 운동시간 (time)
- 칼로리 (cal)
- 달성여부 (done) - Bootstrap badge로 완료/미완료 표시

---

## Validation (add.html / edit.html)

| # | 조건 | 대상 필드 |
|---|------|----------|
| 1 | 날짜 필수 입력 | date |
| 2 | 종목 필수 입력 (공백 불가) | sport |
| 3 | 운동시간 1~300분 범위 내 숫자 | time |
| 4 | 강도 선택 필수 (기본값 미선택 불가) | intensity |
| 5 | 메모 100자 이내 | memo |

---

## RWD

- **공통**: `<meta name="viewport" content="width=device-width, initial-scale=1.0">` 적용
- **Desktop**: container로 중앙 정렬, 테이블 전체 컬럼 표시
- **Mobile**: Bootstrap의 반응형 grid 및 container가 자동으로 패딩/너비 조정. add/edit 폼은 max-width: 600px`으로 좁은 화면에서도 가독성 유지
- 별도 미디어 쿼리 없이 Bootstrap 유틸리티 클래스로 처리

---

## Bootstrap Components & Classes

| 항목 | 사용 위치 |
|------|----------|
| `table table-hover table-striped table-bordered` | index.html 목록 테이블 |
| `table-dark` | 테이블 헤더 |
| `badge bg-success / bg-secondary` | 달성여부 표시 |
| `btn btn-primary / btn-secondary / btn-warning / btn-danger` | 각 페이지 버튼 |
| `form-control`, `form-select`, `form-check` | add/edit 폼 입력 요소 |
| `form-label`, `fw-bold`, `text-danger` | 폼 라벨 스타일 |
| `d-flex`, `justify-content-between`, `align-items-center` | 헤더 레이아웃 |
| `gap-2`, `mb-3`, `mb-4`, `mt-5` | 간격 유틸리티 |
| `card`, `card-footer` | view.html 상세 페이지 |
| Bootstrap Icons (`bi bi-plus-lg`, `bi bi-check-lg`) | 버튼 아이콘 |

---
## Problem & Solution

- exmpl 을 구성하던 도중에 유사하게 진행을 하던 도중 버튼 안에 있던 아이콘이 보이지 않아
30분정도 확인을 했었다. 아이콘에 경우에는 <i> </i> 를 통해서 기본적인 아이콘들을 표시할 수 있다는 것을 찾아본 후 알게 되었고
이후 수정을 한 후 재배포하여 정상적으로 아이콘이 표시되게 되었다. 


--- 

## Reflection

- 이번 과제를 통해서 html 작동 방식에 대해서 더 자세하게 알 수 있었다. 
하지만 url을 통해서 다른 파일로 넘어가는 방식이 가능하다는 것을 알게 되었는데 이럴 경우에는 js 즉 반응형 페이지가 현재 페이지와 다른 것이 차이점이 무엇인지 아직까지 잘 모르겠다.
