# Higher order function design

## implementing scala's map function
```scala
val nums = List(1, 2, 3)
def double(i: Int): Int = i * 2

// take a function and Int list as parameter
def map[A](f: (Int) => A, list: List[Int]): List[A] = {
  for {
    x <- list
  } yield f(x)
}

//using map function
map({ x => x * 2}, nums)
```



taken from [here](https://alvinalexander.com/scala/fp-book/how-to-write-scala-map-function)
