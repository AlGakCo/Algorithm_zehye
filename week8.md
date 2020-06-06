```swift 
func solution2(_ n:Int) -> Int {
    var total = 0
    Loop :for i in 2...n {
        for j in 2...i{
            if i%j == 0 && j != i{
               continue Loop
            }
            }
        total += 1
        }
    return total
}
```
