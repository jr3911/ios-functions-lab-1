# Functions lab 1

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

Complete the function so that it will print out total cost after tax. Make sure to **call the function** afterwards.

```swift
let itemCost = 45.0
let nyTax = 0.08775

func totalWithTax() -> Int {
    let totalCost = Int(itemCost + nyTax)
    return totalCost
}

print("Total cost of the item after tax: $\(totalWithTax())")

```

Then, modify the function you implemented to have a return type of `Int`, and use an external name that looks more readable. Function calls should look something like "total cost of the item after tax"

## Question 2

Convert the the following if/else statement below into function with a `String` return type.

```swift
let todaysTemperature = 72

func responseToWeather() -> String {
    if todaysTemperature <= 40 {
    return ("It's cold out.")
    } else if todaysTemperature >= 85 {
    return ("It's really warm.")
    } else {
    return ("Weather is moderate.")
    }
}

print(responseToWeather())
```


## Question 3

Write a function named `min2` that takes two `Int` values, `a` and `b`, and returns the smallest one.

Function Definition
`func min2(a: Int, b: Int) -> Int`

Example:
Input: `min2(a:1, b:2)`

Output: `1`

```swift
func min2(a: Int, b: Int) -> Int {
    if a <= b {
        return a
    } else {
        return b
    }
}
```


## Question 4

Write a function that takes an `Int` and returns its last digit. Name the function `lastDigit`. Use _ to ignore the external parameter name.

Function Definition:
`func lastDigit(_ number: Int) -> Int`

Example:
Input: `lastDigit(12345)`

Output: `5`

```swift
func lastDigit(_ number: Int) -> Int {
    var numString = String(number)
    var lastDigit = Int(String(numString.last!))!
    return lastDigit
}
```

## Question 5

Write a function that takes in any two positive integers and return the sum.

```swift
func addTwoInts(number x: Int, number y: Int) -> Int {
    let sum = x + y
    return sum
}
```


## Question 6

Write a function takes in any number grade and returns a corresponding letter grade.

| Number Grade | Equivalent Letter Grade |
| :--------: | :---------: |
| 100 | A+ |
| 90 - 99 | A |
| 80 - 89 | B |
| 70 - 79 | C |
| 65 - 69 | D |
| Below 65 | F |

```swift

func gradeEquivalence(numberGrade: Int) -> String {
    switch numberGrade {
    case 100:
        return "A+"
    case 90...99:
        return "A"
    case 80...89:
        return "B"
    case 70...79:
        return "C"
    case 65...69:
        return "D"
    case 0...64:
        return "F"
    default:
        return "Not a valid grade"
    }
}
```
## Question 7

Make a calculator function that takes in three parameters (two numbers and one operator) and returns the answer of the operation.

Operator parameter: (+, -, x, /)

```swift
func calculator(num1: Double, num2: Double, sign: Character) -> Double {
    switch sign {
    case "+":
        let sum = num1 + num2
        return sum
    case "-":
        let difference = num1 - num2
        return difference
    case "x":
        let product = num1 * num2
        return product
    case "/":
        let dividend = num1 / num2
        return dividend
    default:
        return 0
    }
}

print(calculator(num1: 5, num2: 2, sign: "/"))
```

## Question 8

Write a function so that it will print out **total cost after tip.**

```swift
let mealCost = 45
let tipPercentage = 0.15

func totalWithTip() {
    let totalCost = Double(mealCost) + (Double(mealCost) * tipPercentage)
    let message = ("Total cost after tip: $\(totalCost)")
    print(message)
}

let myFinalCost = totalWithTip()
```

Write a function that will print out **total cost after tip and tax.**

```swift
let taxPercentage = 0.09
let mealCost = 45
let tipPercentage = 0.15

func totalWithTipAndTax() {
    let costWithTax = Double(mealCost) + (Double(mealCost) * taxPercentage)
    let totalCost = Double(mealCost) + (costWithTax * tipPercentage)
    let formattedTotalCost = String(format: "%.2f", totalCost)
    let message = ("Total cost after tip: $\(formattedTotalCost)")
    print(message)
}

let myFinalCostWithTipAndTax = totalWithTipAndTax()

```


## Question 9

Implement a function named `repeatPrint` that takes a string `message` and a integer `count` as parameters. The function should print `message` `count` number of times and then print a newline.

Example:
Input: `repeatPrint(message: "+", count: 10)`

Output: `++++++++++`

```swift
func repeatPrint(message: String, count: Int) {
    var text = String(repeating: "\(message)", count: count)
    print("\(text)\n")
}
```


