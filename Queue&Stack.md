> Queue (First In First Out)

```java
// Queue<Wrapper Class, 객체> 큐이름 = new LinkedList<>();
Queue<Integer> q = new LinkedList<>();

for(int i=0;i<5;i++){
	q.offer(i);
}

while(!q.isEmpty()){
	int a = q.peek();
	int b = q.poll();
	System.out.println("# size : "+q.size());
	System.out.println("peek : "+a+" / poll : "+b);
}

/* result.
# size : 4
peek : 0 / poll : 0
# size : 3
peek : 1 / poll : 1
# size : 2
peek : 2 / poll : 2
# size : 1
peek : 3 / poll : 3
# size : 0
peek : 4 / poll : 4
*/
```

**주의하자. →** Queue는 `new LinkedList<>();`의 형태로 선언해 생성해야 한다.

**Queue 메서드**

- offer() : 값 push
- poll() : 값 pop
- peek() : 가장 top의 요소를 알려준다.
- isEmpty() : Queue의 값이 없다면 true를 반환한다.
- size() : Queue의 크기를 int형으로 반환한다.
- contains() : 파라미터의 값을 포함하고 있다면 true를 반환한다.
- clear() : Queue의 모든 값을 지운다.

---

> Stack (Last In First Out)

```java
Stack<Integer> stack = new Stack<>();

for(int i=0;i<5;i++){
	stack.push(i);
}

while(!stack.isEmpty()){
	int a = stack.peek();
	int b = stack.pop();
	System.out.println("# size : "+stack.size());
	System.out.println("peek : "+a+" / remove : "+b);
}

/* result.
# size : 4
peek : 4 / remove : 4
# size : 3
peek : 3 / remove : 3
# size : 2
peek : 2 / remove : 2
# size : 1
peek : 1 / remove : 1
# size : 0
peek : 0 / remove : 0
*/
```

**Stack 메서드** (Queue의 메서드와 다른 것만 서술)

- push() : 값 push
- pop() : 값 pop
