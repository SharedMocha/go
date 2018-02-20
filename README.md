Packages-
fmt,time,strconv,string,io,image,io/ioutil,"log"
    "net/http",testing

fmt.Println
strconv.Atoi

Interfaces
-
io.Reader



Keywords-
Function -without receiver
--

Method -func with receiver
--
Verbs -formaters %T,%s,%g,%f,%v(display its value)
--
Exported Names- upper case letters used from other package-Public
--
naked return ->A return statement without arguments returns the named return values. This is known as a "naked" return.
 := ->easy assign value -cant use this outside function
--
 int / uint ->take 32 bit or 64 bit sizes depending on the system
--
 constant variables->decalred at the top after imports.
--
 ex: const True = true or const value int = 5
--
 //Remember -Const always has to be assgined a value and you cant use :=
Go Lang ->
No Inheritance,Overriding and Overloading
No colun at the end.

--
switch
--
if
--
for
--
defer - do something like cleanup after rest of all functions around it are complete.
//like closing files
-->
Nil slices -The zero value of a slice is nil.A nil slice has a length and capacity of 0 and has no underlying array.
	var s []int
---
s := [2]int{"lula","jala"}
s := []int{"lula","jala"}
s:= make([]int,10)
s:= make(map[int]int)
s:= make(chan int)
s:= [][]int{[]int{"lula","jala"},[]int{"lula","jala"}}
s.append()
s = append(s,1,2,3)

make--
append--
range--
	for i := range pow {
		pow[i] = 1 << uint(i) // == 2**i
	}
	or
		for _, value := range pow {
		fmt.Printf("%d\n", value)
	}
--
-->	
This is known as "dereferencing" or "indirecting".
// indirecting   =  p = &i
// dereferencing =  fmt.Println(*p) -->Accessing value of  something using a pointer
ereferencing a pointer means accessing the value of the variable which the pointer points to. *a is the syntax to deference a.
---slice  vs dynamic slice
--slice length
--slice capacity
---struct
----array
Struct
Struct Literals-A struct literal denotes a newly allocated struct value by listing the values of its fields.
type Vertex struct {
	X, Y int
}

var (
	v1 = Vertex{1, 2}  // has type Vertex
	v2 = Vertex{X: 1}  // Y:0 is implicit
	v3 = Vertex{}      // X:0 and Y:0
	p  = &Vertex{1, 2} // has type *Vertex
)
------

MAPS can be used to go through linkedlist
---------------------------
funcitons can be passed as arugyments -LOL
	jamica := func (x,y int) int{
	return x+y
	}
	fmt.Println(jamica(5, 12))
or
 function being sent to another funcitons
func name(fn (int,int) int) int{
fn(1,2)

}
fmt.Println(something(jamica))
//now first something is called and it passed value to above jamaica funcitons
-------------

Function closures :-:-:-:-:-:-:-:-:
Go functions may be closures. A closure is a function value that references variables from outside its body. The function may access and assign to the referenced variables; in this sense the function is "bound" to the variables.
https://tour.golang.org/moretypes/25
fibonaci series using function closures
package main

import "fmt"

// fibonacci is a function that returns
// a function that returns an int.
func fibonacci() func() int {
 i := 1
 j := 1
 var k int
return func() int{
 k = i + j
 i = j
 j = k
return k
}
}

func main() {
	f := fibonacci()
	for i := 0; i < 10; i++ {
		fmt.Println(f())
	}
}




------------------------
In go we specifiy the main method same like java as
func main(){

}
------------------------

We also add the package name at the top-Same like java
package main
------------------------

For printing here we use fmt.First 
"import "fmt""
then -> fmt.Printf()
------------------------
IMPORTs

import "fmt"
import "math"

OR

import ("fmt""math")

--------------------------
STring formaters
%f  = 1._ _ _ _ _
%g  = 1._ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
%T - TYpe
------------
Exported names
-->
Public variables from other packagers/exported names can be imported 
using UPPER CASE Letters
ex -
import("math")
fmt.Println
----Beauty of declarations in golang
//See how easy it is to assing values and also both string and int in one go-
a,b := swap(1,"hello");
func swap(a int, b string) (int,string){

}
-----------------------
variable declaration 
var c int
var c int = 30
c = 30

