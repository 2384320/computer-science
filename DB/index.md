# 인덱스
## Index

- 데이터 검색 작업 속도를 개선하는 데이터 구조

인덱스를 자료구조로 표현하기도 하는데, 인덱스가 트리 구조나 해시 테이블 구조를 사용하기 때문임.

## 구조

- 인덱스는 Key와 Value로 구성됨.
- Key: 검색에 사용되는 Column
- Value: Record를 가리키는 Pointer

다음과 같은 구조를 가진 인덱스를 구현하는데 Hash Table, B-tree, B+tree 구조를 사용함.

### Hash Table

- 해시 테이블의 경우, 해시값을 이용하여 배열의 인덱스를 구하는데, 다음 상황에서 해시 충돌이 발생할 수 있음.
- 해시 충돌(hash collision): 서로 다른 키 값이 같은 해시 값을 반환하여 같은 배열 인덱스에 데이터를 저장
- 거기에 해시 테이블은 등호(=) 연산에 최적화되어 있음. + 해시 테이블 내의 데이터들은 정렬되어 있지 않음. (데이터베이스에선 부등호(<,>) 연산이 자주 사용됨.)

### B-tree

- B-tree 인덱스는 여러 개의 노드로 구성되며, 각 노드는 하나의 데이터 페이지와 연결되어 있음.
- 검색 동작 순서:
  - 인덱스 노드에 접근
  - 인덱스 노드를 검색하여 검색 키와 일치하는 서브 트리 선택
  - 선택된 서브 트리에서 다시 검색
  - 검색 키와 일치하는 데이터 페이지를 찾으면 검색 종료
- B-tree의 경우, 키 값과 데이터 값이 노드 안에 함께 저장되기 때문에 노드 크기가 크고, 디스크 I/O 작업이 많아지는 문제가 있음. -> 개선된 B+tree를 더 많이 사용.

### B+tree

- B-tree와 다르게 데이터 노드의 포인터만 갖고, 모든 데이터는 리프 노드에만 저장함.
- 리프 노드는 서로 연결된 리스트 형태를 이룸.
- 위의 특징들로 인해 B-tree보다 범위 검색 및 저장 공간 사용 면에서 더 나은 성능을 제공함.
- 시간 복잡도의 경우 B-tree와 같은 O(log n)이지만, 노드의 크기가 더 작아 디스크에서 데이터를 읽어오는 비용이 줄고 검색 성능이 좋음.

## 장단점

### 장점

- 빠른 검색 속도
- 중복 데이터 제거
- 데이터 정렬

### 단점

- 생성시간 소요
- 데이터 공간 차지 (10%)
- 데이터 양이 적으면 효율을 내기 힘듦.
- 삽입, 수정, 삭제에 취약함.
  - 인덱스의 가장 큰 문제점은 정렬된 상태를 계속 유지시켜줘야 한다는 점인데, 레코드 내에 데이터 값이 바뀌는 부분이라면 오히려 데이터베이스의 성능을 저하시킬 수도 있음.
  - INSERT, UPDATE, DELETE를 통해 데이터가 추가되거나 값이 바뀐다면 인덱스 테이블 내에 있는 각 요청이 발생할 때마다 값들을 다시 정렬해야 함.
  - 이때, 인덱스 테이블과 원본 테이블 총 두 테이블의 데이터를 정렬해야 하므로 데이터베이스 속도를 절감시킬 수 있음.

## 실습

다음과 같은 사전 준비가 필요함.
```
1) 게시글을 저장하는 테이블 Board
1-1) 테이블에는 다음과 같은 컬럼이 존재할 것: UserNo / Title / Content / UploadYMD / RegDate
1-2) RegDate: 0000-00-00 00:00:00.000 / UploadYMD: 0000-00-00
1-3) 테이블에는 많은 게시글 데이터가 저장되어 있을 것: 적어도 10만은 저장되어 있어야 할 것 같음.
2) 다음 컬럼에 대한 인덱스가 생성되어 있을 것: UploadYMD
```
`24-10-01 ~ 24-10-31에 게시된 모든 게시글을 게시일 기준 내림차순하기`라는 요구사항이 들어온다면?

- 인덱스 O 버전
```
SELECT *
FROM   BOARD WITH(NOLOCK)
WHERE  REGDATE >= '2024-10-01'
AND    REGDATE < '2024-11-01'
ORDER BY REGDATE DESC
```

- 인덱스 X 버전
```
SELECT *
FROM   BOARD WITH(NOLOCK)
WHERE  UploadYMD >= '2024-10-01'
AND    UploadYMD <= '2024-10-31'
ORDER BY UploadYMD DESC
```

(실습 후 내용 갱신)

## 정리하면 좋을 것

- 해시 테이블, b-tree, b+tree 자세하게 다시 다루면 좋을 듯
- 인덱스 종류, 복합 인덱스 내용 넣기

## 참고 자료

- https://velog.io/@kwontae1313/%EC%9D%B8%EB%8D%B1%EC%8A%A4Index%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90