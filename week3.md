## 해시: 위장

[42578](https://programmers.co.kr/learn/courses/30/lessons/42578)

```swift 
import Foundation

func solution(_ clothes:[[String]]) -> Int {
    var dic:[String:Int] = [:]
    clothes.forEach { (element) in
        if dic.keys.contains(element[1]) {
            dic[element[1]]! += 1
        } else {
            dic[element[1]] = 1
        }
    }

    var answer = 1
    for v in dic {
        answer *= v.value+1
    }
    return answer-1
}
```
