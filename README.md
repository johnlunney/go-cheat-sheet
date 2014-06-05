# Overview

- [Variables](#Variables)
- [Arrays](#Arrays)
- [Slices](#Slices)
- [Maps](#Maps)
- [Control Structures](#Control-Structures)
- [Functions](#Functions)
- [Closures](#Closures)

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
keyValue[1] = "boo!"
delete(keyvalue,1)
y := make(map[int]int)
```

## <a name="Control-Structures"></a>Control Structures

```go

if i == 1{
  //Hey it's one
}else if i==2{
  //It's two
}else{
  //Oh, it's neither
}

var a map[int]int
map[1] = 1
if num,status := map[1]; status{
  fmt.Println(num)
}

switch i{
  case 1: //This one if i is 1. No need of a break
  case 2: fallthrough//This one if i is 2 and then it executes the next case
  case 3: //This one if i is 3
  case 4,5,6,7 : //Yay! All of these will work
  default: //This one when nothing matches
}

i:=1
for i<= 100{
  fmt.Println(i)
  i = i+1
}

for i:=1; i< 1=100;i++{
  fmt.Println(i)
}

arr :=[5]int{1,2,3,4,5}
for n := range arr{
  fmt.Println(n)
}

```

## <a name="Functions"></a>Functions

```go
//Function
func sample(a,b int) int {
  return a*b
}

//Function returning multiple values
func otherFunc(a string, b, c float64) (string, float64) {
  return a, b*c
}

//Variadic functions
func sum(args ...int) int{
  sum:=0
  for _,v := range args{
    total +=v
  }
  return total
}

//Calling the functions
func main(){
  a := sample(1,2)
  b, c := otherFunc("String", 1.2, 2.3)
  d := sum(1,2,3,4,5,6)
}
```

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
