# :house:JetBrains Academy Kotlin笔记

## :calendar:2021.01.29

### :point_right:关于数字类型的类型推断

```kotlin
val twoMillion1 = 2_000_000L			// 可以这样声明一个Long
val twoMillion2: Long = 2_000_000		// 也可以这样声明Long
val bigNumber = 1_000_000_000_000_000 	// 自动判断为Long

// 而Short和Byte只能这样
val shortNumber: Short = 15
val byteNunmber: Byte = 15

// 浮点数也类似
val pi = 3.14159						// 推断为Double
val e = 2.71828f						// 声明为Float
// val fraction: Float = 1.51   			// 这样声明为Float，后面无需`f, 错误的
```



### :point_right:获取一个类型的最大最小值和字节数、比特数

```kotlin
Int.Max_VALUE	// Int类型的最大值
Int.MIN_VALUE	// Int类型的最小值

Int.SIZE_BYTES	// Int类型的字节数
Int.SIZE_BITS	// Int类型的比特数
```



### :point_right:关于`..`

```kotlin
for (i in 0..10) {	// 这里输出的时0到10，而不是0到9
    print(i)
}
```



### :point_right:Kotlin的标准输入

> 第一次完全了解Kotlin的标准输入

```kotlin
val line = readLine()!!	// 强制非空，为空则为""

val number = readLine()!!.toInt() // 输入数字，其他类似
```

:thinking:使用`java`的`Sacnner`

```kotlin
val scanner = Scanner(System.`in`)
val line = scanner.nextLine() // read a whole line, i.e. "Hello, Kotlin"
val num = scanner.nextInt()   // read a number, i.e. 123
val string = scanner.next()   // read a string, i.e. "Hello"
```

Here is an example of correct input data:

```java
Hello, Kotlin
123 Hello
```

This input example is also correct:

```java
Hello, Kotlin
123
Hello
```

---

```kotlin
val scanner = Scanner(System.`in`) // reads data

val num1 = scanner.nextInt() // reads the first number
val num2 = scanner.nextInt() // reads the second number

println(num2) // prints the second number
println(num1) // prints the first number
```

**Example1**

Input:

```java
11 12
```

Output:

```java
12
11
```

**Example 2**

Input:

```java
301
402
```

Output:

```java
402
301
```



## :calendar:2021.02.09

### :key:还是数字类型转换

>To sum up, if you have an expression with different numeric types, use these rules to know the type of the result:
>
>1. If either operand is of type `Double`, the result is `Double`.
>2. Otherwise, if either operand is of type `Float`, the result is `Float`.
>3. Otherwise, if either operand is of type `Long`, the result is `Long`.
>4. Otherwise, the result is `Int`.
>
>Type conversion does not occur when a value is put into the variable. For example, `val longValue: Long = 10.toInt()` is incorrect, because 10 is `Int` and `longValue` requires `Long` type.



## :calendar:2021.02.25

### :point_right:关于`range`

`...`是左右都是闭区间

```kotlin
println(5 in 5..15)  // true
println(15 in 5..15) // true
```

:key:如果要排除右区间

```kotlin
val withinExclRight = c in a..b - 1 // a <= c && c < b
```

还有一些关于字符的

```kotlin
println('b' in 'a'..'c') // true
println('k' in 'a'..'e') // false

println("hello" in "he".."hi") // true
println("abc" in "aab".."aac") // false
```

### :point_right:多维数组

多维数组可以包含不同类型

```kotlin
val arrayOfString2D = arrayOf(
    arrayOf("Practice", "makes", "perfect"),
    arrayOf(1, 2)
)
```

也可以包含不同长度

```kotlin
val array2D = arrayOf(
    arrayOf(0),
    arrayOf(1, 2),
    arrayOf(3, 4, 5))
```

### :key:Repeating 块

```kotlin
repeat(n) {
    // statements
}
```

### :key:`for`循环

只有整型(IntRange, LongRange, CharRange)可以迭代。

比如

```kotlin
for (i in 1..4) print(i)
```

但是

```kotlin
for (i in 'z' downTo 'e' step 200) {}
```

就不行