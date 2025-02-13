# Requirement

> 요구사항 | 시스템이 무엇을 해야 할지에 대해 서술한 것 (=소비자의 니즈)

## 구분

- **기능 요구사항**: 기능, 입출력, 저장, 수행 등 시스템이 제공해야 하는 서비스의 서술문
- **비기능 요구사항**: 성능, 품질, 제약사항, 호환성, 보안 등 시스템이 사용자에게 제공하는 특정 서비스와 직접적으로 관련되지 않은 요구사항

+) 맞추다 25년 필기 1회차 25번

'차량 대여 시스템이 제공하는 모든 화면이 3초 이내에 사용자에게 보여야 한다' → 해당 문장에서 "모든 화면이 3초 이내에 보여야 한다"는 비기능적 요구사항

## 요구사항 개발 프로세스

> 도출/추출 → 분석 → 명세 → 확인/검증

### 1. 요구사항 도출 (Requirement Elicitation)

- 서로의 의견이 어디에 있는지, 어떻게 수집할 것인지 식별하고 이해하는 과정
- 개발자와 고객 사이의 관계가 만들어지고 이해관계자(Stakeholder)가 식별됨.
- SDLC동안 지속적으로 반복됨.
- EX) 청취와 인터뷰, 설문, 브레인스토밍, 워크샵, 프로토타이핑, 유스케이스 등

### 2. 요구사항 분석 (Requirement Analysis)

- 요구사항 중 명확하지 않거나 모호한 부분은 걸러내는 과정
- 타당성을 조사하거나 비용과 일정 제약을 설정하고, 내용이 서로 상충되는 요구사항이 있으면 중재함.
- EX) UML, 자료 흐름도(DFD; Data Flow Diagram), 자료 사전(DD; Data Dictionary), ERD, 상태 전이도(STD) 등

#### 요구사항 분석 기법

> 요구사항 분류 → 개념 모델링 생성 및 분석 → 요구사항 할당 → 요구사항 협상 → 정형 분석

- 요구사항 분류: 요구사항을 기능적 요구사항과 비기능적 요구사항으로 분류
- 개념 모델링 생성 및 분석
- 요구사항 할당
- 요구사항 협상
- 정형 분석(=정형 기술 검토): 소프트웨어 기술자들에 의해 수행되는 검토 방법
  - 의제 및 논쟁, 반박의 제한성
  - 제품 검토의 집중성
  - 참가 인원의 제한성

+) 맞추다 25년 필기 1회차 281번

정형 기술 검토의 경우, 참가 인원을 제한하여 검토의 효율성과 효과를 높임.

#### CASE

> CASE(Computer-Aided Software Engineering) | 요구사항을 자동으로 분석, 요구사항 명세서를 기술하도록 개발된 요구사항 분석을 위한 자동화 도구

##### 분류

- 상위(Upper) CASE: 모델들 사이의 모순 검사, 모델의 오류 검증, 자료 흐름도 작성 등 지원
- 하위(Lower) CASE: 코드의 작성과 테스트, 문서화하는 과정 지원
- 통합(Integrate) CASE: 소프트웨어 생명 주기 전체 과정 지원

##### 원천 기술

- 구조적 기법
- 프로토타이핑 기술
- 자동 프로그래밍 기술
- 정보 저장소 기술
- 분산처리 기술

##### CASE 종류

- SADT(Structured Analysis & Design Technique): 블록 다이어그램을 채택한 자동화 도구
- SREM(Software Requirement Engineering Methodology): 실시간 처리 소프트웨어 시스템에서 요구사항을 명확히 기술할 목적으로 개발한 도구
- PSL/PSA: PSL과 PSA를 사용하는 도구
- TAGS(Technology for Automated Generation of Systems): 개발주기 전과정에서 이용 가능한 통합 자동화 도구

#### HIPO

> HIPO(Hierarchy Input Process Output) | 시스템 분석, 설계, 문서화에 사용되는 도구

- 기본 시스템 모델은 입력, 처리, 출력으로 구성됨.
- 하향식 소프트웨어 개발을 위한 문서화 도구

##### HIPO Chart

- **가시적 도표(Visual Table of Contents)**: 시스템 전체 기능 및 흐름을 Tree 구조로 표현
- **충체적 다이어그램(Overview Diagram)**: 프로그램 구성 기능을 표현 (입력, 처리, 출력 overall)
- **세부적 다이어그램(Detail Diagram)**: 세부적으로 표현

### 3. 요구사항 명세 (Requirement Specification)

- 명확하지 않거나 모호해 이해되지 않는 부분을 발견하고 걸러내는 과정
- 기능 요구사항에서는 완전, 명백하게 기술하며, 비기능 요구사항에서는 필요한 것만 명확히 기술함.
- 사용자가 이해하기 쉽고, 개발자가 효과적으로 설계할 수 있도록 작성해야 함.
- EX) 소단위 명세서(Mini-Spec)

#### 정형 명세 기법

- 수학적 기호, 정형화된 표기법
- 특정: 간결한 표현, 작성자 독립적 결과(완전성 검증 가능), 표기법 어려움
- EX) VDM, Z, Petri-net, CSP

#### 비정형 명세 기법

- 상태, 기능, 객체를 중심으로 자연어 및 다이어그램 작성
- 특징: 자연어라 일관성은 떨어지지만 의사소통 용이
- EX) FSM, Decision Table, ER 모델링, State Chart(SADT)

### 4. 요구사항 확인 (Requirement Validation)

- 개발 자원을 요구사항에 할당하기 전, 명세서가 정확하고 완전하게 작성되었는지 검토하는 활동
- 요구사항 검토 계획 수립 → 검토 및 오류 수정 → 베이스 라인 설정

# 참고 자료

- [요구사항 정의](https://m.blog.naver.com/wook2124/222103001064)
- [\[소프트웨어 공학\] 기능적, 비기능적 요구(Functional, Non-Functional Requirement) - 4-1](https://jelong.tistory.com/entry/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4-%EA%B3%B5%ED%95%99-%EA%B8%B0%EB%8A%A5%EC%A0%81-%EB%B9%84%EA%B8%B0%EB%8A%A5%EC%A0%81-%EC%9A%94%EA%B5%ACFunctional-Non-Functional-Requirement-Engineering-4-1)
- [\[정보처리기사/필기\] 1장. 요구사항 확인(2)](https://velog.io/@jiwon3378/%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4-%EC%84%A4%EA%B3%84-1%EC%9E%A5.-%EC%9A%94%EA%B5%AC%EC%82%AC%ED%95%AD-%ED%99%95%EC%9D%B82)
- [1-소프트웨어 설계. 1. 요구 사항 확인. 2) 요구 사항 분석](https://velog.io/@kjh03160/1-%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4-%EC%84%A4%EA%B3%84.-1.-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%ED%99%95%EC%9D%B8.-2-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EB%B6%84%EC%84%9D)
- [(소프트웨어공학) FTR 정형 기술 검토 개념 설명](https://kkh0977.tistory.com/589)
- [\[정보처리기사/필기\] 1. 소프트웨어 설계](https://velog.io/@stringbuckwheat/%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC-%ED%95%84%EA%B8%B0-1%EA%B3%BC%EB%AA%A9-%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4-%EC%84%A4%EA%B3%84-%EC%9A%94%EC%95%BD#1-%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4-%EC%83%9D%EB%AA%85-%EC%A3%BC%EA%B8%B0)
- [\[정보처리기사 필기\] 1과목.소프트웨어 설계 핵심 요약 - 요구사항 분석 및 설계 도구](https://blog.naver.com/gisafirst/222686734081)
