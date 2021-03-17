# Java List 정리

###### "자바에서 List로 구현된 클래스는 ArrayList, LinkedList, Stack, Vector가 있다."

- [x] **ArrayList** : 빠르다. 배열을 이용해 요소를 저장한다.

- [x] **LinkedList** : Doubly-linked list. 연결 리스트를 이용해 요소를 저장한다.

- [x] **Stack** : LIFO. Vector를 상속받아 스택 메모리 구조의 클래스를 제공한다.

- [ ] Vector : 현재는 사용되지 않음.

  

> **Array vs. ArrayList**
>
> > Array는 길이 고정. ArrayList는 동적으로 길이 변경 가능
> >
> > ArrayList는 보다 다양한 기능 제공 (addAll, removeAll, iterator ... )



> **ArrayList vs. LinkedList**
>
> > Queue를 구현할 때는 LinkedList 사용
> >
> > 검색은 ArrayList가 유리하다.
> >
> > 추가/삭제는 LinkedList가 유리하다.
> >
> > LinkedList는 보다 많은 메모리를 소비한다.





1. List 선언 및 초기화

   ```java
   ArrayList<String> aList = new ArrayList<>();
   ```



2. ArrayList 메소드

   ```java
   ArrayList<Integer> aList = new ArrayList<Integer>();
   aList.add(4);
   aList.add(null); //null값 add가능
   aList.add(1,8); //index 1 뒤에 8 삽입
   aList.remove(1); //index 1 삭제
   aList.clear(); //모든 값 삭제
   ```

   

3. LinkedList 메소드

   ```java
   LinkedList<Integer> lList = new LinkedList<Integer>();
   //나머지는 ArrayList 메소드와 동일하게 사용한다.
   ```

   

----



​	cf. Iterator 사용 방법

```java
Iterator<Integer> iter = aList.iterator();
while(iter.hasNext()){
	System.out.println(iter.next());
}
```



​	cf. Generics : < >

​	제네릭스는 객체 타입으로만 선언한다. 

​	int는 기본자료형이기 때문에 들어갈수 없기에

​	int를 객체화시킨 Wrapper클래스(Integer)를 사용해야 한다.