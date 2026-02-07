# Interview Questions - 2026

## 📑 Quick Navigation
- [Caterpillar (Round 1)](#caterpillar-round-1)
- [Cloud Analogy](#cloud-analogy)
- [Caterpillar (Round 2)](#caterpillar-round-2)

---

# Caterpillar (Round 1)

**Date:** Monday, February 2, 2026  
**Time:** 11:54 AM

---

## Questions & Answers

### <span style="color: red;">1) What are all design patterns you have used in your career?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">Singleton, Factory Method, Abstract Factory Method</span>

---

### <span style="color: red;">2) What is the difference between Abstract Design pattern and Factory Design pattern?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">Factory Method ho ya Abstract Factory method ho, dono he case me agenda ye hai ki **Business Logic** and **Object creation** ko separate karna hai.

- **Factory Method:**  
  Ek Factory ek he tarike ka Object banati hai.  
  *Example:* Burger factory (Object creation part) hai wo sirf Burger Banaegi (Business Logic).

- **Abstract Factory:**  
  Ek Factory (Object Creation part) Multiple tarike ke Object banati hai.  
  *Example:* Meal factory (Object creation part) Burger and Meal dono banaegi (Business Logic).</span>

---

### <span style="color: red;">3) When do you use Semaphore and when to use Mutex? How can we decide?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">- **Mutex:** Is like a lock on the (critical section) shared resource. Jisko key milegi wahi room me jakr use kar paega.

- **Semaphore:** Is like a car parking system. Ek baar me e.g., 10 ya 100 cars park ho sakti hai. Count which decides how many threads can enter in critical section.</span>

---

### <span style="color: red;">4) Did you use the GDB tool for debugging?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">No</span>

---

# Cloud Analogy

---

## Questions & Answers

### <span style="color: red;">1) How would you detect duplicates in an array of 10 million integers with limited memory?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">
```cpp
// Online C++ compiler to run C++ program online
#include <iostream>
#include <vector>
#include <algorithm>
#include <iterator>
using namespace std;

int main() 
{
    std::vector<int> vec= { 10,11,12,10,15,14 ,13, 16,10,15};
    for( std::vector<int>:: iterator iter= vec.begin(); iter!=vec.end()  ; iter++)
    {
         int temp= *iter;
         
         std::vector<int>:: iterator itr2= iter +1 ;
         
         
         auto x= find( itr2  , vec.end() , temp);
         if(x != vec.end())
         {
           
            cout<<"There is duplicate of "<<*iter << " in"<<std::endl;
            copy(vec.begin() , vec.end() , ostream_iterator<int>(cout , " ") );
            cout<<endl;
            cout<<"Now delete both the value"<<*iter <<" and"<< *x <<std::endl;
            
            

            vec.erase(x);
            vec.erase(iter);
            
             copy(vec.begin() , vec.end() , ostream_iterator<int>(cout , " ") );
            cout<<endl;
        }
         
         else
         {
             
             cout<<"There is no duplicate of "<<*iter <<std::endl;
         }
         
         //std::cout<<*iter <<std::endl;
        
    }
    
    // Write C++ code here
    //std::cout << "Try programiz.pro";

    return 0;
}
```
</span>
---

### <span style="color: red;">7) What is bit set, bloom filter and caching in C++?</span>

**<span style="color: green;">Answer: I will learn</span>**  
<span style="color: green;"></span>

---

### <span style="color: red;">8) What is sync and async thread?</span>

**<span style="color: green;">Answer: I will learn</span>**  
<span style="color: green;"></span>

---

### <span style="color: red;">9) What are the types of mutex in C++?</span>

**<span style="color: green;">Answer: I will learn</span>**  
<span style="color: green;"></span>

---

# Caterpillar (Round 2)

---

## Questions & Answers

### <span style="color: red;">10) What is the use of initialization list?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">

Let's take one example and understand the difference:

**Example 1: Using Initialization List**
```cpp
class Complex{
public:
    int a, b;

    Complex(int x, int y): a(x), b(y)   // 'a' jab bann rha hai kisi class Complex k object
    {}                                   // ke liye tabhi wo 'x' se initialize ho ja rha hai.
};                                       // Yha 1 step me kaam ho rha hai.
```

**Example 2: Assignment in Constructor Body**
```cpp
class Complex{
public:
    int a, b;

    Complex(int x, int y)    // 'a' jab bann rha hai kisi Complex class ke object
    {                        // ke liye tabh wo kisi garbage value se initialize ho rha hai
        a = x;               // then 'x' se initialize ho ja rha hai.
        b = y;               // Yha 2 steps me kaam ho rha hai.
    }
};
```

**Advantage of Initialization List:**

When there is reference and const data member whose initialization is mandatory at the time of creation.

**1) Const Member:**
```cpp
class Complex{
public:
    const int a;

    Complex(int x): a(x) {}
};
```

**2) Reference Member:**
```cpp
class Complex{
public:
    int &a;

    Complex(int &x): a(x) {}
};
```

</span>

---

### <span style="color: red;">11) In a copy constructor, if no reference is kept how does it call an infinite loop?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">

**Without Reference (Causes Infinite Loop):**
```cpp
class Complex{
public:
    Complex() {}

    Complex(Complex x)  // No reference - causes infinite loop
    {}
};

int main()
{
    Complex c;
    Complex A(c);  // Complex X(c) -----> Complex X(c) -----> Complex X(c).....infinite times
                   // this again call CC    this again call CC
}
```

**With Reference (Correct Way):**
```cpp
class Complex{
    Complex(const Complex& x)  // Reference parameter - correct way
    {}
};

int main()
{
    Complex c;
    Complex A(c);  // reference of C will go to x.
}
```

</span>

---

### <span style="color: red;">12) What is the difference between Assignment and Copy Constructor?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">

**Copy Constructor:**
```cpp
Complex c(b);  // Copy constructor
```
Called on creation of a new object. 'c' jab exist kia usi time initialize bhi hua.

**Assignment Operator:**
```cpp
Complex c;
c = b;  // Assignment operator
```
Called for an assignment to an existing object. 'c' already exist kar rha tha line 1 me, 2nd line me initialize hua.

**Note:** `Complex c = b;` is also a Copy Constructor (Similar to `Complex c(b)`)

</span>

---

### <span style="color: red;">13) What is the difference between Abstract class and Interface?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">

- **Abstract Class:** Has at least one pure virtual function.
- **Interface:** Has all the functions as virtual.

</span>

---

### <span style="color: red;">14) Explain about Dynamic cast.</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;">

Dynamic cast happens only if a class is polymorphic (at least one virtual function).

**Ideal Scenario:**
```cpp
Parent* ptr = new Child;
Child* ch = dynamic_cast<Child*>(ptr);
```

**Question 1: What if ptr points to Parent object?**
```cpp
Parent* ptr = new Parent;
Child* ch = dynamic_cast<Child*>(ptr);
```
**Answer:** It will not give build error. But now `ch = nullptr`.  
**Why?** Because Runtime par ptr k pass child ke object ka reference hona chahiye. Otherwise it will give us nullptr and dynamic_cast is not successful.

**Question 2: Wrong cast type?**
```cpp
Parent* ptr = new Child;
Child* ch = dynamic_cast<Parent*>(ptr);  // Wrong!
```
**Answer:** Build time error. `Parent*>(ptr)` ki jagah `Child*>(ptr)` hona chahiye.

**Question 3: Upcast vs Downcast**

1) **Upcast (No error):**
```cpp
Child* ch = new Child;
Parent* ptr = ch;  // upcast - No error
```

2) **Downcast (Error):**
```cpp
Parent* ptr = new Child;
Child* ch = (ptr);  // downcast - Error (Can be solved by dynamic_cast)
```

</span>