c := 30
c := 10
var a,b,c := true,false,"sumo"
-------------------
converserison
var i int = 42
var f float64 = float64(i)
var u uint = uint(f)

Or, put more simply:

i := 42
f := float64(i)
u := uint(f)
-----------------
SImple for loop
for i:=0;i<=10;i++{
fmt.Println(i)
}
-----Integresting -if
if a := 17; a <=10{

}
//Here you can intiliaze a variable like for loop and then check for a condition
same like for bit not for--only differenc is it doest itterate
----Switch case
beauty is you can declare both intiliaze and value pass in one step
switch i := runtime.GOOS; i {
case "darwin":
fmt.Println("1");
case "linux":
fmt.Println("3");
default:
fmt.Println("2");
}
2 similar items like above
TYPE SWITCHES
*one is select~case used for gorotunies when a gororutine calls mulitple channels and picks vlaue from one
Select
*other place is interface--usally interface store value like(value,type)--now we can use this simliar appoah
to check what type is the call whether its int,string,struct etc
Select
--------------------------------
Pointers
func main(){
  a := 10 //Assiging some value 
  b := &a; //Getting its memory location
  fmt.Println(*b) //Before Modifying //*b is called derefereince
  *b = 20 //Modifying its undelrying value
  fmt.Println(*b) //After Modifying
 }
 ereferencing a point
 er means accessing the value of the variable which the pointer points to. *a is the syntax to deference a.
 
 ---------
 Struct
 type Vertex struct {
	X int
	Y int
}

func main() {
	v := Vertex{1, 2}
	p := &v
	p.X = 1e1
	fmt.Println(v)
}

----
Arrays
var a [2]int = {1,2}
var a [2]string
	a[0] = "Hello"
	a[1] = "World"
	fmt.Println(a[0], a[1])
	fmt.Println("samaa",a)

	primes := [6]int{2, 3, 5, 7, 11, 13}
	fmt.Println(primes)
	
	-->
		//Sample Array Declaration
	var XXXX [2]int
	XXXX[0] = 1
	//Short declaration
	a := [5]int{1,2,3,4,5}
----
Slice
//Sample Slice Declaration
	var YYYYY []int
	YYYYY[0] = 2
	//Short declaration
	ZZZZZ := []int{1,2,3,4,4,5,6,76,7,8}
	
=----
Slice accessing a struct
type local struct{
  ludo int
  sump string
}
//Initialize
var A []local
A  = local
A := local{{1,"h"},{2,"t"}}
//Another way of adding elment to slice using struct is
	type someval struct{
	name string
	age int
	}
	
	var temp []newtempvaluetostorestruct
	newtempvaluetostorestruct = append(newtempvaluetostorestruct, someval{1,"lala"})
=-------Remeber 2 ways to intialize slice from struct---
type Activities struct{
   name string
   age int
}

s := make([])
s := make([]int,10)
s := make([]Activities,0)
s = append(s,Activities{1,2})

one is using := and one is using default way
Default way is -
	type someval struct{
	name string
	age int
	}
	var temp []newtempvaluetostorestruct
	newtempvaluetostorestruct = append(newtempvaluetostorestruct, someval{1,"lala"})
Using := operation
	type someval struct{
	name string
	age int
	}
	tempValue := someval{{1,"lala"},{2,"value"}}
	
	----------------Slice vs array-------
	Declaration
	var lala [2]int
	var lala []int
	
	Intializaiton
	lala[0] = 1;
	
	Declaration short ay
	lala := [4]int{1,2,3,4}
	lala := []int{1,2,3,4}
	
	Slice with struct declration and intilization
	lula := structname{{},{},{}....}
	
	var lula []structname
	lula  = append(lula,structname(1,2))
	----Accessing elements of a slice  or array as a group-------
	a[0:10]
a[:10]
a[0:]
a[:]
-------
The length of a slice is the number of elements it contains.

The capacity of a slice is the number of elements in the underlying array, counting from the first element in the slice.

The length and capacity of a slice s can be obtained using the expressions len(s) and cap(s).

-----------DYNAMIC SLICE----
firstly the problem with slice is -its size cant be changed
 a := []int{1,2,3,4} //Cant change size
 now lets check dynamic array
 a := make([]Type,length,capacity)
 ex a := make([]int,5)
	
