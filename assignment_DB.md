# 초기 세팅 파일
## DDL
```sql
CREATE TABLE attendance (
  attendance_id INT NOT NULL AUTO_INCREMENT,
  crew_id INT NOT NULL,
  nickname VARCHAR(50) NOT NULL,
  attendance_date DATE NOT NULL,
  start_time TIME,
  end_time TIME,
  PRIMARY KEY (attendance_id)
);
```

## DML
```sql
-- 정규화 이전 상태: attendance(crew_id, nickname, attendance_date, start_time, end_time)
-- crew_id와 nickname 매핑:
-- 1=검프, 2=구구, 3=네오, 4=브라운, 5=브리, 6=포비,
-- 7=워니, 8=리사, 9=제임스, 10=류시, 11=디노, 12=시지프

INSERT INTO attendance (crew_id, nickname, attendance_date, start_time, end_time) VALUES

  -- 검프(crew_id=1)
  (1, '검프', '2025-03-04', '09:45', '18:10'),
  (1, '검프', '2025-03-05', '09:50', '18:05'),
  (1, '검프', '2025-03-06', '09:59', '18:02'),
  (1, '검프', '2025-03-07', '10:00', '18:05'),
  (1, '검프', '2025-03-10', '12:55', '18:10'),
  (1, '검프', '2025-03-11', '09:58', '18:03'),
  (1, '검프', '2025-03-12', '09:55', '18:05'),

  -- 구구(crew_id=2)
  (2, '구구', '2025-03-04', '10:01', '18:01'),
  (2, '구구', '2025-03-05', '09:59', '18:00'),
  (2, '구구', '2025-03-06', '09:58', '17:30'),
  (2, '구구', '2025-03-07', '10:10', '18:00'),
  (2, '구구', '2025-03-11', '09:59', '18:01'),
  (2, '구구', '2025-03-12', '10:02', '18:10'),

  -- 네오(crew_id=3)
  (3, '네오', '2025-03-04', '09:59', '18:00'),
  (3, '네오', '2025-03-05', '10:03', '18:15'),
  (3, '네오', '2025-03-07', '10:00', '17:50'),
  (3, '네오', '2025-03-10', '13:05', '18:10'),
  (3, '네오', '2025-03-12', '09:55', '18:00'),

  -- 브라운(crew_id=4)
  (4, '브라운', '2025-03-04', '09:59', '18:00'),
  (4, '브라운', '2025-03-05', '09:59', '18:00'),
  (4, '브라운', '2025-03-06', '10:00', '18:00'),
  (4, '브라운', '2025-03-07', '10:00', '18:00'),
  (4, '브라운', '2025-03-10', '13:00', '18:00'),
  (4, '브라운', '2025-03-11', '09:59', '18:00'),
  (4, '브라운', '2025-03-12', '09:59', '18:00'),

  -- 브리(crew_id=5)
  (5, '브리', '2025-03-04', '10:20', '18:10'),
  (5, '브리', '2025-03-05', '09:58', '18:02'),
  (5, '브리', '2025-03-06', '09:59', '18:00'),
  (5, '브리', '2025-03-07', '10:02', '18:00'),
  (5, '브리', '2025-03-11', '09:55', '18:00'),
  (5, '브리', '2025-03-12', '09:57', '18:05'),

  -- 포비(crew_id=6)
  (6, '포비', '2025-03-04', '10:15', '17:58'),
  (6, '포비', '2025-03-05', '10:05', '18:05'),
  (6, '포비', '2025-03-10', '13:10', '18:10'),
  (6, '포비', '2025-03-11', '09:52', '18:01'),
  (6, '포비', '2025-03-12', '09:59', '18:00'),

  -- 워니(crew_id=7)
  (7, '워니', '2025-03-04', '10:10', '18:10'),
  (7, '워니', '2025-03-05', '09:50', '18:02'),
  (7, '워니', '2025-03-10', '12:59', '18:05'),
  (7, '워니', '2025-03-12', '10:05', '17:00'),

  -- 리사(crew_id=8)
  (8, '리사', '2025-03-04', '09:55', '18:00'),
  (8, '리사', '2025-03-05', '10:01', '18:03'),
  (8, '리사', '2025-03-06', '10:10', '17:40'),
  (8, '리사', '2025-03-07', '10:02', '18:05'),
  (8, '리사', '2025-03-10', '13:02', '18:00'),
  (8, '리사', '2025-03-11', '10:05', '18:10'),
  (8, '리사', '2025-03-12', '10:03', '18:00'),

  -- 제임스(crew_id=9)
  (9, '제임스', '2025-03-04', '09:55', '18:00'),
  (9, '제임스', '2025-03-05', '09:59', '18:00'),
  (9, '제임스', '2025-03-06', '09:59', '18:10'),
  (9, '제임스', '2025-03-07', '10:05', '18:00'),
  (9, '제임스', '2025-03-10', '12:59', '17:50'),
  (9, '제임스', '2025-03-11', '09:55', '18:00'),
  (9, '제임스', '2025-03-12', '10:01', '18:00'),

  -- 류시(crew_id=10)
  (10, '류시', '2025-03-04', '10:04', '18:00'),
  (10, '류시', '2025-03-05', '10:02', '18:02'),
  (10, '류시', '2025-03-06', '09:45', '18:05'),
  (10, '류시', '2025-03-07', '10:10', '18:00'),
  (10, '류시', '2025-03-10', '13:03', '17:40'),
  (10, '류시', '2025-03-11', '09:57', '18:10'),
  (10, '류시', '2025-03-12', '09:59', '17:30'),

  -- 디노(crew_id=11)
  (11, '디노', '2025-03-04', '09:59', '18:00'),
  (11, '디노', '2025-03-05', '10:10', '18:00'),
  (11, '디노', '2025-03-06', '09:57', '18:05'),
  (11, '디노', '2025-03-07', '10:00', '18:03'),
  (11, '디노', '2025-03-10', '12:57', '18:00'),
  (11, '디노', '2025-03-11', '09:55', '18:00'),
  (11, '디노', '2025-03-12', '10:03', '18:05'),

  -- 시지프(crew_id=12)
  (12, '시지프', '2025-03-04', '09:52', '18:05'),
  (12, '시지프', '2025-03-05', '09:55', '18:00'),
  (12, '시지프', '2025-03-06', '10:15', '18:00'),
  (12, '시지프', '2025-03-07', '10:03', '17:59'),
  (12, '시지프', '2025-03-10', '12:58', '18:10'),
  (12, '시지프', '2025-03-11', '09:55', '18:00'),
  (12, '시지프', '2025-03-12', '10:10', '18:10');
```

