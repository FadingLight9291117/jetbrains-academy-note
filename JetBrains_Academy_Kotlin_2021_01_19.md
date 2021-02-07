# :house:JetBrains Academy Koltin笔记

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
val fraction: Float = 1.51   			// 这样声明为Float，后面无需`f`
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



