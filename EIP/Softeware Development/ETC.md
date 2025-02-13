# ETC

## 수식의 표기법

- 전위 표기법(Prefix): +AB
- 중위 표기법(Infix): A+B
- 후위 표기법(Postfix): AB+

### Infix → Prefix, Postfix

> X = A / B * (C + D) + E

- Prefix: =X+*/AB+CDE
- Postfix: XAB/CD+*E+=

### Prefix → Infix

> + / A - B C * D + E F

- Infix: A / (B - C) + D * (E + F)

### Postfix →  Infix

> A B C - / D E F + * +

- Infix: A / (B - C) +  D * (E + F)
