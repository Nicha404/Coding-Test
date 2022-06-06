# Coding-Test 생각 도구
  
코딩 테스트를 풀 때 필요한 요소 6가지  
 
1. 독해력 - 문제를 정확히 읽어낼 수 있는 능력  
     
2. 배경지식 - 자료구조 & 알고리즘 이론 
 
3. 문제해결력 - 문제 해결 과정을 정립하는 능력을 말한다. 어떤 자료구조 & 알고리즘인지 생각하고 그에 맞는 정확한 로직을 짜는 능력이다. 문제 풀 때 문제를 읽고 먼저 간단하게 요약하고 유형을 파악한 뒤 풀이 과정을 단계별로 적어보자(+ 해결 방안 세분화 시키기). 아무리 생각해도 모르겠다면 귀납적으로라도 접근 할 수 있는 능력을 말한다. 처음에는 크게 크게 BFS식으로 접근하자. 
 
4. 구현력 - 문제 해결 과정을 코드화 시키는 능력. 번역이라고 생각하면 된다. 풀이 과정을 단계별로 구현하기만 하면 된다. 구현할때 가장 먼저 큰 틀부터 코딩하고 그 후에 세부적인 것에 집중하자. 3번과 마찬가지로 BFS식 접근.
 
5. 디버깅 능력 - 답 제출 후 오류가 나왔을 때 대처하는 능력. 

6. 꼼꼼함 - 문제든 코드든 한 줄 한 줄 꼼꼼하게 짚고 넘어가기, 코드 흘려 읽지 않기, .하나만 실수해도 틀리는게 코딩이다.

코테는 딱 세 가지다. 문제파악 -> 단계별 풀이 과정 정립 -> 번역. 문제 풀 때 공책에 1 - 1 문제요약, 1 - 2 유형 파악, 2 단풀, 3 번역  

시간복잡도 계산은 1억번당 1초로 주어진 n개를 잘 보며 잘 계산한다. (https://lemonlemon.tistory.com/54)

***  

**백준 2577번**    

String을 for문에 넣으면  Character로 한문자씩 loop constant에 들어가지게 된다. 베열의 인덱스에 접근할때 Character로는 접근 x, 접근할 시 String으로 먼저 변환하고 그 다음에 Int로 변환 시켜야 한다.

```swift 
var a: Character = "0"
var result = [1, 2, 3]

print(result[Int(String(a))!]) // 1
```   

***

**백준 1065** 
 
세자리 숫자에서 각 자리수 표현하는 방법: 
* 100의 자리 - num / 100
* 10의 자리 - (num % 100) / 10
* 1의 자리 - num % 10

***

**백준 1157** 

Dictionary의 구조에 대해서 헷갈려 고생했던 문제다. 
   
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

***

**백준 1712** 

시간초과가 나서 헤맨 문제이다. 변수 선언을 없애고 고차함수를 사용하였더니 해결되었다.

***

**백준 1427번**

```swift
let n = readLine()!
var arr: [Int] = []

for i in n {
    arr.append(Int(String(i))!)
}
```

Character를 Int로 형변환하려면 String을 거쳐야 한다!

또한 형변환 시 Int랑 Double만 옵셔널로 묶는다. Character랑 String은 옵셔널로 안 묶음. 그러나 Int와 Double을 서로 묶을 때는 옵셔널 사용 안함.
 
```swift
var a = "a"
var b = Int(a)
print(type(of: b))
//Optional<Int>
```

***

**백준 10871**

1.

```swift
for i in [1, 2, 3] {

}
```

for문에서 배열을 범위로 쓸 수 있다.

2.

components separatedBy를 쓰면 배열로 반환된다.

***

**백준 2480**

```swift
if a[0] == a[1] && a[0] == a[2] && a[1] == a[2] {

}
```

&&연산자 ||연산자 연속으로 사용가능

***

**백준 2562**

```swift

var students = ["Ben", "Ben", "Ben", "Ben", "Ben", "Ben"]

print(students.firstIndex(of: "Ben")!) // 0
print(students.lastIndex(of: "Ben")!) // 5
```

firstIndex & lastIndex - 처음 나타난 값과 마지막으로 나타나는 값의 인덱스를 출력함.

***

**백준 11720**

```swift

let a = readLine()! // 323, asd
let b = a.map { $0 }

print(b) // ["3", "2", "3"], ["a", "s", "d"]
```
readLine을 map시키면 배열 안에 Character로 출력된다.

***

**백준 9093**

```swift
let str = readLine()!.components(separatedBy: " ")
str.forEach {
    print($0)
}
//d ddd dd
//d
//ddd
//dd
```

띄어쓰기를 기준으로 한 덩어리로 간주한다. 타입은 Substring

[forEach 설명 링크](https://babbab2.tistory.com/95)

***

**백준 1158**

```swift
var queue = [1, 2, 3]
let value = queue.remove(at: 2)

print(value) // 3(remove하면 remove한 값을 반환)
print(queue) // [1, 2]
```

***

**백준 2439**

배열 아니어도 그냥 변수에 append 쓸 수 있음.

```swift
var a = "a"
a.append("a")
print(a)
// "aa"
```





 




 

 
