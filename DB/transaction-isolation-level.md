# 트랜잭션 격리 수준
## Transaction Isolation Level

- 트랜잭션이 실행되고 있을 때 다른 트랜잭션의 접근 권한에 대한 수준
- 격리 수준 단계가 높아질수록 데이터 일관성이 높아지지만 동시성은 저하됨.

## 트랜잭션 격리 관련 문제점

- Dirty Read: 트랜잭션이 실행되고 있을 때 커밋되지 않은 데이터를 읽는데, 해당 트랜잭션이 롤백되면 오류 데이터를 읽을 수 있음.
- Non-Repeatable Read: 같은 데이터를 한 트랜잭션에서 select함에도 불구하고 값이 달라짐. 
- Phantom Read: 한 트랜잭션 안에서 일정 범위 레코드를 두 번 이상 읽을 때, 첫번째 쿼리에서 없던 레코드가 두번째 쿼리에서 나타남.

## 트랜잭션 격리 수준 단계

1. Read Uncommitted: 트랜잭션 실행 중 다른 트랜잭션 접근 가능 (트랜잭션 격리 X)

- Dirty Read: A 트랜잭션이 test1을 test2로 변경, B 트랜잭션은 변경된 test2를 조회 / 이때 A 트랜잭션이 롤백이 된다면, B 트랜잭션에서 조회한 값은 test1가 됨. -> Dirty Read 발생
- Non-Repeatable Read: A 트랜잭션에서는 select를 반복 실행, B 트랜잭션에서는 데이터 갱신 / A 트랜잭션의 조회 결과가 달라짐 -> Non-Repeatable Read 발생
- Phantom Read: A 트랜잭션에서는 select를 반복 실행, B 트랜잭션에서는 데이터 추가 및 삭제 / A 트랜잭션의 조회 결과 수가 달라짐 -> Phantom Read 발생

2. Read Committed: 트랜잭션 완료 시 다른 트랜잭션 접근 가능

- Dirty Read: A 트랜잭션이 test1을 test2로 변경, B 트랜잭션은 변경되기 전의 test1을 조회 / 아직 A 트랜잭션이 커밋되지 않았으므로 B 트랜잭션은 수정 후의 데이터에 접근이 불가능하여 수정 전의 데이터를 조회함. -> Dirty Read 발생 X
- Non-Repeatable Read: A 트랜잭션에서는 select를 반복 실행, B 트랜잭션에서는 데이터 갱신 / 이때 A 트랜잭션이 커밋된다면, 커밋 전의 조회 결과와 커밋 후의 조회 결과가 달라짐. -> Non-Repeatable Read 발생
- Phantom Read: A 트랜잭션에서는 select를 반복 실행, B 트랜잭션에서는 데이터 추가 및 삭제 / 이때 A 트랜잭션이 커밋된다면, 커밋 전의 조회 결과 수와 커밋 후의 조회 결과 수가 달라짐. -> Phantom Read 발생

3. Repeatable Read: 트랜잭션 범위 내에서 조회한 내용이 항상 동일함을 보장함

- Dirty Read: Read Committed와 같음. -> Dirty Read 발생 X
- Non-Repeatable Read:  A 트랜잭션에서는 select를 반복 실행, B 트랜잭션에서는 데이터 갱신 / A 트랜잭션이 커밋된다 하더라도, B 트랜잭션 내의 조회 내용은 항상 동일성 보장 -> Non-Repeatable Read 발생 X
- Phantom Read: A 트랜잭션에서는 select를 반복 실행, B 트랜잭션에서는 데이터 추가 및 삭제 / 이때 A 트랜잭션이 커밋된다면, 커밋 전의 조회 결과 수와 커밋 후의 조회 결과 수가 달라지는데, 이는 Repeatable Read가 새로운 레코드의 삽입 및 삭제까지는 막지 않기 때문임. -> Phantom Read 발생

4. Serializable: 한 트랜잭션에서 읽고 쓰는 레코드는 다른 트랜잭션에서는 절대 접근이 불가능

- 읽고 쓰는 레코드까지 제어하기 때문에 전체 문제점 발생 X

## 트랜잭션 격리 수준 제어 표
O: 제어, X: 제어 불가능
| |	Dirty Read | Non-Repeatable Read | Phantom Read |
|---|---|---|---|
| Read Uncommitted | X | X | X |
| Read Committed | O | X | X |
| Repeatable Read |	O | O |	X |
| Serializable | O | O | O |

## 더 알아보기

### Non-Repeatable Read VS Phantom Read

- 사용자 A가 동일한 쿼리를 두 번 실행할 사이에 사용자 B는 트랜잭션을 실행 및 커밋함.
- Non-Repeatable Read: 사용자 A가 쿼리한 A 행은 두번째에는 값이 달라짐.
- Phantom Read: 쿼리의 모든 행은 전후에 같은 값을 갖지만, 다른 행이 선택됨. 사용자 B는 트랜잭션을 통해 일부를 삭제하거나 삽입했기 때문임.

-> Non-Repeatable Read의 경우, 다른 트랜잭션에서 커밋된 UPDATE를 읽을 때 발생하며, Phantom Read의 경우, 다른 트랜잭션에서 커밋된 INSERT 및 DELETE를 읽을 때 발생함.

-> Non-Repeatable Read는 하나의 레코드의 값이 한 트랜잭션 내에서 다르게 조회될 수 있음을 얘기하는 것이고, Phantom Read는 하나의 트랜잭션 내에서 조회 쿼리 결과 레코드의 수가 달라질 수 있음을 얘기함.

### with(nolock)과의 관계

- with(nolock)의 경우, 격리성 제한이 걸린 DB의 Read Uncommitted를 허용하여, 실시간으로 데이터를 확인할 때 주로 사용함.
- 데드락이나 교착상태가 발생하지 않음. (with(nolock) 없이 수행할 경우, DB의 성능이 떨어지고, 데드락이 발생될 수 있음.)
- 롤백될 수 있는 데이터까지 읽기 때문에 일관성은 저하됨.
- 기본적으로 MSSQL의 기본 격리수준이 Read Committed이므로, with(nolock)을 사용해야 함.

#### with(readuncommitted)

- 트랜잭션이 실행된 상태에서는 테이블에 잠금이 설정되는데, with(readuncommitted)를 사용하면 트랜잭션에 의한 잠금을 무시하고 접근할 수 있음.
- with(nolock)과는 동일한 역할을 함.

## 노트

- [MVCC와 Phantom Read에 대한 글도 있었는데](https://parkmuhyeun.github.io/woowacourse/2023-11-28-Repeatable-Read/), 이거도 나중에 정리하면 좋을 것 같다. 

## 참고 자료

- https://blackas119.tistory.com/52
- https://ryean.tistory.com/32
- https://stackoverflow.com/questions/11043712/non-repeatable-read-vs-phantom-read
