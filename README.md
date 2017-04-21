Go lang Cheat-Sheet 

Structure

```go
package main
import ("fmt")

func main() {
    fmt.Println("Hello Go")
}
```

Data types

| Type    | Declear | Value  |
|---------|---------|--------|
| Boolean | (bool) | true,false |
| Integer | (int) | (-9223372036854775808) - 9223372036854775807 |
| Unsigned Integer | (uint) | 0 - 18446744073709551615 |
| Float32 | (float32) | |
| Float64 | (float64) | |
| Complex64 | (complex64) | |
| Complex128 | (complex128) | |
| String | (string) | |
| Byte | (byte) | |
| Array 1D | [{length}]{type} |  [10]int |
| Array 2D | [{length}][{length}]{type} | [5][5]int |
| Pointer | | *X , &X |

Operators

| Operator | Description |
|----------|-------------|
| + | addition |
| - | substraction |
| * | multiplication|
| / | quotient |
| % | moduration | 
| == | equal |
| != | not equal |
| < | less than |
| > | greater than |
| <= | less than or equal |
| >= | greater than or equal|
| && | logical AND |
| \|\| | logical OR |
| !  | logical NOT |


Statements

| Statement |
| --------- |
| if |
| if else |
| switch case|

```go
//if
if( a<b ){

}

//if-else 
if( a<b ){

}else{

}

//switch-case
switch () {

    case : 
    case :
    detault : 

}
```


Loops

| Loop |
| --------- |
| for |
| break |
| continue|


```go

for a:=0 ; a<10 ; ++ {

}

for a<b {
    a++
}

var numbers = [6]int{1, 2, 3, 5} 
for i,x:= range numbers{
    // i is the index, x the element
}

//you only need e:
for _, e := range a {
    // e is the element
}

//you only need the index
for i := range a {
}

for a:=0 ; a<10 ; ++ {
    if( a == 5 ){
        continue
    }

    if( a == 7 ){
        break
    }
}

```

Functions

```go
//basic 
func name(){

}

//function with parameter
func name(param1 string,param2 int){}

//function with parameter same type
func name(param1 ,param2 int){}

//function return value
func name() int {
    return 1
}

//function return multiple values
func multipleValues() (int,string) {
    return 1,"test"
}
var x,str = multipleValues()

//function return multiple values with param names
func multipleValues2() (n int, s string) {
    n = 42
    s = "test"
    return
}
var x,str = multipleValues2()


//function as attribute
func main(){

    test := func() int {
        return 1
    }

    fmt.Println( test() )
}


//function with multi parameters
func multiParams(args ...int){
    total := 0
    for i,v:= range args{
        total += v
    }
    return total
}
multiParams(1,2,3)
multiParams(5,5)

```

Type Conversions

```go
type_name(attribute)

var i int = 10
var f float64 = float64(i)
```


Arrays utility functions
```go
make( type , lenght , capacity )
len( array )
cap( array )
array = append( array , [value] )
copy( new_array , array )

arr := []int{1,2,3,4,5}
arr         //[1 2 3 4 5]
arr[1:4]    //[2 3 4]
arr[:3]     //[1 2 3]
arr[3:]     //[4 5]

new_arr := arr[:4]
new_arr     //[1 2 3 4]
```

Map
```go
mapping := make(map[string]int)
mapping ["key"] = 42
mapping ["strs"] = 40
fmt.Println(mapping) // map[strs:40 key:42]
fmt.Println(mapping["key"]) // 42

value,has_value := mapping["key"]
fmt.Println( value,has_value ) // 42 true

value1,has_value1 := mapping["key1"]
fmt.Println( value1,has_value1 ) // 0 false

delete(Map,key)
delete(mapping,"key")
fmt.Println( mapping["key"] )   // 0
```

Structure
```go
type Mathes struct {
    X,Y int
}

func (m Mathes) sum() int { // return as value
    return m.X+m.Y
}

func (m *Mathes) sum_pointer() int {    // return as pointer (Reference)
    return m.X+m.Y
}

func (m Mathes) add1() {    // mutating by value as value
    m.X+=1
    m.Y+=1
}

func (m *Mathes) add1_pointer() {   // mutating by reference as pointer
    m.X+=1
    m.Y+=1
}

func sum_function_argument(v *Mathes) int{ // funciton argument
    return m.X+m.Y
}

func main() {
    m := Mathes{10,20}
    fmt.Println(m.X,m.Y)    // 10 20
    fmt.Println(w.sum())    // 30
    fmt.Println(w.sum_pointer())    // 30
    fmt.Println(sum_function_argument(&w))    // 30

    fmt.Println("mutating by value")
    fmt.Println(w.X)    //10
    w.add1()
    fmt.Println(w.X)    //10

    fmt.Println("mutating by reference")
    fmt.Println(w.X)    //10
    w.add1_pointer()
    fmt.Println(w.X)    //11
}
```

Error Handling
```go
    import (
        "fmt"
        "errors"
    )
    
    func main() { 
        result, err:= Divide(2,0)

        if err != nil {
                fmt.Println(err)
        }else {
                fmt.Println(result)
        }
    }

    func Divide(value1 int,value2 int)(int, error) {
       if(value2 == 0){
          return 0, errors.New("value2 mustn't be zero")
       }
       return value1/value2  , nil
    }
```