## DDL 실습
### 문제 1: 테이블 생성하기 (CREATE TABLE)
```sql
CREATE TABLE crew (
  crew_id INT NOT NULL,
  nickname VARCHAR(50) NOT NULL,
  PRIMARY KEY (crew_id)
);
```
```sql
INSERT INTO crew (crew_id, nickname)
SELECT DISTINCT crew_id, nickname
FROM attendance;
```  

### 문제  2: 테이블 컬럼 삭제하기 (ALTER TABLE)
```sql
ALTER TABLE attendance
DROP COLUMN nickname;
```

### 문제 3: 외래키 설정하기
```sql
ALTER TABLE attendance
ADD CONSTRAINT fk_crew
FOREIGN KEY (crew_id) REFERENCES crew(crew_id);
```

### 문제 4: 유니크 키 설정
```sql
ALTER TABLE crew
ADD CONSTRAINT uq_nickname UNIQUE (nickname);
```

## DML(CRUD) 실습

### 문제 5: 크루 닉네임 검색하기 (LIKE)
```sql
SELECT nickname
FROM crew
WHERE nickname LIKE '디%';
```

### 문제 6: 출석 기록 확인하기 (SELECT + WHERE)
```sql
SELECT *
FROM attendance
WHERE crew_id = (SELECT crew_id FROM crew WHERE nickname = '어셔')
  AND attendance_date = '2025-03-06';
```

### 문제 7: 누락된 출석 기록 추가 (INSERT)
```sql
INSERT INTO attendance (crew_id, attendance_date, start_time, end_time)
VALUES (
  (SELECT crew_id FROM crew WHERE nickname = '어셔'),
  '2025-03-06',
  '09:31:00',
  '18:01:00'
);
```

### 문제 8: 잘못된 출석 기록 수정 (UPDATE)
```sql
UPDATE attendance
SET start_time = '10:00:00'
WHERE crew_id = (SELECT crew_id FROM crew WHERE nickname = '주니')
  AND attendance_date = '2025-03-12';
```

### 문제 9: 허위 출석 기록 삭제 (DELETE)
```sql
DELETE FROM attendance
WHERE crew_id = (SELECT crew_id FROM crew WHERE nickname = '아론')
  AND attendance_date = '2025-03-12';
```

### 문제 10: 출석 정보 조회하기 (JOIN)
```sql
SELECT c.nickname, a.attendance_date, a.start_time, a.end_time
FROM attendance a
JOIN crew c ON a.crew_id = c.crew_id
ORDER BY a.attendance_date, a.start_time;
```

### 문제 11: nickname으로 쿼리 처리하기 (서브 쿼리)
```sql
SELECT *
FROM attendance
WHERE crew_id = (
  SELECT crew_id FROM crew WHERE nickname = '어셔'
);
```

### 문제 12: 가장 늦게 하교한 크루 찾기
```sql
SELECT c.nickname, a.end_time
FROM attendance a
JOIN crew c ON a.crew_id = c.crew_id
WHERE a.attendance_date = '2025-03-05'
  AND a.end_time = (
    SELECT MAX(end_time)
    FROM attendance
    WHERE attendance_date = '2025-03-05'
  );
```

