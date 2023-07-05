> 본 내용은 `coding study with jordy`에서의 내용을 기반으로 작성했습니다.

# Array, ArrayList, Queue, Deque

## 1. Array (배열)
![array](https://velog.velcdn.com/images/tjdrb0402/post/8c5bb037-d4d5-4b9e-90d5-42e10f289ab5/image.png)

- 배열에서 `특정 인덱스`에 접근: O(1)
- 배열에서 데이터의 삽입/삭제 등 `사이즈가 달라질 때`는 배열 안의 데이터를 하나 하나 복사해서 새로 만들어야하기 때문에 O(N)의 시간 복잡도를 가집니다.
    - 단, List, ArrayList에서 `가장 끝에 데이터를 삽입하는 것은 약 O(1)`의 시간 복잡도를 가집니다.
- 배열에서 데이터 검색(탐색): 배열 안에 `특정 데이터가 있는지` 알기 위해서는 모든 데이터를 확인해야하기 때문에 O(N)의 시 복잡도를 가집니다.

## 2. ArrayList
![arraylist](https://velog.velcdn.com/images/tjdrb0402/post/41e43f24-f409-4fb3-a598-b6b3dc2f2df8/image.png)

- Array, ArrayList는 어떤 데이터를 지우거나 삽입하는 등의 사이즈가 달라지는 연산에는 사용하기 좋지 않을 것입니다.

### 배열과 ArrayList의 차이
```java
public class Test {

		private static final int MAX = 1_000_000;

		public static void main(String[] args) {

				long s = System.currentTimeMillis();

				int a = 0;

				int[] arr = new int[MAX];
				for (int i = 0; i < MAX; i++) {
						a += arr[MAX - 1];
				}
				
				long e = System.currentTimeMillis();

				System.out.println((e - s) / 1000.0);


				// ArrayList
				s = System.currentTimeMillis();

				ArrayList<Integer> list = new ArrayList<>();

				int b = 0;
				for (int i = 0; i < MAX; i++) {
						list.add(i);
				}
		}
}

```
- ArrayList는 처음에 사이즈가 16인 ArrayList를 만들고 가득 찼을 때 데이터를 추가하면 길이를 2배로 늘리는 작업을 하기 때문에 배열보다 조금 더 느립니다. (Array와 ArrayList 모두 데이터를 복사해서 만들지만 2배로 늘리는 작업으로 시간적 loss가 생깁니다.)
- 배열에 들어갈 개수가 정해져있다면 List(ArrayList)보다 배열을 사용하는 것이 더 좋을 것입니다.


## 3. Queue
![queue](https://velog.velcdn.com/images/tjdrb0402/post/7c61236d-5b0b-43a6-8473-6f68160ee6bf/image.png)
- FIFO
- 끝에 데이터를 삽입/삭제에 매우 유리합니다. (시간 복잡도: O(1))


## 4. Deque (Double Ended Queue)

![deque](https://velog.velcdn.com/images/tjdrb0402/post/cb5f1fdd-a17d-4d74-89b5-f1b30f7efff1/image.png)

- Deque, ArrayDeque을 사용하면서
    - addLast(), pollFirst()만 사용하면 Queue처럼,
    - addLast(), pollLast()만 사용하면 Stack처럼 사용할 수 있습니다.

### LinkedList와 ArrayDeque의 차이
- 메모리 관점에서 보면 LinkedList는 노드마다 포인터를 갖고 있다보니 거의 2배의 메모리를 차지하게 됩니다.






