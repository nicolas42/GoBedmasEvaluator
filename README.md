# GoBedmasEvaluator

This is primarily to compare the C++, Go, and Rebol programming languages.

Rebol seems to be approximately 10X slower than the go version.

Surprisingly, the C++ version, written by a friend, seems to be slower than the Go version.

However if the cpp function is executed twice then the second run will be faster than Go

hinting that it may be the initial memory allocation that is the bottleneck for the CPP version.

In testing

Time taken in microseconds
Rebol	Golang	CPP
233		26		103

Terminal printout follows.

$ rebol Bedmas.r

0:00:00.000233

$ go run Bedmas.go

2234*((1+2)^2 + (3-5)*234/7)
= -129252.85714285714
26.413µs elapsed
37860 function calls possible per second

$ make Bedmas
c++     Bedmas.cpp   -o Bedmas
Bedmas.cpp:88:1: warning: control may reach end of non-void function
      [-Wreturn-type]
}
^
1 warning generated.
Morty:Bedmas Nick$ ./Bedmas
1*(2+3)^4
625 left
103 microseconds