## 집계 함수 실습

### 문제 13: 크루별로 '기록된' 날짜 수 조회
```sql
SELECT c.nickname, COUNT(*) AS date_count
FROM attendance a
JOIN crew c ON a.crew_id = c.crew_id
GROUP BY a.crew_id, c.nickname
ORDER BY a.crew_id;
```

### 문제 14: 크루별로 등교 기록이 있는(start_time IS NOT NULL) 날짜 수 조회
```sql
SELECT c.nickname, COUNT(a.start_time) AS attend_count
FROM attendance a
JOIN crew c ON a.crew_id = c.crew_id
GROUP BY a.crew_id, c.nickname
ORDER BY a.crew_id;
```

### 문제 15: 날짜별로 등교한 크루 수 조회
```sql
SELECT attendance_date, COUNT(*) AS crew_count
FROM attendance
WHERE start_time IS NOT NULL
GROUP BY attendance_date
ORDER BY attendance_date;
```

### 문제 16: 크루별 가장 빠른 등교 시각(MIN)과 가장 늦은 등교 시각(MAX)
```sql
SELECT c.nickname,
       MIN(a.start_time) AS earliest_start,
       MAX(a.start_time) AS latest_start
FROM attendance a
JOIN crew c ON a.crew_id = c.crew_id
WHERE a.start_time IS NOT NULL
GROUP BY a.crew_id, c.nickname
ORDER BY a.crew_id;
```

# 🤔 생각해 보기
## SQL 실습 관련
### 1. 기본키란 무엇이고 왜 필요한가?

기본키란, 테이블에서 각 레코드를 고유하게 식별하는 키다. 
기본키가 있으면 특정 레코드를 정확히 하나만 가리킬 수 있어서, 조회,수정,삭제 시 어떤 행을 대상으로 하는지 명확해진다.

### 2. MySQL에서 사용되는 AUTO_INCREMENT는 왜 필요할까?

일일이 ID값을 지정해야 하는 번거로움을 줄이고, 중복 없는 고유값을 자동으로 생성한다. 이로써 테이블에 로우가 추가될 때마다 새로 생기는 값의 ID생성 오류를 막는다.

### 3. 학생이 등교는 했지만 하교 버튼을 누르지 않았을 때, end_time에 NULL이 저장된다. NULL 값을 처리할 때 주의할 점은?

NULL은 "값이 없음"을 의미하며, 0이나 빈 문자열과는 다르다.
비교 시 `= NULL`이 아닌 `IS NULL` / `IS NOT NULL`을 써야 하고,
`COUNT(컬럼명)`은 NULL을 제외하므로 `COUNT(*)`와 결과가 다를 수 있다.

### 4. crew와 attendance 테이블의 관계를 ER 다이어그램으로 시각화해보자. 이 관계를 일상 생활의 예시로 비유한다면 어떤 것이 있을까?

crew와 attendance는 1:N 관계이다.
하나의 crew는 여러 개의 attendance를 가질 수 있으며,
attendance는 crew_id를 외래키로 가져 crew를 참조한다.

이는 고객-주문, 학생-출석내역 관계와 유사하다.

### 5. 출석 시스템에서 동시에 100명이 등교 버튼을 누른다면 어떤 일이 일어날까? 이 문제를 2026 공통강의 - DB에서 배운 트랜잭션과 ACID 속성으로 설명해보자.

각 INSERT는 별개의 트랜잭션으로 처리된다.
원자성에 의해 각 트랜잭션은 완전히 성공하거나 실패해야 하고,
격리성에 의해 트랜잭션끼리 서로 간섭하지 않아야 한다.
이 두 속성이 없다면 같은 ID가 두 명에게 발급되거나, 절반만 저장된 기록이 생길 수 있다.

### 6. 출석 데이터가 파일(CSV)이 아닌 데이터베이스에 저장되는 이유는 무엇일까? 파일 시스템으로 출석을 관리했다면 어떤 문제가 생길까?

파일로 관리하면 파일에 동시에 접근할 때 덮어쓰기로 데이터가 손실되고,
중복 저장으로 일관성이 깨지며, 검색 시 파일 전체를 읽어야 해서 느리다.
DB는 이런 문제를 트랜잭션, 인덱스, 접근 권한으로 해결한다.

### 7. 출석 데이터를 관계형 DB가 아닌 NoSQL(예: MongoDB)로 저장한다면 테이블 구조가 어떻게 달라질까? 어떤 장단점이 있을까?

크루 문서 안에 출석 배열을 내장하는 구조가 자연스럽다.
스키마가 유연해서 크루별로 다른 정보를 자유롭게 추가할 수 있다는 장점이 있지만,
출석 데이터처럼 구조가 명확하고 집계·조인이 많은 경우엔 RDBMS가 더 적합하다.