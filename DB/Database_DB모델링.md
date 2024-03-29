# 데이터베이스



#### 데이터베이스의 정의

---

* 같은 데이터가 목적이 다른 여러 가지 응용에 중복되어 사용될 수 있다는 **공용의 개념**에 기초를 둠
* 통합된 데이터의 집합
  * 최소의 중복, 통제된 중복
* 저장된 데이터
* 운영 데이터(유지)
* 공용 데이터
  * 응용 시스템들이 공동으로 소유



#### 데이터베이스 저장 구조

---

1. 외부 단계 : 외부 스키마
   * 사용자 개개인이나 응용 프로그래머가 접근하는 데이터베이스의 정의를 기술
2. 개념 단계 : 개념 스키마
   * 전체적인 논리 구조, 필요로 하는 데이터를 통합한 조직 전체의 데이터베이스 하나만 존재
3. 내부 단계 : 내부 스키마
   * 물리적 저장 장치의 입장에서 본 전체 데이터베이스의 명세

* 개념 모델링 => 논리 모델링 => 물리 모델링  -> 산출결과: 내부스키마

* 저장 구조
  * 물리적 구조
    * 컨트롤 파일, 리두로그 파일, 데이터 파일 
  * 논리적 구조
    * 테이블 스페이스, 세그먼트, 익스텐드, 데이터 블록

mySQL => 페이지 단위 저장



#### 데이터베이스 설계

---

* 요구사항 분석 단계

  * 모호성 해결

  * 용어사전 사용

* 설계 단계

  * 요구사항 분석
  * 개념적 설계 -> 엔티티(명사) 표현(골격 작성)
    * 엔티티(명사) 찾기
    * 영속적 데이터 구분
  * 논리적 설계 -> 정규화
  * 물리적 설계 -> 성능 ( 분할, 병합, 반정규화)
    * 분할 -> 수직(모델링 단계), 수평(운영 하면서 필요에 의해)

* 구현 단계

* 운영 단계

* 감시 및 개선 단계     



#### ER 모델

---

* ERD( Entity Relationship Diagram)
* Entity와 이들 간의 관계를 알기 쉽게 미리 약속된 도형을 사용하여 그림으로 표현한 것
  * ex)  사원 : Entity 
  * 사원번호: 식별자
  * 사원명, 주민번호, 주소 .... : 속성

1. Entity
   * 관리하고자 하는 데이터
   * 하나 이상의 속성이 있어야 한다

2. 관계
   * 관련된 업무가 수행되는 규칙
3. 속성
   * 엔티티에 저장되는 개체 집합의 특성을 설명하는 항목
4. 식별자 (변경 불가)
   * 각각의 인스턴스를 구별해주는 속성



#### 정규화

---

* 제 1차 정규화
  * 반복 또는 복수 값을 갖는 속성의 제거(**반복 그룹 제거**)
  * 1:M 의 관계로 설정해야 한다
* 제 2차 정규화
  * 기본 키(Primary Key)에 종속되지 않는 속성의 제거
  * 모든 속성은 반드시 기본 키 완전 함수 종속되어야 한다
* 제 3차 정규화
  * 일반 속성들 간에 함수적 종속 관계가 있는 경우는 기본 키에 대해 이행적 함수 종속이다
  * 따라서 이행적 함수 종속을 제거하는 것이 3차 정규화의 목적



#### index

---

- 자주 조회하는 컬럼에 인덱스를 부여
- 검색 속도 향상 (nlogn 보다 빠르다)
- DML 작업이 많을 때는 비효율적 (계속해서 새로 생성)