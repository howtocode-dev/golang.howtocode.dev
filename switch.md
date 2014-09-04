# সুইচ

সুইচ স্টেটমেন্ট এর ব্যাসিক এক্সাম্পল দেখে নেই:

```go
	i := 2
    fmt.Print("write ", i, " as ")
    switch i {
    case 1:
        fmt.Println("one")
    case 2:
        fmt.Println("two")
    case 3:
        fmt.Println("three")
    }
```

এখানে আমার সুইচ স্টেটমেন্টকে একটি এক্সপ্রেশন দিয়ে দেই । এরপর সেই এক্সপ্রেশনের ভ্যালুর সাথে আমাদের কেইসগুলো ম্যাচ করিয়ে দেখি যে শর্ত মেলে কিনা । যে সব কেইস ম্যাচ করে সেইসব কেইসের সাথে থাকা কোড ব্লক রান করে । 

আমরা কেইস স্টেটমেন্ট এ কমা দিয়ে একাধিক কন্ডিশন দিয়ে দিতে পারি, যেমন: 

```go

package main

import "fmt"
import "time"

func main() {
    switch time.Now().Weekday() {
    case time.Saturday, time.Sunday:
        fmt.Println("it's the weekend")
    default:
        fmt.Println("it's a weekday")
    }
}
```

তবে সুইচ স্টেটমেন্ট এর পাশাপাশি কেইস স্টেটমেন্ট এও আমরা ডাইনামিক এক্সপ্রেশন ব্যবহার করতে পারি । আমরা চাইলে সুইচ স্টেটমেন্টে কোন এক্সপ্রেশন পাস নাও করতে পারি, সেক্ষেত্রে সুইচ কে ইফ-এলস এর মত করে ব্যবহার করা যায় -  

```go
package main

import "fmt"
import "time"

func main() {
	t := time.Now()
	switch {
	case t.Hour() < 12:
		fmt.Println("it's before noon")
	default:
		fmt.Println("it's after noon")
	}
}

```

এখানে দেখুন `case t.Hour() < 12` ডাইনামিক এক্সপ্রেশন । এবং আমরা সুইচ স্টেটমেন্টে `t` কে পাস না করে, কেইস স্টেটমেন্টে এসে সরাসরি `t.Hour()` ব্যবহার করেছি । জিনিসটা ইফ-এলস দিয়ে আমরা এভাবে করতে পারতাম: 

```go
package main

import "fmt"
import "time"

func main() {
	t := time.Now()
	if t.Hour() < 12 {
		fmt.Println("it's before noon")
	}

}
```