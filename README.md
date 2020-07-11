# Slice tricks

Did you forget how to delete an element from the slice?
Don't go to https://github.com/golang/go/wiki/SliceTricks anymore to figure that out...
Use slicetricks package instead!

## I want to play

 There you go https://go2goplay.golang.org/p/y1dkGPLVEe9
 ```
 func main() {
	fmt.Println(Copy([]int{1,2,3}))	
	fmt.Println(Copy([]string{"a", "b", "c"}))
	
	fmt.Println(Cut([]int{1,2,3}, 0, 2))
	fmt.Println(Cut([]string{"a", "b", "c"}, 0, 2))
	
	fmt.Println(Delete([]int{1,2,3}, 0))
	fmt.Println(Delete([]string{"a", "b", "c"}, 0))
	
	fmt.Println(Filter([]int{1,2,3,4,5}, func(x int) bool {return x > 2 }))
	
	fmt.Println(Deduplicate([]string{"a", "b", "c", "d", "e", "f", "a", "f"}))
	
	fmt.Println(Batch([]bool{true, false, true, false, true, true, false}, 3))
	
	haystack := []string{"a", "b", "c", "d", "e"} // [a b c d e]
	haystack = MoveToFront("c", haystack)         // [c a b d e]
	fmt.Println(haystack)
	haystack = MoveToFront("f", haystack)         // [f c a b d e]
	fmt.Println(haystack)

	fmt.Println(SlidingWindow(2, []string{"a", "b", "c", "d", "e"}))
}
```

## Problems with the package
1. Go generics not official yet
2. Panics a lot if you put wrong indices
3. Code coverage 0%

## TODO
1. Wait for generics to be official
2. Increase code coverage up to 100%
3. Test edge cases.