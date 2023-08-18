### Hello world
```Golang
Package main
import "fmt"

func main(){
fmt.Println("hello world")
}
```

### Variable Declaration
#### Normal variable
```Golong
//Function One
var a int

//Function Two
var a int = 100

//Function Three
var a = 100

//Function Four (Automatically match the data type)
a:=100
```

**Notice**
```Annotation

The fourth declaration method cannot be used for the global variable, only being used in a function structure.
```

For simplificity, multiple variables can be declared in a structure.
```Golong
//with the same type
var x,y int=10,100

//with distinct types
var(
	x int =10
	y bool=true
)
```

#### Constant Variable

Modifications cannot be allowed for constant variables
```Golong
const length int = 100
```

Automatically increasing variable $iota$  increases line by line

```Golong
const{
	x = iota // iota=0, x=0
	y        // iota=1, y=1
	z	     // iota=2, z=2
}
```

### Function Definiaition

* Function Pattern
```Golang
func $FUNCTION_NAME($Params) ($RETURN_VALUE){

}
```

* Examples
```Golong
1. None return value
func foo(a string){

}

2. One return value
func foo(a string) int{
return 1
}

3. Multiple return values
func foo(a string) (int, string){
return 11,"hello"
}

func foo(a string) (r1 int, r2 string){
	r1=0
	r2="hello"
}
```
* init() function
```Annotation

It will be perfomed at the end of importing packages. For the package list, their init() will be invoked recursively.

package list: lib1 -> lib2->lib3
// -> means import
init() invoking order: lib3->lib2->lib1
```

### Import Package

By default, Golong will report an error if imported packages are unused. An anonymous import approach can bypass this limit.
```
import(
// anonymous import
 _ "lib1"
)
```

### Defer Operation
```Annotation
The defer keyword will push the latter function into a stack. After finishing the other operations, current function will perform the defer stack with LIFO(后进先出).
```

Example
```Golong

func main(){
	defer fmt.Println("1")
	defer fmt.Println("2")

	fmt.Println("3")
	fmt.Println("4")	
}

Output:
3
4
2
1
```

### Slice

In essence, it acts as a dynamic array. 
```Golong
//Constant array
var myArray [10]int

myArray := [10]int{0,1,2}

Notice: the constant array must match the formal param's length while conveying it to the function.

//dynamic array

// without space
var myArray [] int
// allocation space
myArray=make([]int, 3)

// merge aformentioned operations
myArray:=make([]int, 3)

// list the slice's elements
for k,v := range myArray{
	...
	// k is the index
	// v is the value
}

// append elements 
myArray=append(myArray,3)

// slice elements
m=myArray[:2]
```

