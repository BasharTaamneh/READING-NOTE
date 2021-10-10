# A beginner's guide to Big O Notation

* Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. ... In computer science, big O notation is used to classify algorithms according to how their run time or space requirements grow as the input size grows.
  
* used in Computer Science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm.

## O(1)

* O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

~~~
bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}
~~~

## O(N)

* O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. The example below also demonstrates how Big O favours the worst-case performance scenario; a matching string could be found during any iteration of the for loop and the function would return early, but Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

~~~
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}
~~~

## O(N²)

* O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N³), O(N⁴) etc.

~~~
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}
~~~

## O(2^N)

* O(2^N) denotes an algorithm whose growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential — starting off very shallow, then rising meteorically. An example of an O(2^N) function is the recursive calculation of Fibonacci numbers:

~~~
int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}
~~~

---

### Logarithms

---

* In mathematics, the logarithm is the inverse function to exponentiation. That means the logarithm of a given number x is the exponent to which another fixed number, the base b, must be raised, to produce that number x. In the simplest case, the logarithm counts the number of occurrences of the same factor in repeated multiplication; e.g. since 1000 = 10 × 10 × 10 = 103, the "logarithm base 10" of 1000 is 3, or log10 (1000) = 3. The logarithm of x to base b is denoted as logb (x), or without parentheses, logb x, or even without the explicit base, log x, when no confusion is possible, or when the base does not matter such as in big O notation.

* More generally, exponentiation allows any positive real number as base to be raised to any real power, always producing a positive result, so logb(x) for any two positive real numbers b and x, where b is not equal to 1, is always a unique real number y. More explicitly, the defining relation between exponentiation and logarithm is:

~~~
{\displaystyle \log _{b}(x)=y\ }{\displaystyle \log _{b}(x)=y\ } exactly if {\displaystyle \ b^{y}=x\ }{\displaystyle \ b^{y}=x\ } and {\displaystyle \ x>0}{\displaystyle \ x>0} and {\displaystyle \ b>0}{\displaystyle \ b>0} and {\displaystyle \ b\neq 1}{\displaystyle \ b\neq 1}.
~~~

**For example, log2 64 = 6, as 26 = 64.**

---
**a common example:**

* Binary search is a technique used to search sorted data sets. It works by selecting the middle element of the data set, essentially the median, and compares it against a target value. If the values match, it will return success. If the target value is higher than the value of the probe element, it will take the upper half of the data set and perform the same operation against it. Likewise, if the target value is lower than the value of the probe element, it will perform the operation against the lower half. It will continue to halve the data set with each iteration until the value has been found or until it can no longer split the data set.

* This type of algorithm is described as O(log N). The iterative halving of data sets described in the binary search example produces a growth curve that peaks at the beginning and slowly flattens out as the size of the data sets increase e.g. an input data set containing 10 items takes one second to complete, a data set containing 100 items takes two seconds, and a data set containing 1,000 items will take three seconds. Doubling the size of the input data set has little effect on its growth as after a single iteration of the algorithm the data set will be halved and therefore on a par with an input data set half the size. This makes algorithms like binary search extremely efficient when dealing with large data sets.
