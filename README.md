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


