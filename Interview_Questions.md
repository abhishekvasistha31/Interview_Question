# Interview Questions - 2026

## 📑 Quick Navigation
- [Caterpillar (Round 1)](#caterpillar-round-1)
- [Cloud Analogy](#cloud-analogy)

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

**<span style="color: green;">Answer:I will learn</span>**  
<span style="color: green;"></span>

---

### <span style="color: red;">8) What is sync and async thread?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;"></span>

---

### <span style="color: red;">9) What are the types of mutex in C++?</span>

**<span style="color: green;">Answer:</span>**  
<span style="color: green;"></span>
    