DYNAMIC SLICE--APPEND--adding
s = append(slicename,value1,value2)
	j := append(s, 0,2) or 
	var s []int && 	s = append(s, 1)
--->
var test []structtype
test = append(test ,structtype(value1,vlaue2))

-----------------------> <----------------------
//Array
Declaration 
var a [5]int

Initilization
a = {1,2,3,4,5}

Accessing

a[0]

Assigning

a[0] = 1
------------------------> <-------------------------
//Array
Declaration 
var a [5]int
Initilization
a[0] = 1
Accessing
a[0]
Declaration and Initilization in one go
a := [5]int{1,2,3,4,5}

//Slice //ArrayList
Declaration
var b []int
b  = []int{}

Declaration & Initilization
a := []int{1,2,3,4,5}
a := make([]int,length,capacity)
a := make([]int,0)
//append
a  = append(a,value)
a  = append(a,6,7,8)

//Map
Usually map goes with struct as its key-value --U can only use map
Lets define a struct first
type person Struct{
   name string
   countriesvisited []string
}
//Make a map
//Declare and set value and access(access and set is similar to array)
var makingmap map[string]string
var somevariable map[keytype]valuetype
m = map[string]int{}

//set value
somevariable["Hemanth"] = "USA"

//Intilize and declare
makemap := map[string]string{"hemanth":"usa","div":"in"}

Using Make
makemap := make(map[string]string)
//Accessing using for loop
 for i := range makemap{
 fmt.Println(longMap[i])
 }
 
 //2 value assignment to check if value is present
 i, ok := m["route"]
  _,present = m["keyvlaue"]
   ok and present will hold boolean if its there or not
------------
Function closures
https://www.calhoun.io/what-is-a-closure/

A closure is something like an abstract func-
but the beauty is it cna access variables outside its scope-
say if we have a function and another funciton inside it as annonymus-
the inside funciton is called closure funciton and it can access elements of the above funciton
------Annoynimus functions---------
https://www.calhoun.io/what-is-a-closure/
--------------
Method
any function with a receiver
or any funciton which receives Type---
-----
value receivers VS POINTER RECEIVER
POINTER receivers -cant modify the values of underlying type--uslaly pointr rceivers dont return anything as the mainly modify udnerlying struct type 

VALUE receivers - cant modify underlying values of a type
so mostly we use pontr receiver

check below links --we can implement same pointers in funciton too-
https://tour.golang.org/methods/5

There are two reasons to use a pointer receiver.

The first is so that the method can modify the value that its receiver points to.

The second is to avoid copying the value on each method call. This can be more efficient if the receiver is a large struct, for example.
---------
BEAUTY IS U CAN DEFINE FUNC ON TYPES-EVEN MORE YOU CAN DEFINE FUNC ON ONE TYPE WITH POINTER RECEIVER AND WITHOUT POINTER RECIVER
I.E u can specify that sos and so method can only be called in a pointer is apssed--so it can edit
wheras for read only u can tell them use these methods

------------------INTERFACES contains empty methods---REMEBER--INTERFACES ARE Implemneted on types like struct
Example:-
type Local interface{
getName()
updateName() boolean
}
type Person struct{
  name string
  age int
}
func (p Person) getName(){

}
func (p *Person) updateName() boolean{

}
-------------METHODS VS INTERFACES IN GO LANG-
A method is something which is a functin with receiver-a receiver can be a type like struct
->an interfce has abstract methods that need to be implmented-
usually the way to implement interface is 
+define interface type with empty methods and return types
+define struct
+create methods that take in above struct and has method names as deinfed in above interface
+Now in main func define a variable for itnerface and then assgn/attach it to struct(VV IMP-This is only for interface not method)
+finally call methods using variable u declaed in above step
------

---------------------------
Interface values
Under the covers, interface values can be thought of as a tuple of a value and a concrete type:

(value, type)
An interface value holds a value of a specific underlying concrete type.

