# Unified Modeling Langauge

개발 시스템을 이해하기 쉬운 형태로 표현하여 기획자, 개발자, 아키텍쳐가 효율적으로 의사소통 할 수 있게 해주는 표준화된 모델링 언어이며, 객체지향적인 분석과 설계를 지원함.

## 특징

- 가시화 언어(Visualization Language): 개념 모델 작성 시 오류가 적고 의사소통이 용이함.
- 구축 언어(Construction Language): 다양한 프로그래밍 언어로 실행 시스템 예측이 가능하며, 만들어진 모델링에서 소스 코드로 변환하여 구축하거나 역변환하여 역공학 등의 방식 도입이 가능함.
- 명세화 언어(Specification Language): 정확한 모델링을 제시하여 완전한 모델 작성이 가능함.
- 문서화 언어(Documentation Language): 시스템에 대한 평가 및 의사소통의 문서가 될 수 있음.

## 구성 요소

- 사물(Things)
- 관계(Relationships)
- 다이어그램(Diagrams)

### 사물

모델을 구성하는 가장 중요한 기본 요소로, 다이어그램 안에서 관계가 형성될 수 있는 대상

- 구조 사물(Structural Things): 시스템의 개념적, 물리적 요소를 표현함.
  - EX) Class, UseCase, Component, Node, ..
- 행동 사물(Behavioral Things): 시간과 공간에 따른 요소들의 행위를 표현함.
  - EX) 상호작용(Interaction), 상태 머신(State Machine), ..
- 그룹 사물(Grouping Things): 요소들을 그룹으로 묶어서 표현함.
  - EX) Package
- 주해(사물) 사물(Annotation Things): 부가적인 설명이나 제약조건 등을 표현함.
  - EX) Note

### 관계

#### 연관관계 (Association)

- 연관관계(ㅡ; Association): 양방향 연관관계이므로 연관된 두 사물은 서로를 인지함.
  - EX AㅡB: A와 B는 서로 연관됨.
- 직접연관관계(ㅡ>; Direct): 단방향 연관관계이므로 참조하는 사물만 참조할 사물을 인지함.
  - EX Aㅡ>B: A는 B와 연관됨.
- 집합(ㅡ◇; Aggregation): 집합관계이므로 전체 소멸 시 부분은 사용이 가능함.
  - EX Aㅡ◇B: A는 B의 일부임.
- 합성(ㅡ◆; Composition): 합성관계이므로 전체 소멸 시 부분도 소멸됨.
  - EX Aㅡ◆B: A는 B의 일부이며, B에 합성되어 있음.

#### 의존관계 (Dependency)

- 의존(-->): 다른 클래스를 참조하는 관계를 표현함.
  - 참조: 객체 생성/메서드 호출/매개변수로 객체 사용
  - 의존관계는 확장의존관계(\<\<Extend>>)와 포함의존관계(\<\<Include>>)로 나뉘며, 전자는 선택적 확장되는 관계이며 후자는 반드시 포함하는 관계임. (스테레오 타입(\<\<>>; Stereotype) 사용 = 확장 메커니즘)
  - EX A-->B: A는 B를 참조함.


- vs 직접연관관계
  - 직접연관관계는 참조하는 객체나 클래스가 사용 후에도 **유지되는 관계**임.
  - 반대로 의존관계는 참조하는 객체나 클래스가 사용 후에는 **사라지는 관계**임.

#### 일반화관계 (Generalization)

- 일반화(ㅡ▷): 상속 관계를 표현함.
  - EX Aㅡ▷B: A는 B를 상속 받음.

#### 실체화관계 (Realization)

- 실체화(--▷): 추상 메서드를 오버라이딩하는 관계를 표현함.
  - EX A--▷B: A는 B라는 추상 메서드를 오버라이딩함. (Aㅡⓑ와 같은 의미)

### 다이어그램

#### 구조적 다이어그램 (Structure Diagram)

- 클래스 다이어그램(Class Diagram): 시스템을 구성하는 클래스들 사이의 관계를 표현함.
- 객체 다이어그램(Object Diagram): 객체 정보를 보여줌.
- 컴포넌트 다이어그램(Component Diagram): 컴포넌트 구조 사이의 관계를 표현함.
- 배치 다이어그램(Deployment Diagram): 소프트웨어, 하드웨어, 네트워크를 포함한 실행 시스템의 물리 구조를 표현함.
- 복합체 구조 다이어그램(Composite Structure Diagram): 복합 구조의 클래스와 컴포넌트 내부 구조를 표현함.
- 패키지 다이어그램(Package Diagram): 클래스나 유스케이스 등을 포함한 여러 모델 요소들을 그룹화해 패키지를 구성하고 패키지들 사이의 관계를 표현함.

#### 행위적 다이어그램 (Behavior Diagram)

- 활동 다이어그램(Activity Diagram): 업무 처리 과정이나 연산이 수행되는 과정을 표현함.
- 상태 머신 다이어그램(State Machine Diagram): 객체의 생명주기를 표현함.
- 유스케이스 다이어그램(UseCase Diagram): 사용자 관점에서 시스템 행위를 표현함.
- 상호작용 다이어그램(Interaction Diagram) 
  - 순차 다이어그램(Sequence Diagram): 시간 흐름에 따른 객체 사이의 상호작용을 표현함.
  - 상호작용 개요 다이어그램(Interaction Overview Diagram): 여러 상호작용 다이어그램 사이의 제어 흐름을 표현함.
  - 통신 다이어그램(Communication Diagram): 객체 사이의 관계를 중심으로 상호작용을 표현함.
  - 타이밍 다이어그램(Timing Diagram): 객체 상태 변화와 시간 제약을 명식적으로 표현함.

# 참고 자료

- [UML](https://m.blog.naver.com/wook2124/222103001651)
- [\[UML\]UML(Unified Modeling Language) 이란?](https://lxxyeon.tistory.com/87)
- [2024 #정보처리기사 필기요약 #1-1. UML](https://simuing.tistory.com/entry/2021-%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC-%ED%95%84%EA%B8%B0%EC%9A%94%EC%95%BD-UML)
- [UML 클래스 관계](https://kyoun.tistory.com/100)
- [\[UML 관계\] 구성요소 간의 관계 표기법](https://itproda.tistory.com/101)
