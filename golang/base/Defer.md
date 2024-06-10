откладывает выполнение функции до тех пор, пока остальные функции в том же контексте не выполнятся 

```go
package main

import "fmt"

func main() {
	defer fmt.Println("world")

	fmt.Println("hello")
	fmt.Println("hello")
	fmt.Println("hello")
}

hello
hello
hello
world
```

все такие конструкции складываются в стек 

```go
package main

import "fmt"

func main() {
	fmt.Println("counting")

	for i := 0; i < 10; i++ {
		defer fmt.Println(i)
	}

	fmt.Println("done")
}

counting
done
9
8
7
6
5
4
3
2
1
0
```