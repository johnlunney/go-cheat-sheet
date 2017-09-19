# Overview

- [Variables](#Variables)
- [Arrays](#Arrays)
- [Slices](#Slices)
- [Maps](#Maps)
- [Control Structures](#Control-Structures)
- [Functions](#Functions)
- [Closures](#Closures)
- [Pointers](#Pointers)
- [Structs](#Structs)
- [Methods](#Methods)


## <a name="Variables"></a>Variables

```go
const title ="Best Series Ever"
var season int = 6
episodes := 22

var(
  a = 5
  b = 6.54
  c = "hello!"
  )
```

## <a name="Arrays"></a>Arrays

```go
var primes [5]int
primes[0]=2

letters := [3]string{"a","b","c"}

temps :=[3]float64{
  1.2,
  2.3,
  3.4,
}
```

## <a name="Slices"></a>Slices

```go
var a []float64
b := make([]string)
arr := [5]int{1,2,3,4,5}
x := arr[0:3]
```

## <a name="Maps"></a>Maps

```go
var keyValue map[int]string
keyValue = make(map[int]string)
keyValue[1] = "boo!"
delete(keyvalue,1)
value,ok := keyValue[1] // Check if a value exists for a key
```

## <a name="Control-Structures"></a>Control Structures

```go
// Basic if
if i == 1{
  // Hey it's one
}else if i==2{
  // It's two
}else{
  // Oh, it's neither
}

// Using if with a statement
if x := someFunc(); x != y{
  fmt.Println("x is not equal to y")
}else{
  fmt.Println("x equals y")
}

// Using if with multiple return value in a statement
var a map[int]int
map[1] = 1
if num,status := map[1]; status{
  fmt.Println(num)
}

switch i{
  case 1: // This one if i is 1. No need of a break
  case 2: fallthrough // This one if i is 2 and then it executes the next case
  case 3: // This one if i is 3
  case 4,5,6,7 : // Yay! All of these will work
  default: // This one when nothing matches
}

i:=1
for i<= 100{
  fmt.Println(i)
  i = i+1
}

for i <100{

}

for i:=1; i < 100;i++{
  fmt.Println(i)
}

arr :=[5]int{1,2,3,4,5}
for n := range arr{
  fmt.Println(n)
}

```

## <a name="Functions"></a>Functions

```go
// Function
func sample(a,b int) int {
  return a*b
}

// Function returning multiple values
func otherFunc(a string, b, c float64) (string, float64) {
  return a, b*c
}

// Function returning named variables
func anotherFunc(a int)(b, c int){
  b = a+1
  c = a+2
  return
}

// Variadic functions
func sum(args ...int) int{
  sum:=0
  for _,v := range args{
    total +=v
  }
  return total
}

// Calling the functions
func main(){
  a := sample(1,2)
  b, c := otherFunc("String", 1.2, 2.3)
  d := sum(1,2,3,4,5,6)

  // A function can be a value
  yetAnotherFunc := func(a, b float64 ) float64{
    return a*a*b
  }

  fmt.Println(yetAnotherFunc(1.3,4.2))
}


## <a name="Closures"></a>Closures

```go
func makeEvenGenerator() func() uint {
    i := uint(0)
    return func() (ret uint) {
        ret = i
        i += 2
        return
    }
}
func main() {
    nextEven := makeEvenGenerator()
    fmt.Println(nextEven()) // 0
    fmt.Println(nextEven()) // 2
    fmt.Println(nextEven()) // 4
}
```


## <a name="Pointers"></a>Pointers

```go

//Simple pointer
func main(){
  x:= 200
  fmt.Println(x) //prints 200
  xPtr := &x
  *xPtr = 0
  fmt.Println(x) // prints 0
}

//Struct pointer
type Person struct{
  Name string
  Age int
  Weight float64
}

func main(){
  p := Person{"Jack",10,50}
  pPtr := &p
  fmt.Println(pPtr.Name) // prints Jack
}

```


## <a name="Structs"></a>Structs

```go
// Defining a struct
type Person struct{
  Name string
  Age int
  Weight float64
  Height float64
}

// Declaring and initializing a struct
a := new(Person)
b := Person{ Name:"John", Age:52, Weight:160.3, Height: 72.0}
c := Person{ "James", 45, 174, 65.5}
d := Person{ Name:"Jim"}
e := Person{}

// Accessing the fields in a struct
a.Name = "Cormoran"
a.Weight = 200

fmt.Println("c's name is ", c.Name)

```

## <a name="Methods"></a>Methods

```go
// Method for the struct Person defined earlier
func (p *Person) BMI() float64{
  return 703.06957964*(p.Weight/(p.Height*p.Height))
}

func main(){
  c := Person{ "James", 45, 174, 65.5}
  fmt.Println(c.BMI())
}
```