Calling a method on an interface value executes the method of the same name on its underlying type.
How this works ?
1.)First define interface and its methods
step 2.)Next define types like struct
step 3.)now marry bth struct and interace--Here define method either on pointers or directly
REST -> USE ABOVE DELCARED STUFF->Now in your main funciton or anyware you need to bind all these like below
1.)var somevariable Interfacetype //Declare
2.)somevariable = structTYpe(value)// Here structTYpe is delard in step2
3.)as of now we decalred intrface and set a value to our struct 
last step is calling methods deinfed in step 3
we are Marry it with some structe

---------COOL THINS IS U CAN HAVE MANY METHODS WITH SAME NAME --ONLY RULE IS RECEIVER SHOUD CHANGE--

empty interface
The interface type that specifies zero methods is known as the empty interface:

interface{}
An empty interface may hold values of any type. (Every type implements at least zero methods.)
--SAMPLE CODE WITH METHOD AND INTERFACE--
package main

import "fmt"

type Person struct{
   name string
   age string
}
type PersonActivities interface{
  Eating() string
}
type IndianName string

func (p Person) Drinking(){
  fmt.Println(p.name," - Yes he is drinking")
}
func (in IndianName) Drinking(){
  fmt.Println("Yes he is drinking")
}
func (p Person) Eating() string{
  return "is eating"
}
func (in IndianName) Eating() string{
  return "is indian name"
}

func main(){
hema := Person{"Hemanth","21"}
hema.Drinking()
var pa PersonActivities;
pa = Person{"Hemanth","21"}
fmt.Println(pa.Eating())
pa = IndianName("Sundha")
fmt.Println(pa.Eating())
}
---------
Type assertion - usually an interface holds value like this {value,type}
now a type assertion is used to get that value--usally we check it as below
variable,booleancheck := interfaceinstance.{type}
Example
type human interface{
 Eating() string
}
type persondetails struct{
 name string
}
func (p persondetails) human() string{
 //Do nothing
}
func main(){
var i human//decalre interface
i := persondetails{"hema"} //implements struct
i.human()//as an example

// type assertion to get "hema" back
i,ok := i.(persondetails)
//here we store value "hema" in i and true/false in ok

}

-------TYPE SWITCHES---
SO NOW if we need to check what type is a type assertion --to see which type it belong to--we do this because
an interface method cna be attached to any struct type--like string interfer-
one method with multiple types of receiver is possible--nw ifwe need to know what type it is beloging and do something
we use type switching--its same like switch -but rather than checking for value-
we check for type of interface
switch v := i.(type) {
case int:
    // here v has type T
case string:
    // here v has type S
default:
    // no match; here v has the same type as i
}
-----------------------
Stringers
One of the most ubiquitous interfaces is Stringer defined by the fmt package.

type Stringer interface {
    String() string
}
A Stringer is a type that can describe itself as a string. The fmt package (and many others) look for this interface to print values.
-------
Errors
---------------
Go programs express error state with error values.

The error type is a built-in interface similar to fmt.Stringer:

type error interface {
    Error() string
}
i, err := strconv.Atoi("42")
----------------
Usually a go program starts at main and executes and closed-it doesnt wait for anything--
now lets get into rountines-->U can think like go routines are light weight threads which are used to
execute concurent process/progreams-Now to tell main method to wait for a go rountine to return results we use channels.
In simple words channels help in syncorning data between multiple go rounties(Think of google search goinf to multiple locations to get data))

Go rountine
channel
range -- if a channel is give size its called buffered channel and range is used to iterage on it

close --telling a channel that no more data will come

select - used in many cases--say for example if we send  aquery to c3 and pega draft--we need to pick which ever comes first-then we cna use select combined with goroutines.
this way if c3 come sback faster we take the result and move on-
its same like switch case
all cases will be executed and which ever comes first will be picked--if multiple come then it randomly picks.
lastly if noting comes back it gives values from default
select {
case i := <-c:
    // use i
default:
    // receiving from c would block
}
The select statement lets a goroutine wait on multiple communication operations.

A select blocks until one of its cases can run, then it executes that case. It chooses one at random if multiple are ready.

---------
sync.Mutex  -telling only one go routeine can accesss a vriable
https://tour.golang.org/concurrency/9
-------------
Type assertion -Access value from an interfac
Function closures - function accessing vairable not in its direct scope
TYPE SWITCHES
Select
Mutex
