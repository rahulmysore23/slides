---
title: Session on Go - 1
date: 2021-10-31
author: Rahul
extensions:
  - terminal
  - qrcode
  - image_ueberzug
styles:
  table:
    column_spacing: 15
  margin:
    top: 3
    bottom: 0
  padding:
    top: 3
    bottom: 3
---

# In This Session

- What is Go?
- Why Go?
- Basics
- Let's write some code
- Q & A
- Useful Links

# About me

- **R & D Engineer 2** at Jukshio
- Work on backend with Go
- LinkedIn - rahulmysore23
- Github - rahulmysore23

# What is Go?

- It's a static programming language
- Other static programming languages - C, C++, ...
- Dynamic Programming languages - Python, JavaScript, ...
- Created by Google in 2007
- Made public in 2009
- Designed by industry experts Robert Griesemer, Rob Pike, Ken Thompson 

# Why Go? 

- Fast, Simple, easy and efficient
- Cross platform support
- Concurrency, Goroutines <3
- Great tooling support - Gofmt, GoPls, net/http (pkg) ...
- Has a very active community
- Case studies - https://go.dev/solutions/#case-studies

# Popular tools built with Go

- Docker
- Kubernetes
- Prometheus 
- CockroachDB
- Istio

# Basics - Installation

- Download and install the latest Go binary from - https://golang.org/
- Add Go to the $PATH env variable (Do this in your .bashrc file for a global access)
- Open your terminal and run - go version

```terminal8
bash -il
```

# Basics - Development environment

- Goland (A full fledged Go IDE) - Free trail for 30 days
- VSCode - Install Official Go plugin
- Vim/Neovim - Install vim-go plugin (with a lifetime configuration of vim)

> Don't forget to install an awesome color scheme 

> P.S. It's Gruvbox

# Basics - Hello World

- The following program prints a very popular text

```go
package main

import (
    "fmt" // importing internal go pkg
)

func main() {
    fmt.Print("Another hello world program") // Uses Print function to print 
}
```

# Basics - Run a Go program

- Save the program as - main.go
- All the Go files should end with .go
- Run the program using the command given below

```bash
go run main.go
```

```terminal8
bash -il
```

# Basics - Types

- Numeric - integer, float, byte, rune
- Boolean
- Strings
- Derived types - Structs, Channels, ...

# Basics - Variable Declaration 

```go 

// Style - 1
var number int
number = 10

// Style - 2
number := 10

//Stype - 3
var number int = 10

```

# Basics - Conditionals

Conditionals are branching statements

- If, else if, else

```go
if condition {
    // Executes statements in this block if the condition satisfies
} else if this_condition {
    // Executes statemanets in this block if the condition satisfies 
} else {
    // Executes statements in this block only if all the conditions fail
}
```

# Basics - Loops

```go

// Basic for loop
sum := 0
for i := 1; i < 5; i++ {
    sum += i
}

fmt.Println(sum) // Prints?  

// While loop
n := 1
for n < 5 {
    n += 10
}

fmt.Println(n) // Prints?

// for each loop
strings := []string{"hello", "world"}
for i, s := range strings {
    // i is index, s is value at index 
    fmt.Println(i, s) // Prints? 
}

// Infinite loop
sum := 0
for {
    sum++ // repeated forever
}
fmt.Println(sum)

```

# Basics - Struct

- Collection of different types

```go 
type person struct {
    name string
    age  int
}
```

- Create an instance of struct
- Access values using the dot (.) operator

```go 
func main() {
    var p person
    
    fmt.Println(p)
    
    p.name = "s1mple"
    p.age = 22
    
    fmt.Println(p)
}
```

# Basics - Struct Methods - Value receiver

- Values are not modified, Since the instance is referred

```go 
func (p person) setDefaultValues() {

    fmt.Println(p) // Prints? 
    
    p.age = 30
    p.name = "niko"

}

func main() {
    var p person
    
    p.age = 22
    p.name = "s1mple"
    
    fmt.Println(p)
    
    p.setDefaultValues()
    
    fmt.Println(p)
}

```

# Basics - Struct Methods - Pointer receiver

- Values are modified, Since the instance is passed

```go 
func (p *person) setDefaultValues() {

    fmt.Println(p) // Prints? 
    
    p.age = 30
    p.name = "niko"

}

func main() {
    p := &person{}
    
    p.age = 22
    p.name = "s1mple"
    
    fmt.Println(p)
    
    p.setDefaultValues()
    
    fmt.Println(p)
}

```

# Basics - Internal Packages

- Included with Go binary

```go
package main

import (
    "fmt"
)

func main(){
    fmt.Println("Prints data")
}

```

# Basics - External packages 

- Use go get command to download the package

```bash 
go get -u github.com/gorilla/mux
```
- import and using the pkg 

```go
package main

import (
    "github.com/gorilla/mux"
)

func main(){
    r := mux.newrouter()
    // other statements
}

```

# Basics - Modules

- Used for dependency management 
- Similar to python virtual env
- Create a module using the below command - Creates go.mod file

```bash 
go mod init module_name
```
- Suggested module_name -> github.com/<username>/<repo_name> (Becomes easier to publish the pkg)
- Download external pkgs using go get in the directory where go.mod is initialized
- The downloaded pkgs are avaiable only for the go mod directory

# Basics - Using user defined packages

- Add the following to your go file to create a new pkg 

```go
package demo
```

- Each directory should have a single pkg
- Sub directories can have it's own pkg

# Basics - Importing a user defined pkg

- Pkg should be imported using go module name
- If the go module is named demo, the pkg is named mypkg and has the following dir structure 

```bash
.
├── go.mod
├── main.go
└── myPkg
    └── myPkg.go
```

```go 
import (
    "demo/mypkg" // importing user pkg
)
```

# Let's write some code

- Create a calculator pkg
- Should - Add, Sub, Multiply, Divide

# Q & A

Dude, Use Stackoverflow!

# Useful links

- Official Go Repo - https://github.com/golang/go
- Official Go Blog - https://go.dev/blog/
- Official Tour - https://tour.golang.org/welcome/1
- Tutorials - https://gobyexample.com/
- Book - Go in Action - https://www.amazon.in/Go-Action-William-Kennedy/dp/1617291781 
