# jQuery

##### 크로스 플랫폼을 지원하는 경량 Javascript library.

###### js로 길게 표현했던 것들을 jQuery를 이용해 보다 간략하게 표현할 수 있다.



## 기본구문

```js
// $(selector).action();
$(document).ready(function(){
    //TODO ~
})

//위와 같은 표현.
$(function(){
    //TODO ~
})
```

----



- #### jQuery(function | selector | htmlTag | DOM객체)

  - $( ) : jQuery 함수의 축약형

  - 함수에 전달한 인자를 이용해서 jQuery객체를 생성해서 리턴

  - 인자

    **1. function**

       - window.onload = function(){} 와 같은 의미의 초기화 함수

         ```js
         // 아래는 모두 같은 의미
         jQuery().ready(function(){})
         jQuery (function(){ })
         $(function(){ })
         ```
         
         

    **2. selector**

       - selector에 해당하는 Tag를 찾아 jQuery객체를 생성해서 리턴

       - 사용방법
    
         ```js
         $(selector) // html 전체에서 selector에 해당하는 tag를 찾기
         $(selector, content) // content 내에서 selector에 해당하는 tag를 찾기
         // ex) $('div') : div태그를 찾는 selector
         ```
     
         

    **3. htmlTag**

       - 태그를 생성한 후 생성된 태그를 이용해서 jQuery객체를 생성해서 리턴
    
         ```js
         document.createElement('tag')
         // ex) $('<div/>') : div 태그를 생성
         ```
         
         
    
    **4. DOM객체**
    
       - DOM객체를 jQuery 객체로 변경
    
         ```js
         var id = document.getElementById('id');
               $(id)
         
               $('#btn').click(function(){
                    //this는 event가 발생된 DOM객체
                $(this) 
               })
         ```

