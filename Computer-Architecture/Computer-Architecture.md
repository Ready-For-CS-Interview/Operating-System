# Computer-Architecture

---

## Index
1. [내용](#1-내용)
2. [질문 및 답변](#2-질문-및-답변)

---

## 1. 내용

<details>
<summary>1-1. 컴퓨터 구성</summary>
<a href="https://velog.io/@jooon/%EC%9E%90%EB%A3%8C-%EA%B5%AC%EC%A1%B0-Array-Linked-List" target="_blank">
컴퓨터 구성 정리글
</a>
</details>

<details>
<summary>1-2. CPU 작동원리</summary>
<a href="https://velog.io/@jooon/%EC%9E%90%EB%A3%8C-%EA%B5%AC%EC%A1%B0-Array-Linked-List" target="_blank">
CPU 작동원리 정리글
</a>
</details>

<details>
<summary>1-3. 숫자표현법</summary>
<a href="https://velog.io/@jooon/%EC%9E%90%EB%A3%8C-%EA%B5%AC%EC%A1%B0-Array-Linked-List" target="_blank">
숫자표현법 정리글
</a>
</details>


<details>
<summary>1-4. Cache Memory</summary>
<a href="https://velog.io/@jooon/%EC%9E%90%EB%A3%8C-%EA%B5%AC%EC%A1%B0-Array-Linked-List" target="_blank">
Cache Memory 정리글
</a>
</details>


<details>
<summary>1-5. Parity Bit</summary>
<a href="https://velog.io/@geooeg/%EC%BB%B4%ED%93%A8%ED%84%B0-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98-Parity-bit" target="_blank">
Parity bit 정리글
</a>
</details>


<details>
<summary>1-6. RAID</summary>
<a href="https://velog.io/@geooeg/%EC%BB%B4%ED%93%A8%ED%84%B0-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98-RAID" target="_blank">
RAID 정리글
</a>
</details>

---

## 3. 질문 및 답변
<details>
<summary><b>Array와 linked list의 차이</b></summary>
배열은 연속된 메모리 공간에 같은 타입의 데이터를 저장하는 구조이다. 인덱스를 통해 O(1) 시간에 임의 접근이 가능하지만, 크기가 고정되어 있고 중간 삽입이나 삭제 시 데이터 이동이 필요해 O(n)의 비용이 발생한다. 또한 배열은 연속된 메모리 덕분에 캐시 적중률이 높아 순차 접근 성능이 좋고, Linked List는 포인터를 따라가야 해서 캐시 효율이 떨어진다. 반면, Linked List는 각 노드가 포인터를 통해 연결된 구조로, 메모리가 연속적일 필요는 없다. 중간 삽입/삭제는 포인터만 조작하면 되기 때문에 삽입과 삭제가 빠른 반면, 임의 접근은 지원하지 않아 O(n) 시간이 걸린다.
</details>

<details>
<summary><b>Hash Function, HashTable 설명</b></summary>
해시 함수는 어떤 데이터를 고정된 크기의 데이터로 변환하는 함수이다. 예를 들어 문자열을 입력받아 배열 인덱스로 변환할 수 있도록 해준다. 
해시 테이블은 이 해시 함수를 활용해서 데이터를 빠르게 저장하고 검색하는 자료구조이다. 일반적으로 key-value 쌍으로 구성되어 있고, 키를 해시 함수에 넣으면 결과값을 인덱스로 사용해 데이터를 배열에 저장한다. 이 방식 덕분에 평균적으로 탐색, 삽입, 삭제 연산이 O(1) 시간에 가능하다. 
다만 해시 함수가 서로 다른 키를 같은 인덱스로 매핑할 수 있는데, 이를 해시 충돌이라고 하고, 체이닝이나 오픈 어드레싱 같은 방식으로 해결한다.
</details>

<details>
<summary><b>Stack,Queue,Deque의 차이</b></summary>
스택(Stack)은 LIFO 구조이다. 마지막에 삽입된 데이터가 가장 먼저 삭제된다. 삽입과 삭제는 모두 한쪽 끝(Top)에서만 이루어진다. 함수 호출 스택, 되돌리기 기능 등에 사용된다.
큐(Queue)는 FIFO 구조이다. 먼저 삽입된 데이터가 먼저 삭제된다. 데이터는 뒤에서 삽입되고 앞에서 삭제된다. 프로세스 스케줄링, 작업 대기열 등에 사용된다.
덱(Deque)은 Double-Ended Queue의 줄임말로, 양쪽 끝에서 삽입과 삭제가 모두 가능한 자료구조이다.
스택처럼 사용할 수도 있고, 큐처럼도 사용할 수 있다. 슬라이딩 윈도우 최적화, LRU 캐시 구현 등에 활용된다.
</details>

<details>
<summary><b>Heap, Pirority Queue 설명</b></summary>
Heap은 완전 이진 트리 형태로 구성된 자료구조이다. 부모 노드가 자식 노드보다 크거나 작다는 규칙을 만족하며 Max Heap은 부모 노드가 자식보다 크고, Min Heap은 부모가 자식보다 작다.
힙은 배열로 구현되는 경우가 많고, 삽입이나 삭제 시에는 log n 시간 복잡도를 가진다.
주로 최댓값이나 최솟값을 빠르게 찾고 싶을 때 사용된다.
Priority Queue는 우선순위가 높은 데이터를 먼저 꺼내는 큐이다.
일반적인 큐가 FIFO 방식이라면, 우선순위 큐는 데이터의 우선순위에 따라 처리 순서가 달라진다.
Priority Queue는 내부적으로 보통 Heap을 이용해 구현된다. 그래서 둘은 개념적으로는 다르지만, 실제 구현에서는 함께 묶여서 설명되는 경우가 많다.
사용 예로는 운영체제의 프로세스 스케줄링, 네트워크 패킷 처리, 다익스트라 알고리즘에서 많이 사용된다.
</details>

<details>
<summary><b>Tree, Binary Tree, BST, AVL Tree 설명</b></summary>
Tree는 하나의 루트 노드에서 시작해서 여러 개의 자식 노드로 뻗어나가는 계층적 자료구조이다. 사이클이 없는 연결 구조이고, 보통 계층 구조 표현에 자주 사용된다. 예를 들어, 파일 시스템 구조나 조직도, XML 파서 등이 트리 구조이다. Binary Tree는 트리 구조 중에서 각 노드가 최대 두 개의 자식을 가지는 트리이다.

왼쪽 자식과 오른쪽 자식으로 나뉘며, 전체 구조는 재귀적으로 이루어진다.

BST는 이진 트리 중에서도 왼쪽 자식은 부모보다 작고, 오른쪽 자식은 부모보다 크다는 규칙을 만족하는 트리이다. 이 조건 덕분에 탐색, 삽입, 삭제 같은 연산을 평균적으로 O(log n) 시간에 할 수 있다.

단, 데이터가 정렬된 순서로 들어오면 한쪽으로 쏠린 트리가 되어 시간 복잡도가 O(n)까지 나빠질 수 있다. 이 문제를 해결하기 위해 나온 게 AVL Tree이다.

AVL 트리는 자기 균형 이진 탐색 트리(Self-Balancing BST)로, 모든 노드에 대해 왼쪽 서브트리와 오른쪽 서브트리의 높이 차이가 1 이하가 되도록 유지한다. 삽입이나 삭제가 일어난 후에도 회전을 통해 균형을 자동으로 맞춘다. 그래서 항상 최악의 경우에도 탐색, 삽입, 삭제가 O(log n) 시간에 보장된다.
</details>

<details>
<summary><b>List와 set의 차이</b></summary>
List는 순서가 있는 데이터 집합이다. 데이터가 삽입된 순서를 그대로 유지하며, 중복된 값도 허용된다.
또한 인덱스를 이용해서 특정 위치의 요소에 직접 접근할 수 있다. array와의 차이점은 array는 메모리 상에서 연속적인 데이터여야 하지만, list는 연속적인 메모리 공간일 필요는 없다.

Set은 순서가 없는 데이터 집합이다. 데이터 간의 순서 정보가 없고, 중복된 값을 허용하지 않는다.
보통 내부적으로는 해시 테이블을 기반으로 구현되며, 어떤 값이 존재하는지 빠르게 검사할 수 있다.

List는 순서를 유지하면서 여러 번 같은 값을 저장해야 하거나, 인덱스를 기반으로 접근할 일이 있을 때 사용된다. Set은 중복을 제거해야 하거나, 특정 값이 존재하는지만 빠르게 확인하고 싶을 때 적합하다.
</details>

<details>
<summary><b>BST의 최악의 경우의 예와 시간복잡도에 대해서 설명</b></summary>
데이터가 어느정도 이 된 상태로 BST에 들어오게 되면 트리의 균형이 무너지게 되면서 Time Complexity가 검색,삽입,삭제 모두 O(n)에 가깝게 된다.
</details>

<details>
<summary><b>피보나치 수열을 코드로 구현하는 방법에 대해서 설명</b></summary>
재귀, DP가 있다.
</details>

<details>
<summary><b>DFS, BFS에 대해서 설명</b></summary>
DFS는 깊이 우선 탐색이다. 그래프나 트리 구조에서 한 방향으로 계속 깊게 들어갔다가, 더 이상 갈 곳이 없으면 되돌아오는 방식으로 탐색한다.그래프나 트리 구조에서 한 방향으로 계속 깊게 들어갔다가, 더 이상 갈 곳이 없으면 되돌아오는 방식으로 탐색한다. 보통 재귀 함수나 스택을 이용해 구현되며, 특정 경로 탐색이나 백트래킹 문제에 자주 사용된다.

BFS는 너비 우선 탐색이다.  시작 노드에서 가까운 노드부터 탐색한 다음, 그 다음 거리의 노드들을 탐색해 나간다. 큐를 이용해서 구현하며, 최단 거리를 구해야 하는 문제에서 유리하다.

두 방식의 가장 큰 차이는 탐색 순서이다. DFS는 특정 경로를 끝까지 파고드는 방식이라 탐색 깊이에 따라 효율이 다르다. 반면 BFS는 한 단계씩 넓게 탐색하기 때문에 항상 가장 가까운 해답부터 찾는다.

DFS는 재귀로 구현할 경우 스택 오버플로우에 주의해야 한다. 또한 방문 체크를 하지 않으면 무한 루프에 빠질 수 있다. 

BFS는 큐를 사용하기 때문에 넓은 그래프에서는 메모리 사용량이 커질 수 있다. 특히 노드 수가 많을수록 큐의 크기가 커져서 공간 복잡도가 높아진다. 출발 점에서 같은 거리에 존재하는 블럭들은 동시에 방문한다.
</details>

<details>
<summary><b>정렬, 탐색에 대해 설명</b></summary>
탐색은 자료 구조 내에서 특정 값을 찾는 과정이다. 예를 들어, 배열이나 트리, 그래프 등에서 원하는 데이터를 찾을 때 사용된다. 대표적인 탐색 알고리즘에는 선형 탐색과 이진 탐색이 있다.

선형 탐색은 데이터를 처음부터 끝까지 하나씩 확인하면서 찾는 방식이다. 구현이 간단하지만 시간 복잡도는 O(n)이다.

이진 탐색은 정렬된 배열을 전제로 한다. 중간 값을 기준으로 절반씩 범위를 줄여가며 탐색하며, 시간 복잡도는 O(log n)이다.

정렬은 데이터를 일정한 기준에 따라 순서대로 나열하는 과정이다. 

정렬은 여러가지 종류가 있다. Insertion Sort, Bubble Sort, Quick Sort, Heap Sort 등이 있다. 다만 Insertion Sort와 Bubble Sort의 경우 시간복잡도가 O(n^2)이지만, Quick Sort와 Heap Sort는 평균적으로 O(nlogn)이 걸린다. 하지만 Heap Sort의 경우 최악의 경우 O(nlogn)이며, Quick Sort의 경우 O(n^2)이 걸리게 된다.
</details>