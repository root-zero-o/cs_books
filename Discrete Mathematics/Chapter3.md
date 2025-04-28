# 3. 집합론과 디지털적인 수의 세계

## 3.1 집합의 표현

`집합(Set)`이란 수학적 성질을 가지는 객체들의 모임이다.

집합에는 중복되는 원소가 없어야 한다. A = {1, 2, 2, 3} 은 A = {1, 2, 3}으로 표현되어야 한다.

집합을 S라 하고, 하나의 원소를 a라 하면,

- a∈S : a가 집합 S의 원소이다.
- a∉S : a가 집합 S의 원소가 아니다.

### 집합을 표현하는 방법

- 원소 나열법 : `S={1, 2, 3, 4, 5}`
- 조건 제시법 : `S={x|p(x)}`
  - x : 원소를 대표하는 변수
  - p(x) : 원소들이 가지고 있는 성질
  - 예 : `S={x|x는 자연수이고 1 < x < 5}`

### Cardinality

집합 S 내에 있는 서로 다른 원소들의 개수를 그 집합의 `카디날리티(cardinality)` 또는 `원소 수`라 하고 `|S|`라 표기한다.

- `A = {1, 2, 3, 4, 5}`일 때, `|A| = 5`

집합 S1에서 집합 S2로의 일대일 대응인 함수가 존재할 때, S1과 S2가 같은 카디날리티를 가지고 있다고 한다.

- 유한 집합인 경우 만약 S1이 S2의 진부분 집합이면, S1과 S2는 서로 다른 cardinality를 가진다.
- 무한 집합인 경우 S1이 S2의 진부분집합이여도 같은 cardinality를 가진다.
  - S1 = 짝수들의 집합, S2 = 모든 정수들의 집합
  - S1은 S2의 진부분집합
  - 하지만 f(2i) = i로 정의된 함수 f는 짝수에서 모든 정수로의 일대일 대응 함수이기 때문
- 대각선화(diagonalization)

  - 모든 정수들의 집합과 모든 실수들의 집합은 일대일로 대응될 수 없다.
  - 모든 정수들의 집합은 countable하고, 모든 실수들의 집합은 uncountable하기 때문
  - 칸토어의 대각선 논법(Cantor's Diagonal Argument)으로 증명 가능
  - 만약 실수를 자연수처럼 나열할 수 있다고 가정하면, 항상 그 리스트에 없는 실수를 만들어낼 수 있음.

- 즉, 두 개의 집합이 둘 다 가부번형(countable infinite)이라면, 서로 일대일 대응이 가능하므로 cardinality가 같다.
- 둘 중 하나만 가부번형이고, 다른 하나는 비가부번형(uncountable)이라면, cardinality가 다르다.

#### 무한집합

- 실수집합 R과 (0,1)사이의 실수집합의 cardinality는 같다.
- 실수집합 R과 R^2의 cardinality는 같다.
- 실수집합 R보다 실수집합의 모든 부분집합을 모은 멱집합 P(R)이 더 크다.

#### 가산적 집합(countable set)

정수의 집합과 일대일의 대응 관계에 있는 집합들을 `가산적 집합(countable set)` 또는 `가산적으로 무한한 집합(countably infinite set)`이라고 한다.

<br/>

## 3.2 집합의 연산

### 집합의 연산

- 합집합(Union) : 집합 A 또는 집합 B에 속하는 모든 원소의 집합. `A∪B`로 표기한다.
- 교집합(Intersection) : 집합 A에도 속하고 집합 B에도 속하는 모든 원소의 집합. `A∩B`로 표기한다.
  - 집합 A와 집합 B가 공통된 원소를 하나도 가지지 않은 경우(`A∩B = ∅`) = A, B를 서로소(disjoint)라고 한다.
- 차집합(Difference) : 집합 A에 속하고 집합 B에는 속하지 않는 모든 원소들의 집합. `A-B`로 표기한다.
- 대칭 차집합(Symmetric difference) : `A∪B`의 원소 중에서 `A∩B`에 속하지 않는 모든 원소들의 집합. `A⊕B`로 표기한다.
- 곱집합(Cartesian product)
  - 순서쌍(ordered pair) : 순서로 구분되는 원소들의 쌍. `(a,b)`로 나타낸다. 순서로 구분되므로 `(a,b) != (b,a)`이고, `(a,b) = (c,d)`이면 `a=c`이고 `b=d`이다.
  - 곱집합 or 카티시안 곱(Cartesian product)는 `x∈A`이고 `y∈B`인 모든 순서쌍 `(x,y)`의 집합. `A×B`로 표기한다.

### 집합 연산의 cardinality

집합 A, B, C가 유한 집합일 때 아래 식들이 성립한다.

  1. |A∪B| = |A| + |B| - |A∩B|
  2. |A∩B| = |A| + |B| - |A∪B|
  3. |A∪B∪C| = |A| + |B| + |C| - |A∩B| - |A∩C| - |B∩C| + |A∩B∩C|
  4. |A-B| = |A∩B′| = |A| - |A-B|
  5. |AxB| = |A| * |B|

### 집합의 대수법칙

- 멱등 법칙(idempotent law)
  - A∪A = A, A∩A = A
- 항등 법칙(identity law)
  - A∪∅ = A, A∩∅ = ∅, A∪U = U, A∩U = A
- 교환 법칙(commutative law)
  - A∪B = B∪A, A∩B = B∩A
- 결합 법칙(associative law)
  - (A∪B)∪C = A∪(B∪C), (A∩B)∩C = A∩(B∩C), (A⊕B)⊕C = A⊕(B⊕C)
- 분배 법칙(distributive law)
  - A∪(B∩C) = (A∪B)∩(A∪C), A∩(B∪C) = (A∩B)∪(A∩C)
- 흡수 법칙(absorption law)
  - (A∩B)∪A = A, (A∪B)∩A = A
- 보 법칙(complement law)
  - A′′ = A
- 역 법칙(inverse law)
  - A∪A′ = U, A∩A′ = ∅, U′ = ∅, ∅′ = U
- 드 모르간의 법칙(De Morgan's law)
  - (A∪B)′ = A′∩B′, (A∩B)′ = A′∪B′
- 기타 법칙
  - A-B = A∩B′, A-A = ∅, A-∅ = A

### 쌍대(duality)

집합에 관한 명제에서 그 명제 안에 있는 교집합과 합집합을 전체 집합에 대한 여집합으로 바꾸어서 만든 새로운 명제를 원래 명제의 쌍대(duality)라고 한다.

(A∪B)′ = A′∩B′ 를 쌍대로 바꾸면 (A∩B)′ = A′∪B′

