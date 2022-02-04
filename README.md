# Coding-Test 생각 도구

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
A
Nil
Nil
Nil
Nil
```

Dictionary에서 Key 와 Value 둘 중 하나만 없어도 Nil값으로 처리된다. 그래서 for문에서 Character별로 돌아갈때 유일하게 A값만 정상적으로 출력된다.