## Question 10

Write a function named `first` that takes an Int named n and returns an array with the first n numbers starting from 1.

Function Definition
`func first(_ n: Int) -> [Int]`

Example:
Input: `first(3)`

Output: `[1, 2, 3]`

```swift
func first(_ n: Int) -> [Int] {
    var numArray = [Int]()
    for i in 1...n {
        numArray.append(i)
    }
    return numArray
}
```

## Question 11

Write a function that prints the numbers from 1 to x, except:

If the number if a multiple of 3, print `"Fizz"` instead of the number
If the number is a multiple of 5, print `"Buzz"` instead of the number
If the number is a multiple of 3 AND 5, print `"FizzBuzz"` instead of the number
Your function should take in one parameter: x (the number to count up to)

```swift
func writeSomething(x: Int) {
    for i in 1...x {
        if i % 3 == 0 && i % 5 == 0{
            print("FizzBuzz")
        } else if i % 3 == 0 {
            print("Fizz")
        } else if i % 5 == 0 {
            print("Buzz")
        } else {
            print(i)
        }
    }
}
```


## Question 12

Write a function named `reverse` that takes an array of integers named `numbers` as a parameter. The function should return an array with the numbers from `numbers` in reverse order.


Example:
Input: `reverse([1, 2, 3])`

Output: `[3, 2, 1]`

```swift
func reverse(_ numbers: [Int]) -> [Int] {
    let reversedArray = Array(numbers.reversed())
    return reversedArray
}
```


## Question 13

Write a function that prints out the most frequently appearing Int in an array of Int.

```swift
func intWithMostFrequencies(_ array: [Int]) -> Int {
    var mostFrequentNum: Int = 0
    var freqTracker = 0

    //preparing to create a dictionary with the set made from array as the unique keys
    let uniqueKeys = Set<Int>(array)
    var dictionary: [Int:Int] = [:]

    //populating dictionary with the unique keys and assisning them an updating value
    //loop cycles through the original input array and keeps track of frequencies
    for i in uniqueKeys {
        for currentNum in array where currentNum == i {
            freqTracker += 1
            dictionary[i] = freqTracker
        }
        freqTracker = 0     //resets the tracker at the end of each iteration
    }

    //iterate through the dictionary and updates which key has the highest value
    for k in dictionary.keys {
        if dictionary[k]! > freqTracker {
            freqTracker = dictionary[k]!
            mostFrequentNum = k
        }
    }

    //returns the key that had the highest value (frequency in this context) in the dictionary
    return mostFrequentNum
}
```

## Question 14

Write a function that sums all the even indices of an array of Ints.

```swift
func sumUpEvenIndices(_ array: [Int]) -> Int {
    var sum = 0
    for i in 0..<array.count {
        if i % 2 == 0 {
            sum += i
        }
    }
    return sum
}
```


## Question 15

Write a function that flips a dictionary.  All of the keys are now values and all of the values are now keys.

Example:
Input: `[1: "hi", 5: "bye"]`

Output: `["hi": 1, "bye": 5]`

```swift
func flip(_ dictionary: [Int:String]) -> [String:Int] {
    let setKeysFromValues = Set<String>(dictionary.values)
    var flippedDictionary: [String:Int] = [:]
    
    for k in setKeysFromValues {
        for key in dictionary.keys where dictionary[key] == k {
            flippedDictionary[k] = key
        }
    }
    
    return flippedDictionary
}
```


## Question 16

Write a function that finds the person with the second highest test score in a Dictionary that maps names to scores.

Example:
Input: `["Person 1": 83, "Person 2": 74, "Person 3": 82]`

Output: `"Person 3"`

```swift
func secondBest(_ input: [String:Int]) -> String {
    var highestScore = 0
    var secondHighestScore = 0
    var firstPlace = ""
    var secondPlace = ""

    //finding the highest score and person
    for k in input.keys {
        if input[k]! > highestScore {
            firstPlace = k
            highestScore = input[k]!
        }
    }

    //finding the second highest score and person
    for j in input.keys {
        if input[j]! > secondHighestScore && input[j]! != highestScore {
            secondPlace = j
            secondHighestScore = input[j]!
        }
    }
    return secondPlace
}

```

## Question 17

Write a function that determines if a value is inside of array.

```swift
func isValueInsideArray(_ value: Int, array: [Int]) -> Bool {
    var verification: Bool = false
    for i in array {
        if i == value {
            verification = true
        }
    }
    return verification
}
```

