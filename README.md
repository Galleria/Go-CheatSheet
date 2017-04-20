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
[lo:hi] //slice low and high-1
[1:4] //slice from idx 1:3  [0 1 2 3 4 5] 
[:3] //slice from idx 0:2 [0 1 2 3 4 5]
[3:] //slice from idx 2:len-1 [0 1 2 3 4 5]

```

