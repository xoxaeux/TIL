# Algorithm - Union Find

###### "UnionFind는 서로소 집합을 찾는 방법이다."



##### "Solution : 집합의 부모(parent)를 찾아 부모의 link를 다른 집합의 부모로 변경시켜주자."

1. 가장 처음 집합은 자기 자신을 부모로 설정한다.

   ``` java
   //	int[] numArray	:	{0} {1} {2} {3} {4} {5} {6} {7} {8} {9}
   //	int[] parents	:	 0   1   2   3   4   5   6   7   8   9
   
   for(int i=0; i<=9; i++){
       parents[i]=i;
   }
   ```



2. 부모를 찾는다.

   ```java
   /*	
   	예를 들어, 두 예시를 통해 살펴보자..
   	8이 속한 집합과 3이 속한 집합을 합친다.
   	이후 1이 속한 집합과 3이 속한 집합을 합친다.
   */
   
   //항상 작은 수를 a, 큰 수를 b로 설정한다.
   if(a < b){
       int temp = a;
       a = b;
       b = temp;
   }
   
   int fa = find(a);
   int fb = find(b);
   
   private static int find(int i){
       if(parents[i]==i) { //타고 올라가서 인덱스와 parents가 동일하다면,
           return i;
       }
       return find(parents[i]); //parents가 다른 인덱스를 가리킨다면, 타고 올라가자.
   }
   ```

   

3. 부모가 다를 경우엔 두 집합을 합친다.

   ```java
   // 여기서 부모에 통일성을 두기 위해,
   // 더 큰 인덱스의 부모의 링크를 변경해주도록 설정하였다.
   
   // private static void union(int fa, int fb){}
   if(fa>fb){
       parents[fa]=fb;
   }else if(fa<fb){
       parents[fb]=fa;
   }
   ```



4. 이후, find 함수를 통해 두 원소가 같은 부모에 속해 있는지 확인함으로,

   서로소 관계에 있는지 판별할 수 있다.

   ```java
   // (a,b) = (8,3), (1,3)
   //	int[] numArray	:	{0} {1} {2} {3} {4} {5} {6} {7} {8} {9}
   //	int[] parents	:	 0   1   2   1   4   5   6   7   3   9
   
   if(find(1) == find(8)){
       System.out.println("서로소 관계가 아닙니다.")
   }
   ```

   

*cf. SWEA_3289 / JUNGOL_1863*	