## Question 18

Write a function takes an `Int` as input, and returns true if it is even, or false if it is odd.
Using your new function, write code that prints out whether `dieRoll` is even or odd:

`let dieRoll = Int(arc4random_uniform(6) + 1)`

```swift
func rollResult(_ number: Int) -> Bool {
    if number % 2 == 0 {
        return true
    } else {
        return false
    }
}

let dieRoll = Int(arc4random_uniform(6) + 1)

print(rollResult(dieRoll))
```
## Question 19

Write a function that takes `[Int]` as input. It should return the largest Int in the array.

Using your function from the first step, use String interpolation to print a sentence that states what the largest Int in `myArray` is.

`let myArray = [3,5,1,3,532,1,4,91,20,30,92,143]`

If you haven't already done so, write a function that takes in an Int and returns whether that number is even or odd. Use that function to print a sentence that states whether the largest Int in `myArray` is even or odd.

```swift
func largestNumInArray(_ intArr: [Int]) -> Int {
    var highestNum = intArr[0]
    for i in intArr {
        if i > highestNum {
            highestNum = i
        }
    }
    return highestNum
}

let myArray = [3,5,1,3,532,1,4,91,20,30,92,143]

print("The largest integer in 'myArray' is: \(largestNumInArray(myArray))")

func oddOrEven(_ number: Int) -> String {
    if number % 2 == 0 {
        print("The number is even")
        return "even"
    } else {
        print("The number is odd")
        return "odd"
    }
}

oddOrEven(largestNumInArray(myArray))
```

## Question 20

Write a function that takes a String as input and returns the number of characters in the string

Using your function, print how many characters are in myString:

```swift
let myString = "Swift is a new programming language for iOS, OS X, watchOS, and tvOS apps that builds on the best of C and Objective-C, without the constraints of C compatibility."

func numCharInString(_ string1: String) -> Int {
    return string1.count
}

print(numCharInString(myString))
```


## Question 21

