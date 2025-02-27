# E-R (Entity-Relationship) Diagram

> 개체 타입과 이들 간의 관계 타입을 이용해 현실 세계를 개념적으로 표현

- 1:1, 1:N, N:M 등의 관계 유형을 제한 없이 나타낼 수 있음.
- 시스템에 영향받지 않음. (고려 대상 x)
- 설계 변경이 거의 발생하지 않아 데이터 중심의 설계가 가능함.
- 하나의 개체가 물리적으로 하나으 테이블이 되는 것은 아님.

## 표기법

- 개체: 사각형
- 관계: 마름모
- 타원: 속성
- 이중 타원: 다중값 속성
- 밑줄 타원: 기본키 속성
- 복수 타원: 복합 속성 (타원에 타원이 여러 개 연결된 형태)
- 관계: 개체 간 관계에 대한 대응수를 선 위에 기술
- 선, 링크: 개체 타입과 속성을 연결
  - 바커 표기법(Barker Notation): 관계를 링크 위에서 실선/점선으로 구분함. (실선: N / 점선: 1)
  - IE 표기법(Information Engineering Notation): 관계를 링크 위에서 >, |, o 기호를 통해 구분함. (>: N / |: 1 / o: 0)

# 참고 자료

- [\[2021 정보처리기사-3과목\] E-R 다이어그램](https://y-oni.tistory.com/entry/2021-%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC-3%EA%B3%BC%EB%AA%A9-E-R-%EB%8B%A4%EC%9D%B4%EC%96%B4%EA%B7%B8%EB%9E%A8#toc114)
