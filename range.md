# রেঞ্জ

`range` ব্যবহার করে কোনো স্লাইস, ম্যাপ বা চ্যানেল iterate করা যায়। যখন স্লাইস iterate করার জন্য `range` ব্যবহার করা হয় তখন প্রতিটি iterate এর জন্য `range` দুটো ভ্যালু রিটার্ন করে: ইনডেক্স এবং ঐ ইনডেক্সের ভ্যালুর কপি। একটা উদাহরণ দেখা যাক:

```go
package main

import "fmt"

var doubles = []int{0, 2, 4, 6, 8, 10}

func main() {
    for i, v := range doubles {
        fmt.Println("Double of", i, "is", v)
    }
}
```

এখানে `doubles` অ্যারেটি আইটারেট করার জন্য `range` ব্যবহার করা হয়েছে। প্রতিটি iteration এ `i` আর `v` তে থাকবে যথাক্রমে ইনডেক্স আর ওই ইনডেক্সের ভ্যালুর কপি। প্রোগ্রাম রান করলে এই আউটপুট পাওয়া যাবে:

```text
Double of 0 is 0
Double of 1 is 2
Double of 2 is 4
Double of 3 is 6
Double of 4 is 8
Double of 5 is 10
```

যদি ইনডেক্স বা ভ্যালুর দরকার না পড়ে তবে সেটা `_` ব্যবহার করে স্কিপ করা যায়। আবার শুধু ইনডেক্স চাইলে দ্বিতীয় ভ্যারিয়েবল লিখার প্রয়োজন পড়ে না। উদাহরণ দেখি:

```go
package main

import "fmt"

func main() {
    // ইন্টিজারের স্লাইস তৈরি করলাম
    doubles := make([]int, 6)

    // শুধু ইনডেক্স নিয়ে সেগুলোর সাথে দুই গুণ করছি
    for i := range doubles {
        doubles[i] = 2 * i
    }

    // এবার স্লাইসটির ভ্যালুগুলো দেখাচ্ছি, ইনডেক্স বাদ দেয়ার জন্য `_` ব্যবহার করছি
    for _, value := range doubles {
        fmt.Println(value)
    }
}
```

আউটপুট:

```text
0
2
4
6
8
10
```

