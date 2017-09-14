# Swift-3
Basic Code of Swift 3

```swift
/*
swift 3
*/

var hello = "Hello "
var world:String = "World"
var msg = hello + world
// print(msg)
print("Hello \(world)")
```

## Data type
```swift
let pi = 3.14159

var myAge:Int = 21
print("Min Int \(Int64.min)")
print("Max Int \(Int64.max)")

var pi2: Float = 3.1415
var pi3: Double = 3.1415

//print("Min Double \(DBL_MIN)")
//print("Max Double \(DBL_MAX)")

print("Max Float \(Float.greatestFiniteMagnitude)")

var canVote: Bool = true
var myGrade: Character = "A"
//print(myGrade)
var three: Double = 3.0
var two: Int = 2
var five = three + Double(two)
//print(five)
print("3: \(Int(3.14))")
```

## Conditional
```swift
var age:Int = 8

if age < 5{
    print("Go to Preschool")
}else if age == 5{
    print("Go to Kindergarden")
}else if (age > 5) && (age <= 18){
    var grade: Int  = age  - 5
    print("Go to Grade \(grade)")
}else{
    print("Go to College")
}

var income: Double = 12000
var gpa: Double = 3.7

print("Get Grant: \((income < 15000) || (gpa >= 3.8))")
print("Not True : \(!true)")

var canDrive :Bool = age >= 16 ? true : false
print(canDrive)

let ingredient = "pasta"
switch ingredient{
    case "tomatoes", "pasta":
        print("Spaghetti")
        fallthrough
    case "beans":
        print("Burrito")
    case "potatoes":
        print("Mashed Potatoes")
    default:
    print("Water")
}

let testScore: Int = 89
switch testScore{
case 89...100:
    print("You got on A")
default:
    print("You got on F")
}
```


## Basic Operation
```swift
print("5 + 4 = \(5 + 4)")
print("5 - 4 = \(5 - 4)")
print("5 * 4 = \(5 * 4)")
print("5.0 / 4.0 = \(5.0 / 4.0)")
print("5 % 4 = \(5 % 4)")

print("4 + 5 * 10 = \(4 + 5 * 10)")
print("(4 + 5) * 10 = \((4 + 5) * 10)")

var randNum: Int = 5
randNum += 1
print(randNum)
randNum -= 1
print(randNum)

// There is also sin, cos, tan, asin, acos, atan, sinh, cosh, tanh
// print("log(2.718) = \( log2(2.718) )")
```

## String
```swift
var randStr = "This is a random string"
var randStr2 = " and here is another"
var randStr3 = randStr + randStr2
print("Length : \(randStr3.characters.count)")

print("First : \(randStr3[randStr3.startIndex])")

let index5 = randStr3.index(randStr3.startIndex, offsetBy: 5)
print("5th : \(randStr3[index5])")

print("Empty : \(randStr.isEmpty)")

randStr2.insert("A", at: randStr2.startIndex)
print(randStr2)

randStr2.insert(contentsOf: "string ".characters, at:
    randStr2.index(randStr2.startIndex, offsetBy: 2))
print(randStr2)

let startIndex = randStr2.index(randStr2.startIndex, offsetBy: 2)
let endIndex = randStr2.index(randStr2.startIndex, offsetBy: 9)
let stringRange = startIndex ..< endIndex
//print(stringRange)
let subStr = randStr2.substring(with: stringRange)
//print(subStr)

if let hereMatch = randStr2.range(of: "here"){
    randStr2.replaceSubrange(hereMatch, with: "there")
}
print(randStr2)
```