Write a function that counts how many characters in a String match a specific character.  (e.g: count how many "a"s are in a String, or count how many ","s are in a String.

Example:
Input:
```swift
let testString = "This is a test string for your code"
let targetCharacter: Character = "i"

func charCounter(_ string1: String, char1: Character) -> Int {
    var counter = 0
    for c in string1 where c == char1 {
        counter += 1
    }
    return counter
}

print(charCounter(testString, char1: targetCharacter))
```

Sample output: `3`


## Question 22

Write a function that counts how many characters in a String match one of several possible characters.  (e.g: count how many vowels are in a String, or count how many "a"s "b"s and "c"s are in a Sting)

Example:
Input:
```swift
let inputString = "This one is a little more complicated"
let targetCharacters: [Character] = ["a","e","i","o","u"]

func charCounter(string1: String, charArray: [Character]) -> Int {
    var counter = 0
    for possibleMatch in charArray {
        for c in string1 where possibleMatch == c {
            counter += 1
        }
    }
    return counter
}

print(charCounter(string1: inputString, charArray: targetCharacters))
```

Output: `13`


## Question 23

Write a function that returns the number of unique Ints in an array of Ints.

Example:
Input: `let inputArray2 = [3,1,4,1,3,2,6,1,9]`

Output: `4`

```swift
let inputArray2 = [3,1,4,1,3,2,6,1,9]

func uniqueNumsInArray(intArray: [Int]) -> Int {
    var uniqueKeys = Set<Int>(intArray)
    var dictionary: [Int:Int] = [:]

    //populating the dictionary that keeps track of frequencies for each number
    for k in uniqueKeys {
        var frequency = 0
        for num in intArray {
            if k == num {
                frequency += 1
                dictionary[k] = frequency
            }
        }
    }

    //making an array with only numbers that have shown up once
    var uniqueNums = [Int]()
    for k in dictionary.keys where dictionary[k] == 1 {
        uniqueNums.append(k)
    }

    return uniqueNums.count
}

print(uniqueNumsInArray(intArray: inputArray2))
```

//Explanation: 2, 4, 6, 9 are unique in the array. Every other number is not unique.


## Question 24

Write a function that converts a binary number into decimal. The binary number will be given as an array of Ints.

Example:
Input: `let binaryArray = [1,0,1,1,1,0,1]`

Output: `93`

```swift
let binaryArray = [1,0,1,1,1,0,1]

func convertBinaryToDecimal(_ intArray: [Int]) -> Int {
    //make a string out of the Ints in the array of Ints
    var stringArray = [String]()
    for i in intArray {
        stringArray.append(String(i))
    }
    let stringBinary = stringArray.joined()

    //convert the string binary into Int decimal
    let convertedBinary = Int(stringBinary, radix: 2)!

    return convertedBinary
}

print(convertBinaryToDecimal(binaryArray))
```

## Question 25

Write a function named `timeDifference`. It takes as input four numbers that represent two times in a day and returns the difference in minutes between them. The first two parameters `firstHour` and `firstMinute` represent the hour and minute of the first time. The last two `secondHour` and `secondMinute` represent the hour and minute of the second time. All parameters should have external parameter names with the same name as the local ones.

Example:
Input: `timeDifference(firstHour: 12, firstMinute: 3, secondHour: 13, secondMinute: 10)`

Output: `67`

```swift
func timeDifference(firstHour firstHour: Int, firstMinute firstMinute: Int, secondHour secondHour: Int, secondMinute secondMinute: Int) -> Int {
    let hourDiff = abs(firstHour - secondHour)
    let minDiff = abs(firstMinute - secondMinute)
    return (hourDiff * 60 + minDiff)
}
```


## Question 26

Write a function called `filterOdd` that takes an array of ints and returns it with just the even numbers.

Example:
Input:  `filterOdd(arr: [1, 2, 3, 4, 5, 6, 7, 8])`

Output: `[2, 4, 6, 8]`

```swift
func filterOdd(arr intArray: [Int]) -> [Int] {
    var tempArray = [Int]()
    for i in 0..<intArray.count {
        if intArray[i] % 2 == 0 {
            tempArray.append(intArray[i])
        }
    }
    return tempArray
}
```


## Question 27

Write a function called `doubleIt` that takes an array of ints and returns it with all the elements doubled.

Example:
Input: `doubleIt(arr: [1, 2, 3, 4])`

Output: `[2, 4, 6, 8]`

```swift
func doubleIt(arr intArray: [Int]) -> [Int] {
    var arrayDoubled = [Int]()
    for i in intArray {
        arrayDoubled.append(i * 2)
    }
    return arrayDoubled
}
```


Then write a function called `multiplyBy` that takes an array of ints and an int n that will return the array with all the elements multiplied by n.

Example:
Input:  `multiplyIt(arr: [1, 2, 3, 4], n: 4)`

Output:  `[4, 8, 12, 16]`

```swift
func multiplyIt(arr intArray: [Int], n integer: Int) -> [Int] {
    var numsMultiplied = [Int]()
    for i in intArray {
        numsMultiplied.append(i * integer)
    }
    return numsMultiplied
}
```


## Question 28

Write a function called `unwrap` that takes an array of optional ints and returns an array with them unwrapped with any nil values removed.

Example:
Input:  `unwrap(arr: [nil, 7, 4, nil, 43, 11, nil, 2])`

Output: `[7, 4, 43, 11, 2]`

```swift
func unwrap(arr arrOptInts: [Int?]) -> [Int] {
    var unwrappedArr = [Int]()
    for i in arrOptInts {
        if let i = i {
            unwrappedArr.append(i)
        }
    }
    return unwrappedArr
}
```


## Question 29

Write a function that takes an array of bools and returns a dictionary that maps the bools to how many times they appear in the array.

Example:
Input:  `countBools(arr: [true, true, false, true, false, true])`

Output: `[false: 2, true: 4]`

```swift
func countBools(arr arrBools: [Bool]) -> [Bool:Int] {
    let boolKeys = Set<Bool>(arrBools)
    var dictionary: [Bool:Int] = [:]

    for k in boolKeys {
        var frequency = 0
        for element in arrBools where element == k {
            frequency += 1
            dictionary[k] = frequency
        }
    }
    return dictionary
}
```


## Question 30

Write a function that takes a string as input and returns a dictionary that maps each unique character to how many times they appear in the string.

Example:
Input:  `countCharacters(str: "Hello, World!")`

Output: `["H": 1, "r": 1, "!": 1, "e": 1, "o": 2, "l": 3, ",": 1, " ": 1, "W": 1, "d": 1]`

```swift
func countCharacters(str string: String) -> [Character:Int] {
    let dictKeys = Set<Character>(string)
    var dictionary: [Character:Int] = [:]

    for k in dictKeys {
        var frequency = 0
        for c in string where c == k {
            frequency += 1
            dictionary[k] = frequency
        }
    }
    return dictionary
}
```


## Question 31

Write a function that takes this dictionary of baseball teams by ID and returns an array of tuples that contain each team's ID and name.

`let baseballTeamsById = [1001:"Mets", 1002:"Yankees", 1003:"Rays", 1004:"Marlins"]`

Example:
Input:  `dictToTuples(dict: baseballTeamsById)`

Output: `[(.0 1003, .1 "Rays"), (.0 1001, .1 "Mets"), (.0 1004, .1 "Marlins"), (.0 1002, .1 "Yankees")]`

```swift
func dictToTuples(dict dict: [Int:String]) -> [(Int, String)] {
    var arrTuples = [(Int, String)]()
    var baseballTuple: (Int, String)

    for k in dict.keys {
        baseballTuple = (k, dict[k]!)
        arrTuples.append(baseballTuple)
    }
    return arrTuples
}
```

## Question 32

Write a function that checks if a String is a [Palindrome](https://en.wikipedia.org/wiki/Palindrome)

```swift
func palindromeCheck(_ string: String) -> Bool {
    let backwardsString = String(string.reversed())
    if string == backwardsString {
        return true
    } else {
        return false
    }
}
```

## Question 33

Write a function that checks if a String is a [pangram](https://en.wikipedia.org/wiki/Pangram)

```swift
func pangramCheck(_ string: String) -> Bool {
    let formattedString = string.lowercased().components(separatedBy: " ").joined()
    let set = Set(formattedString)
    let alphabet = Set("qwertyuiopasdfghjklzxcvbnm")
    return set == alphabet
}
```


## Question 34

Write your own `min()` and `max()` functions for an Array of Ints

```swift
func min(_ intArr: [Int]) -> Int {
    let sortedArr = intArr.sorted()
    return sortedArr.first!
}

func max(_ intArr: [Int]) -> Int {
    let sortedArr = intArr.sorted()
    return sortedArr.last!
}
```


## Question 35

Given two arrays of Ints, write a function that tells you all the values they have in common.

```swift
func sharedValues(_ arr1: [Int], _ arr2: [Int]) -> [Int] {
    let set1 = Set<Int>(arr1)
    let set2 = Set<Int>(arr2)
    let inCommon = set1.intersection(set2)
    let arrSharedValues = Array(inCommon)
    return arrSharedValues
}
```


## Question 36

Find the most-frequently appearing Array of Ints in an Array of Arrays of Ints.

```swift
func mostFrequentArray(_ matrix: [[Int]]) -> [Int] {
    let arrayKeys = Set<[Int]>(matrix)
    var dictionary: [[Int]:Int] = [:]
    var mostArray = [Int]()
    var highestFrequency = 0
    
    //populate dictionary
    for k in arrayKeys {
        var frequency = 0
        for element in matrix where element == k {
            frequency += 1
            dictionary[k] = frequency
        }
    }
    
    //iterate through dictionary and update what is the highest frequency
    for k in dictionary.keys where dictionary[k]! > highestFrequency {
        highestFrequency = dictionary[k]!
        mostArray = k
    }

    return mostArray
}
```


## Question 37

Given a String as input, rotate all a-z characters by one.  This is called [ROT-1 encryption](http://www.rot-n.com/).

Sample input:
`This is a test string. Anything can be written in here (even Zebras and zebras).`

Sample output:
`Uijt jt b uftu tusjoh. Bozuijoh dbo cf xsjuufo jo ifsf (fwfo Afcsbt boe afcsbt).`

```swift
func rotateLetters(_ string: String) -> String {
    var rotatedString = ""
    let alphabet = "qwertyuiopasdfghjklzxcvbnm"
    for c in string.unicodeScalars {
    //this 'if' conditino is for characters that aren't part of the alphabet
        if alphabet.contains(String(c).lowercased()) == false {
            rotatedString.append(String(c))
        //this 'else' condition is for characters that are part of alphabet
        } else {
            var shiftValueOne = c.value + 1
            if shiftValueOne >=  97 && shiftValueOne <= 122 {
                rotatedString.append(String(Unicode.Scalar(shiftValueOne)!))
            } else if shiftValueOne >= 65 && shiftValueOne <= 90 {
                rotatedString.append(String(Unicode.Scalar(shiftValueOne)!))
            //below else if statements to deal with loop back to "a" or "A" if current character is "z" or "Z". Hardcoded the value.
            } else if shiftValueOne > 122 {
                rotatedString.append("a")
            } else if shiftValueOne > 90 {
                rotatedString.append("A")
            }
        }
    }
    return rotatedString
}
```
