# Go

## Basics

### Packages, variables, and functions

- Go program is made up of packages, and it starts running in package main
- "factored" import statement

  ```go
  import (
    "fmt" 
    "math"
  )
  ```

- A name is exported if it begins with a capital letter

  ```go
  math.Pi
  ```

- Type comes after the variable name

  ```go
  func add(x, y int) int { // shortened
    return x + y
  }
  ```  

- Multiples results

  ```go
  func add(x, y string) (string, string) {
    return y, x
  }

  func main (){
    a, b := swap("hello", "world")
    fmt.Println(a, b)
  }
  ```

- Named return values

  ```go
  func split(sum int) (x, y int){
    x = sum * 4 / 9
    y = sum - x
    return
  }

  ```

- Variables

  ```go
  var c, python, java bool
  ```

- Variables with initializers (the type can be omitted)

  ```go
  var c, python, java = true, false, "no!"
  ```

- Short variable declarations
  
  ```go
  c, python, java := true, false, "no!"
  ```

- Type conversions

  ```go
  f := float64(42)
  u := uint(f)
  ```

- Type inference

  ```go
  i := 42           // int
  f := 3.142        // float64
  g := 0.867 + 0.5i // complex 128
  ```

- Constants

  ```go
  const World = "世界“
  ```

- Numeric Constants

  ```go
  const  (
    Big = 1 << 100
    Small = Big >> 99
  )
  ```

### Flow control statements: for, if else, switch and defer

- For

  ```go
  for i := 0; i < 5; i++ {
    sum += i
  }

  // init and post statement are optional
  sum := 1
  for ; sum < 1000; {
    sum += sum
  }

  // For is Go's "while"
  sum := 1
  for sum < 1000 {
    sum += sum
  }
  ```

- if and else

  ```go
  func isPositive(x int) bool{
    if x < 0 {
        return true
    } else {
        return false
    }
  }
  ```

- if with a short statement

  ```go
  func pow(x, n, lim float64) float64 {
    if v:= math.Pow(x, n); v < lim {
        return v
    }
    return lim
  }
  ```

- switch

  ```go
  fmt.Print("Go runs on ")
  switch os:= runtime.GOOS; os {
    case "darwin":
        fmt.Println("OS X.")
    case "linux":
        fmt.Println("Linux.")
    default:
        fmt.Printf("%s. \n", os)
  }

  // p.s.: Switch without a condition is the same as switch true
  ``
  
- Defer statement defers the execution of a function until the surrounding function returns

  ```go
  defer fmt.Println("world")
  fmt.Println("hello")

  // hello
  // world
  ```

- Stacking defers (last-in-first-out)

  ```go
  for i := 0; i < 3; i++ {
    defer fmt.Println(i)
  }
  fmt.Println("done")

  // done
  // 2
  // 1
  // 0
  ```

### More types: structs, slice, and maps

- A pointer holds the memory address of a value

  ```go
  i := 26

  p := &i // 26
  *p = 6 // i = 6
  ```

- A struct (public) is a collection of fields

  ```go
  type Vertex struct {
    X int
    Y int
  }

  v1 := Vertex{1, 2} // {1 2}
  v2 := Vertex{Y: 2} // {0 2}
  v3 := Vertex{} // {0 0}
  p := &Vertex{1, 2} // &{1 2}

  v1.X = 4 // {4 2}
  ```

- Arrays

  ```go
  var a [1]string
  a[0] = "Hello"

  primes := [6]int{2, 3, 5, 7, 11, 13}
  fmt.Println(primes[1:4]) // [3 5 7]
  fmt.Println(primes[:4]) // [2 3 5 7]
  fmt.Println(primes[2:]) // [5 7 11 13]
  ```

- Arrays (struct)

  ```go
  s := []struct {
    i int
    b bool
  }{
    {2, true},
    {3, false}
  }
  ```

- Slice length and capacity

  ```go
  s := []int{2, 3, 5, 7, 11, 13} // len=6 cap=6
  s = s[:0] // len=0 cap=6
  s = s[:4] // len=4 cap=6
  s = s[2:] // len=2 cap=4
  ```

- Nil slices (len=0 cap=0)

  ```go
  var s []int // s == nil
  ```

## Methods and interfaces

## Generics

## Concurrency
