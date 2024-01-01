### Stack / Queue
---
### 📚 Stack
---
![image](https://github.com/leesoyuun/CS-Study/assets/51051548/9b12f0c2-906a-4656-a705-ebd8d6463910)

> 쌓여있는 책을 예시로 들 수있다.
> 책을 쌓기 위해서 아래부터 순서대로 쌓아야한다. 책을 찾고자하는 사용자는 위에서부터 하나씩 책 표지를 확인하며 찾아야한다.
>
> 다른 예시 : 프x글스

### 특징
---
#### 후입선출 (LIFO - Last In First Out) 구조
`Stack`이란 데이터를 쌓아올린 형태의 자료구조이다.<br>
데이터를 한 방향으로만 저장을 할 수 있고, 맨 위에있는 `Top` 데이터만 삽입 / 삭제 / 조회 가 가능하다.

### 시간복잡도
--- 
- 삽입 자료를 추가하기 위해서는 맨위에 한번 push하면 끝 -> **O(1)**
- 삭제 : 맨 위 자료만 삭제하면된다 -> **O(1)**
- 검색 : 총 10개의 자료 중 맨 위의 자료를 찾는다 하면 바로 데이터를 찾을 수 있지만, 맨아래에 있는경우 모든 경우를 고려해야하므로 -> **O(n)**
  
### 주요 메서드 ( JavaScript 기준 )
---
1. `push()`<br>
    - 스택에 새로운 원소를 삽입한다.
2. `pop()`
    - 최상층에 위치한 데이터를 읽어오고, 해당 데이터를 스택에서 제거한다.

### JavaScript의 Stack 구현
> JavaScript는 다른 언어와 다르게 기본 메서드들이 적은 편이다 :(
Stack 생성을 위한 Class 정의
```
class Stack{
  // constructor 생성
  constructor() {
    this.storage = {};
    this.size = 0;
  }

  //stack에 element추가
  push(element){
    this.size++;
    this.storage[this.size] = element;
  }

  //stack에서 element제거한 후 해당 element 반환
  pop() {
    if(this.size <= 0 ) { 
      return; // size가 0이하면 아무일도 일어나지않음
    }
    let removed = this.storage[this.size];
    delete this.storage[this.size];
    this.size--;
    return removed;
  }

  // 맨위의 값 가지고 오기
  top() {
    return this.storage[this.size];
  }
}

const stack = new Stack();
stack.push("Hello");
stack.push("GitHub");

console.log(stack.pop()); // GitHub
console.log(stack.pop()); // Hello

```

**JavaScript에서 스택은 해당 코드를 사용해도 좋지만 배열의 push와 Pop 메서드를 사용하여 활용이 가능합니다.**



