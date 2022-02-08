# Coding-Test 생각 도구

코딩 테스트를 풀 때 필요한 요소 5가지.

1. 독해력 - 문제를 정확히 읽어낼 수 있는 능력

2. 배경지식 - 자료구조 & 알고리즘 이론

3. 문제해결력 - 문제 해결 과정을 정립하는 능력. 어떤 자료구조 & 알고리즘인지 생각하고 그에 맞는 정확한 로직을 짜는 능력이다. 문제 풀 때 문제를 먼저 간단하게 정리해보고 그 풀이 과정은 순서도를 그려보면서 하자. 아무리 생각해도 모르겠다면 귀납적으로라도 접근 할 수 있는 능력을 말한다.

4. 구현력 - 문제 해결 과정을 코드화 시키는 능력. 번역이라고 생각하면 된다. 구현할때 가장 먼저 큰 틀부터 코딩하고 그 후에 세부적인 것에 집중하자. DFS식 접근.

5. 디버깅 능력 - 답 제출 후 오류가 나왔을 때 대처하는 능력.
***

**백준 2577번** - String을 for문에 넣으면  Character로 한문자씩 loop constant에 들어가지게 된다. 베열의 인덱스에 접근할때 Character로는 접근 x, 접근할 시 String으로 먼저 변환하고 그 다음에 Int로 변환 시켜야 한다.

```swift 
var a: Character = "0"
var result = [1, 2, 3]

print(result[Int(String(a))!])
```

***

**백준 1065** - 각 자리 숫자들을 표현하는 방법: 
* 100의 자리 - num / 100
* 10의 자리 - (num % 100) / 10
* 1의 자리 - num % 10

***

**백준 1157** - Dictionary의 구조에 대해서 헷갈려 고생했던 문제다. 

```swift
let word = "Apple"
var dict: [String: Int] = ["A": 3]

for i in word {
    if dict[String(i)] == 3 {
        print("A")
    } else {
        print("Nil")
    }
}

결과값
A
Nil
Nil
Nil
Nil
```

Dictionary에서 Key 와 Value 둘 중 하나만 없어도 Nil값으로 처리된다. 그래서 for문에서 Character별로 돌아갈때 유일하게 첫번째 index값만 정상적으로 출력된다.


