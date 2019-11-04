## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

answer:
```swift
func capitialized (input: String) -> String {
    return input.uppercased()
    
}
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

answer:
```swift
func capitializedAlternating (input: String) -> String {
    
    var newCaptializedAlternating = String()
    
    for (index, char) in input.enumerated() {
        if index % 2 == 1 {
            newCaptializedAlternating += char.uppercased()
        } else {
            newCaptializedAlternating += char.lowercased()
        }
    }
    return newCaptializedAlternating
}
```

3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

answer:
```swift
func givenAString(input: String, char: Character) -> String {
    let removedChar = input.filter {$0 != char} // input is a constant
    return removedChar
}
```

## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

answer:
```swift
func largestInt (array: [Int]) -> Int {
    
    var int = array[0]
    
    for num in array {
        if num > int {
            int = num
        }
    }
    return int
}
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

answer:
```swift
func smallestInt (array: [Int]) -> Int {
    
    var int = array[0]
    
    for num in array {
        if num < int {
            int = num
        }
    }
    return int
}
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

answer:
```swift
func sum(array: [Int]) -> Int {
    return array.reduce(0, +)
}
```

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

answer:
```swift
func averageOfDouble(array: [Double]) -> Double {
    
    var sum = 0.0
    for num in array {
        sum += num
    }
    return sum / Double(array.count)
}
```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

answer:
```swift
func someFunc(array: [Double], double: Double) -> Double {
    
    var sum = 0.0
    
    for num in array {
        if num > double {
            sum += num
        }
    }
    return sum
}
```


6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

answer:
```swift
func productOfAll(array: [Double]) -> Double {
    
    var total = 1.0
    
    for num in array {
        total *= num
    }
    return total
}
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

answer:
```swift
func secondSmallestValue(array: [Int]) -> Int {
    array.sorted()[1]
}
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

answer:
```swift
func whatIfs(array: [String?]) -> [String]{
    return array.compactMap{$0}
}
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

answer:
```swift
func whatIfs2(array: [String?]?) -> [String] { 
    
    var newArray: [String] = []
    if let unwrappedString = array {
        newArray = unwrappedString.compactMap{$0}
    }
    return newArray
}
```

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

answer:
```swift
func whatIfs3(array: [Int?]) -> Int {
    var sum = 0
    for num in array {
        guard let aNumber = num else {
            continue
        }
        sum += aNumber
    }
    return sum
}
```

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

answer:
```swift
func aFunction(array: [Int?]?) -> Int {
    
    var sum = 0
    
    guard array != nil else {
        return sum += (array?.compactMap{$0 != nil})!
    }
    return sum
}
// error: Cannot convert value of type '[Bool]' to expected argument type 'Int'
```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`

answer:
```swift
func whatIfs4(array: [Int?], int: Int?) -> Int {
    
    var sum = 0
    
    for num in array {
        if let unwrappedNum = num {
            if unwrappedNum != int {
                sum += unwrappedNum
            }
        }
    }
    return sum
}
```


## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

answer:
```swift
func dictionary1(array: [String]) -> [String] {
    return Array(Set(array)).sorted()
}
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

answer:
```swift
func frequentLetter(aString: String) -> Character {
    var finalDictionary = [Character: Int]()
    for char in myString {
        if let value = finalDictionary[char] {
            finalDictionary[char] = value + 1 
        } else {
            finalDictionary[char] = 1 
        }
    }
    
    var mostFrequentChar = ""
    var mostTimes = 0
    
    for (key, value) in finalDictionary { 
        if value > mostTimes {
            mostFrequentChar = key.description 
            mostTimes = value
        }
    }
    return Character(mostFrequentChar)
}
```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

answer:
```swift
func containsTwice(array: [Int]) -> [Int] {
    
    var emptyDictionary = [Int:Int]()
    var elementsThatAppearAtLeastTwice = [Int]()
    
    for key in array {
        if let value = emptyDictionary[key] { // if this is not a nil
            emptyDictionary[key] = value + 1  // how to break once it has a duplicate
        } else {
            emptyDictionary[key] = 1
        }
    }
    for (key, value) in emptyDictionary {
        if value >= 2 {
            elementsThatAppearAtLeastTwice.append(key)
        }
    }
    return elementsThatAppearAtLeastTwice
}
```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`

answer:
```swift
func function0(string: String) -> Character {

    var emptyDictionary = [Character:Int]()
    
    let joinedString = string.replacingOccurrences(of: " ", with: "")
    for char in joinedString {
        if let value = emptyDictionary[char] {
            emptyDictionary[char] = value + 1
        } else {
            emptyDictionary[char] = 1
        }
    }
    
    var mostFrequentChar = ""
    var mostTimes = 0
    
    for (key, value) in emptyDictionary {
        if value > mostTimes {
            mostFrequentChar = key.description
            mostTimes = value
        }
    }
    return Character(mostFrequentChar)
}
```

## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

answer:
```swift
func function1(array: [String]) -> [String] {
    return array.sorted{ $0 < $1 }
}
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

answer:
```swift
func function2(array:[String]) -> [String] {
    return array.sorted(by: {$0.count < $1.count})
}
```

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

answer:
```swift
func function3(array: [String]) -> [String] {
   
    var newFunction3 = [String]()
    for num in array {
        if num.count > 4 {
            newFunction3.append(num)
        }
    }
    return newFunction3
}

// OR 

func function4(array: [String]) -> [String] {
    return array.filter{$0.count > 4}
}
```

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`

answer:
```swift
func function5(array: [String]) -> String {
    var newArray = String()
    for element in array {
        newArray += element + " "
    }
    newArray.removeLast()
    return newArray
}

// OR 

func function6(array: [String]) -> String {
   var newArray1 = String()
    array.forEach{element in newArray1.append(element + " ") }
    return newArray1
}
```


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
func function7(array: [Int], instance: NumberType) -> [Int] {
    
    var oddArray = [Int]()
    var evenArray = [Int]()
    
    for num in array {
        if num % 2 == 1 {
            oddArray.append(num)
        } else {
            evenArray.append(num)
        }
    }
    
    if instance == NumberType.odd {
        return oddArray
    } else {
        return evenArray
    }
}

// OR

func function8(array: [Int], instance: NumberType) -> [Int] {
    switch instance {
    case .even:
        return array.filter({$0 % 2 == 0 })
    case .odd:
        return array.filter({$0 % 2 == 1 })
    }
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
func function9(string: String, instance: StringType) -> String {
    
    switch instance {
    case .lowercase:
        return string.lowercased()
    case .uppercase:
        return string.uppercased()
    }
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`

answer:
```swift
func function10(array:[FileStatus], num: Int) -> [FileStatus] {
    var newArray2 = [FileStatus]()
    
    for element in array {
        switch element {
        case .saved(let numOfVersions):
            if numOfVersions > num {
                newArray2.append(element)
            }
        case .unsaved:
            continue
        }
    }
    return newArray2
}
```
