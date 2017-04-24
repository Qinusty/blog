---
layout: post
title: 'Learning Go : GoTour'
---

Over my Easter break I was in the mood for something new, I come across this sort of mood every couple weeks, wanting to learn or at least try a new technology.
I narrowed my list of technologies to two languages I was interested in: Go and Rust. I ended up with Go after deciding through the complex process of tossing a coin.
So what did I know about Go? 

- Go was a 'new' language, developed by Google, gaining popularity over the past few years.
- Go was said to be good at handling concurrency.
- Go was a compiled language

So in summary, not much. Over the past week I have worked my way through the GoTour, a series of web pages containing code examples and a REPL for seeing the code in action.
This was a great resource for learning and allowed me to jump straight in without even installing a compiler or an IDE.

The basic syntax for go can be a little different than other languages:

```go
// both of the following do the same thing.
var x int = 5
x := 5

// Once i has been used you can just say
x = 5

// arrays are fixed size
var xs [5]int
xs := [5]int{1,2,3,4,5}

// Strings are strings
var cs string = "Hello World"

// Flow control
a := 5
b := 6

if a < b { // No parenthesis required.
    foo()
} else {
    bar()
}

// Switches are great in Go because break's are not required. 
// Breaks are assumed and fallthrough is required for the c style 
// outcome of not putting in a break.
switch a {
    case 5:
        foo()
    case 6: 
        bar()
        fallthrough // causes the below statement to run
    default:
        fmt.Println("This prints on anything but 5")
}

// Go has something called Short Statements, which can be used in 
// both switch and If statements. The values defined in short
// statements can be used through the else statements too.
if c := a + b; c > 10 {
    fmt.Println("a+b > 10")
} else {
    fmt.Println(c)
}

// Go only has for loops, as nothing else is required.
for i := 0; i < 10; i++ {
    fmt.Println(i) // a standard print statement using the fmt package in go.
}

// while 
i := 0
for i < 10 {
    fmt.Println(i)
    i += 2
}

// looping through collections
xs := []int{1,2,3,4,5}
for index, value := range xs {
    fmt.Println(index, " ", value)
}
for i := 0; i < len(xs); i++ {
    fmt.Println(i, " ", xs[i])
}

// Array slicing - A feature I happily welcome

xs := []int{1,2,3,4,5}
xs = xs[1:3] // {2, 3}
```

# Functions

As a language, Go surprised me with lots of small features which just made writing code easier, features which made sense to me as a developer. For example, Go's functions are defined as such: 

```go
func foo(param int) {
    bar()
}
``` 

This is a familiar syntax for any developer, until you start working with return values.

```go
func foo(param int) int {
    bar()
    return 0
}
```

This is not too different and honestly, I like it. Its easy to read and there is no doubt on what types the function returns. However Go allows you to omit the type of
consecutive parameters with the same type. e.g.

```go
func add(a, b int) int {
    return a + b
}
```

This is quite nice and makes things look a little tidier. My favourite part about function definitions is the ability to name your return values.

```go
func foo(param int) (total int) {
    total = param + 10
    return
}
```

This allows you to use the return value `total` throughout your function before calling return, also allowing you to omit the value after the return statement. However this is not recommended for long functions, but it is still a nice addition and can tidy up some small functions.

# Structs

Go does not have classes, You can group data into structs in a similar way to C as such

```go
type Foo struct {
    val1 int
    val2 int
}
```

Structs can be instantiated like this `foo := Foo{1,2}` or `foo := Foo{val1: 1, val2: 2}` and any of the parameters can be left out and will be initialised at their zero value.

Go allows you to have functions associated with structs to make them feel more like Objects, these are called methods and are declared as such

```go
func (f Foo) Sum() int {
    return f.val1 + f.val2
}
```

The variable f is called a receiver, You can reference this method using the following call.

```go
foo := Foo{1,2}
sum := foo.Sum() // = 3
```

You might have noticed the capital letter at the start of Sum, this doesn't follow traditional camel case from Java, C# etc. This is because of how Go handles packages. A function/type is only exported if it starts with a capital letter. So all types and functions/methods should start with a capital letter if you want them to be accessible from outside the current
package. 

# Interfaces

Interfaces are strange in Go as you do not tell a Struct that it should implement an interface, you just implement the methods.

```go
type Summable interface {
    Sum() int
} 

type Foo struct {
    val1 int
    val2 int
}

// This function with a Foo receiver is picked up by the compiler
// This makes the Foo type compatible with the Summable interface
func (f Foo) Sum() int { 
    return f.val1 + f.val2
}
```

We can now have a function which takes a Summable type and pass in a Foo type object.

```go
func DoubleSum(val Summable) int {
    return val.Sum() * 2
}
```

A great example of how this is used, is within the `fmt` package where the Interface Stringer exists. This is go's equivalent of a Java toString function.

```go
type Stringer interface {
    String() string
}
```

As an example `fmt.Println()` takes any value as long as its type implements the String() function, making it compatible with Stringer.

```go
func (f Foo) String() string {
    return fmt.Sprintf("Foo with val1: %v and val2: %v", f.val1, f.val2)
}
``` 

Now we can do this:

```go
foo := Foo{1,2}
fmt.Println(foo) // outputs: Foo with val1: 1 and val2: 2
```

# Deferring

Another nice feature Go has is the keyword `defer` which adds the following call to a deferred stack which will be popped one by one after the current function returns.
e.g.

```go
for i := 0; i < 5; i++ {
    fmt.Print(i, " ")
    defer fmt.Print(i, " ")
}
// outputs: 0 1 2 3 4 4 3 2 1 

```
This can be useful for cleaning up after a function exits. 

# Pointers

If you're familiar with C, this is basically the same except Go has no pointer arithmetic. If not check out this (page)[http://www.c4learn.com/c-programming/pointer-overview/] for a quick guide to pointers (it's for C but it's the concept of pointers that matter).

```go
i := 5
p := &i // p is set to be a pointer of i
*p += 5 // dereference p and add 5
fmt.Println(i) // outputs: 10
```

If we take our Foo struct and Sum function from before you can see how Go assumes when you try to call a method on a pointer that it should automatically dereference it for you.

```go
foo := Foo{1,2}
p := &foo

p.Sum() // 3
foo.Sum() // 3
(*p).Sum() // 3
// No need for the C style p->Sum()
```

# Summary

So far I quite like Go, I haven't gotten to the more advanced parts of Go yet such as Channels but I'm liking it. The language as a whole feels thought out and looks quite appealing to me. As for community and tools, Go is already making huge strides in those areas as the Go toolkit provides an insane amount of utility, with `go get` available for downloading libraries from git repositories into a configured workspace.

The small feature of 

