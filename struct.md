`struct` দিয়ে আমরা নতুন ইউজার ডিফাইনড ডাটা টাইপ তৈরি করতে পারি। `bool` , `int`, `string` , `byte` ইত্যাদি যে বেসিক ডাটা টাইপ গুলো আছে এদের ব্যবহার করে নতুন ডাটা টাইপ বানালে কোড মেইন্টেইন করা সহজ হয়। 
যেমন আমরা যদি নতুন একটি ডাটা টাইপ বানাতে চাই যার নাম হবে `Point` । `Point` এর দুইটা `int` টাইপের ডাটা ফিল্ড আছে `x` এবং `y` । তাহলে `struct`  ব্যবহার করে `Point` বানাতে হলে লিখতে হবে 
  ```go
package main

import "fmt"

//এখানে Point টাইপ এর নতুন ডাটা টাইপ ডিফাইন করা হল 
type Point struct {    
x int
y int
}

func main() {

   // এখানে Point টাইপের variable যার নাম mypoint ডিক্লেয়ার করা হল আর x = 10 এবং y = 20 দিয়ে initialize করা হল
    mypoint := Point{10,20}
    fmt.Println("mypoint.x = ",mypoint.x," mypoint.y = ",mypoint.y)
    
    }
}
``` 
ইউজার ডিফাইন্ড ডাটা টাইপের ডাটা ফিল্ড গুলোকে এক্সেস করতে পারব  `.` অপারেটর দিয়ে । যেমন উপরে `mypoint` এর x এবং y ফিল্ড কে আমরা এক্সেস করছি `mypoint.x` এবং `mypoint.y` দিয়ে। 