## Array
```swift
var array1 = [Int]()
array1.append(5)
array1 += [7,9]
print("Index 1 : \(array1[1])")
array1[0] = 4
print(array1)
array1.insert(10, at: 3)
print(array1)
array1.remove(at: 3)
print(array1)

array1[0...2] = [1,2,3]
print(array1)
print("Length : \(array1.count)")

var array2 = Array(repeating: 0, count: 5)
print(array2)

var array3 = array1 + array2
print(array3)

for itm in array3{
    print(itm)
}

for (index, value) in array3.enumerated(){
    print("\(index) : \(value)")
}

var array4 = [1,2,3]
for itm in array4{
    print(itm)
}

for i in 1...5{
    print(i)
}

for i in 1...10 where i % 2 == 0{
    print("Even : \(i)")
}

var i: Int = 1
while i < 10{
    if i % 2 == 0{
        i += 1
        continue
    }
    if i == 7{
        break
    }
    print(i)
    i += 1
}

let magicNum: UInt32 = arc4random_uniform(10)
var guess: UInt32 = 0
// print(magicNum)
repeat {
    print("Guess : \(guess)")
    guess += 1
} while (magicNum != guess)

print("Magic Number was \(magicNum)")
```

## Dictionary
```swift
var dict1 = [Int: String]()
print("Empty : \(dict1.isEmpty)")

dict1[1] = "Paul Smith"
print(dict1)

var cust:[String: String] = ["1" : "rezwan", "2" : "zakia"]
print(cust)
print("Size : \(cust.count)")

cust["3"] = "zemi"
cust["3"] = "zannatul"
print(cust)

if let name = cust["3"] {
    print("Index 3: \(name)")
}
cust["3"] = nil
print(cust)

for (key, value) in cust {
    print("\(key) : \(value)")
}
```

## Tuples
```swift
let height: Double = 6.25
let weight: Int = 175

let myData = (height, weight)
print("Height : \(myData.0)")

let myData2 = (height: 6.25, weight: 175)
print("Weight: \(myData2.weight)")
```

## Optional
```swift
var politicalParty: String?
politicalParty = "Independent"

if politicalParty != nil {
    let party = politicalParty!
    print("Party : \(party)")
}

if let party = politicalParty {
    print("Party : \(party)")
} else {
    print("No Party")
}

let party = politicalParty ?? "No Party"
print(party)
```

## Function
```swift
func getSum(num1: Int, num2: Int){
    print("Sum : \(num1 + num2)")
}
getSum(num1: 5, num2: 6)

func getSum2(num1: Int, num2: Int = 1) -> Int{
    return num1 + num2
}
print("Sum : \(getSum2(num1: 8, num2: 6))")

func getSum3(nums: Int...) -> Int{
    var sum: Int = 0 
    for num in nums{
        sum += num
    }
    return sum
}
print("Sum : \(getSum3(nums: 1,2,3,4))")

func doMath(num1: Double, num2: Double){
    func divide() -> Double{
        return num1 / num2
    }
    print("Divide : \(divide())")
}
doMath(num1: 5.0, num2: 6.0)

func twoMults(num: Int) -> (two: Int, three: Int){
    let two: Int = num * 2
    let three: Int = num * 3
    return (two, three)
}
let mults = twoMults(num: 2)
print("2 Mults : \(mults.two), \(mults.three)")

var square: (Int) -> (Int) = {
    num in
    return num * num
}
print("5 Squared : \(square(5))")

var squareCopy = square
print("5 Squared : \(squareCopy(5))")

let numbers = [8,9,2,4,1,0,7]
let sortedNums = numbers.sorted(by: {
    x, y in x < y
})
for i in sortedNums {
    print(i)
}

let squareNums = numbers.map {
    (num: Int) -> String in
    "\(num * num)"
}
print(squareNums)

func funcMaker(val: Int) -> (Int) -> Int {
    func addVals(num1: Int) -> Int{
        return num1 + val
    }
    return addVals
}
let add4 = funcMaker(val: 4)
print("4 + 5 = \(add4(5))")

func doMath2(_ mathFunc: (Int, Int) -> Int, val: Int){
    print("Sum : \(mathFunc(val, val))")
}
func addNums(a: Int, b: Int) -> Int{
    return a + b
}
doMath2(addNums, val: 5)

let nums2 = [1,2,3,4,5,6]
let evenNums = nums2.filter{
    (num: Int) -> Bool in
    return num % 2 == 0
}
print(evenNums)

let sum2 = nums2.reduce(0) {
    (x: Int, y: Int) -> Int in
    return x + y
}
print(sum2)
```

