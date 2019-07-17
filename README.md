## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

var hello = "Hello there"
print(hello.uppercased())

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

var hello = "Hello there"
var newString = String()
for (key,value) in hello.enumerated() {
if key % 2 == 0 {
newString.append(value.uppercased())
} else {
newString.append(value)
}
}
print(newString)

3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

var str = "Hello, there"
var emptyStr = String()
for i in str {
if i != "e" {
emptyStr.append(i)
}
}
print(emptyStr)

## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

var arrayNum = [1,5,2,4,1,4]
var max = 0
for num in arrayNum {
if max < num {
max = num
}
}
print(max)


2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

var arrayNum = [1,5,2,4,1,4]
var min = 9000 
for num in arrayNum {
if min > num {
min = num
}
}
print(min)

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

var arrayNum = [1,5,2,4,1,4]
var sum = 0
for num in arrayNum {
sum += num
}

print(sum)


4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

var arrayNum = [3,4.5,7.5,2,1]
var sum: Double = 0
for num in arrayNum {
sum += num


}
sum = sum / Double(arrayNum.count)
print(sum)

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

var arrayNum = [3,4.5,7.5,2,1]
var emptyArray = [Double]()
var arrayNum2: Double = 3
var sum: Double = 0
for num in arrayNum {
if num > arrayNum2 {
sum += num
}


}

print(sum)

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

var arrayNum = [3,4.5,7.5,2,1]
var product = Double(1)
for num in arrayNum {
product *= num
}
print(product)


7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

var arrayNum = [3,6,1,9,4,8]
var smallestNum = arrayNum.sorted()[1]
print(smallestNum)


## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

var stringArray = [nil, "We", "come", nil, "in", "peace"]
var emptyArray = [String]()
for word in stringArray where word != nil {
emptyArray.append(word!)
}
print(emptyArray)


2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

var stringArray: [String?] = [nil]
var emptyArray = [String]()
for word in stringArray where word != nil {
emptyArray.append(word!)
}
print(emptyArray)

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`
```swift
var integers: [Int?] = [4, nil, 9, 5, nil]
var emptyArr = [Int]()
for numbers in integers{
guard numbers != nil else { // if our condition is false it will do whatever is in else

continue
}
emptyArr.append(numbers!)
}

print(emptyArr.reduce(0, +))
```

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`
```swift
var integers: [Int?] = [nil]
var emptyArr = [Int]()
for numbers in integers{
guard numbers != nil else { // if our condition is false it will do whatever is in else

continue
}
emptyArr.append(numbers!)
}

print(emptyArr.reduce(0, +))
```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`
```swift
var nums: [Int?] = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var integer: Int? = 1
var emptyArr = [Int]()

for numbers in nums where numbers != nil && numbers != integer{

emptyArr.append(numbers!)
guard numbers != nil else { // if our condition is false it will do whatever is in else

break
}
}

print(emptyArr.reduce(0, +))
```


## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`
```swift
var fruits = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]

print(Set(fruits).sorted())
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`
```swift
var message = "Never trust a computer you can't throw out a window ~ Steve Wozniak"

var list = [Character:Int]()
var count = 0
var alphabet = "abcdefghijklmnopqrstuvwxyz"

for letter in alphabet{
for char in message{
if char == letter{
count += 1
list.updateValue(count, forKey: char)
}
}
count = 0
}

var max = 0
var mostOcurringLetter = String()

for (key,value) in list{
if value > max {
max = value
mostOcurringLetter = String(key)
}
}
print(mostOcurringLetter)
```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`
```swift
var numbers = [1,1,2,3,3,3,4,5,6,6,7]

var list = [Int:Int]()
var count = 0
var digits = Set(numbers)

for nums in digits{
for items in numbers{
if nums == items{
count += 1
list.updateValue(count, forKey: nums)
}
}
count = 0
}
//print(list)

var newArr = [Int]()

for (key,value) in list{
if value >= 2 {
newArr.append(key)
}
}
print(newArr.sorted())
```


4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`
```swift
var message = "Never trust a computer you can't throw out a window ~ Steve Wozniak"

var list = [Character:Int]()
var count = 0
var alphabet = "abcdefghijklmnopqrstuvwxyz"

for letter in alphabet{
for char in message{
if char == letter{
count += 1
list.updateValue(count, forKey: char)
}
}
count = 0
}

var max = 0
var mostOcurringLetter = String()
var secondLetter = String()
var secondBigNum = 0

for (key,value) in list{

if value > max {
secondLetter = mostOcurringLetter
secondBigNum = max
max = value
mostOcurringLetter = String(key)
}
}
print("Letter that occurs second most:\(secondLetter) this many times:\(secondBigNum)")
```


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

```swift
var arrOfStr = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(arrOfStr.sorted(by: < ))
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`
```swift
var arrOfStr = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(arrOfStr.sorted(by: {(x,y) in
x.count < y.count
} ))
```
3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`
```swift
var arrOfStr = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(arrOfStr.filter{$0.count > 4})
```
4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`

```swift
var arrOfStr = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
var emptyString = String()


for i in arrOfStr{
emptyString.append(i + " ")
}

print(emptyString)
```

## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
case even
case odd
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`
```swift
enum NumberType {
case even
case odd

func evenOrOdd(num: [Int])-> [Int]{
var oddOrEven = [Int]()
var odd = [Int]()
switch self {
case .even:
oddOrEven = num.filter{$0 % 2 == 0}

case .odd:
oddOrEven = num.filter{$0 % 2 != 0}

}
return oddOrEven
}
}
var numbers = [1,2,3,4,5,6]
```

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
case lowercase
case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``
```swift
enum StringType {
case lowercase
case uppercase

func changeCase(a: String)->String{
var emptyString = String()
switch self {
case .lowercase:
emptyString = a.lowercased()
case .uppercase:
emptyString = a.uppercased()
}
return emptyString
}
}

var message = "Design is not just what it looks like and feels like. Design is how it works"

let upper = StringType.uppercase
let lower = StringType.lowercase
print(upper.changeCase(a: message))
print(lower.changeCase(a: message))
```

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
