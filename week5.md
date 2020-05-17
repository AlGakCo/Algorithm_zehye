```swift 
var array1 = [Int]()
var array2 = [Int]()

func solution(_ array:[Int], _ commands:[[Int]]) -> [Int] {
    for n in 0...commands.count-1{
        let i = commands[n][0]
        let j = commands[n][1]
        for number in i-1...j-1{
            array1.append(array[number])
        }
        array1.sort(by: <)
        array2.append(array1[k-1])
        array1.removeAll()
        
    }
    
    return array2
}
```

월요일에 깔끔히 정리해서 올리겠습니당.. 일단 코드만 