## Enumeration
```swift
enum Emotion{
    case joy
    case anger
    case fear
    case disgust
    case sad
}
var feeling = Emotion.joy
feeling = .anger
print("Angry : \(feeling == .anger)")
```

## Struct
```swift
struct Rectangle {
    var height = 0.0
    var length = 0.0
    
    func area() -> Double {
        let area = height * length
        return area
    }
}
let myRect = Rectangle(height: 10.0, length: 5.0)
print("Area : \(myRect.height) * \(myRect.length) = \(myRect.area())")
```

## Class
```swift
class Animal {
    var name: String = "No Name"
    var height: Double = 0.0
    var weight: Double = 0.0
    var sound: String = "No Sound"
    
    init(name: String, height: Double, weight: Double, sound: String){
        self.name = name
        self.height = height
        self.weight = weight
        self.sound = sound
    }
    
    func getInfo(){
        print("\(self.name) is \(self.height) cms tall and weights \(self.weight) kgs and likes to say \(self.sound)")
    }
    
    func getSum(num1: Int, num2: Int) -> Int{
        return num1 + num2
    }
    
    func getSum(num1: Double, num2: Double) -> Double{
        return num1 + num2
    }
}
var rover = Animal(name: "Rover", height: 38, weight: 12.7, sound: "Ruff")
rover.getInfo()

class Dog: Animal{
    final func digHole(){
        print("\(self.name) digs a hole")
    }
    
    override func getInfo(){
        super.getInfo()
        print("and digs holes")
    }
}
var spot = Dog(name: "Spot", height: 38, weight: 12.7, sound: "Ruff")
spot.getInfo()

func printGetInfo(animal: Animal){
    animal.getInfo()
}
printGetInfo(animal: rover)
printGetInfo(animal: spot)

spot.name = "Doug"
print("2 + 5 = \(spot.getSum(num1: 2, num2: 5))")
print("2.2 + 5.6 = \(spot.getSum(num1: 2.2, num2: 5.6))")

print("Is Spot a Dog : \(spot is Animal)")
```

## Protocol
```swift
protocol Flyable {
    var flies: Bool { get set }
    
    func fly(distMiles: Double) -> String
}

class Vehicle: Flyable{
    var flies: Bool = false
    var name: String = "No Name"
    
    func fly(distMiles: Double) -> String{
        if (self.flies){
            return "\(self.name) flies \(distMiles) miles"
        }else{
            return "\(self.name) can't fly"
        }
    }
}

var fordF150 = Vehicle()
fordF150.name = "Ford f-150"
fordF150.flies = false
print(fordF150.fly(distMiles: 10))
```

## Error Handling
```swift
enum DivisionError: Error{
    case DivideByZero
}

func divide(num1: Float, num2: Float) throws -> Float{
    guard num2 != 0.0 else{
        throw DivisionError.DivideByZero
    }
    return num1/num2
}
do {
    try divide(num1: 4, num2: 0)
} catch DivisionError.DivideByZero{
    print("Can't Divide by Zero")
}
```

## Extension
```swift
extension Double{
    var km: Double { return self * 1000.0 }
    var m: Double {return self }
    var ft: Double { return self * 3.28 }
    var inch: Double { return self * 39.37 }
    
    mutating func square() -> Double {
        let sqr = self * self
        return sqr
    }
}
let oneMeter = 1.0.inch
print("One Meter is \(oneMeter) inches")

var randNum2:Double = 5
print("Square of 5 : \(randNum2.square())")
```
