# unordered_map : 



Here's how you can use `std::unordered_map` with some examples:

```cpp
#include <iostream>
#include <unordered_map>
#include <string>

int main() {
    // Example 1: Creating an unordered_map
    std::unordered_map<int, std::string> myMap;

    // Example 2: Inserting elements into the unordered_map
    myMap.insert({1, "One"});
    myMap.insert({2, "Two"});
    myMap.insert({3, "Three"});
    
    // Example 3: Accessing elements using operator[]
    std::cout << "Value associated with key 2: " << myMap[2] << std::endl;

    // Example 4: Iterating over the unordered_map
    std::cout << "Iterating over the unordered_map:" << std::endl;
    for (const auto& pair : myMap) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    // Example 5: Finding elements in the unordered_map
    auto it = myMap.find(3);
    if (it != myMap.end()) {
        std::cout << "Key 3 found with value: " << it->second << std::endl;
    } else {
        std::cout << "Key 3 not found" << std::endl;
    }

    // Example 6: Erasing elements from the unordered_map
    myMap.erase(2);

    // Example 7: Checking if an element exists in the unordered_map
    if (myMap.count(2) == 0) {
        std::cout << "Key 2 does not exist after erasing" << std::endl;
    }

    return 0;
}
```

Output:
```
Value associated with key 2: Two
Iterating over the unordered_map:
1: One
2: Two
3: Three
Key 3 found with value: Three
Key 2 does not exist after erasing
```

These examples cover creating an unordered map, inserting elements, accessing elements using `operator[]`, iterating over the map, finding elements, erasing elements, and checking if an element exists.

----------------------------------------------------------------------------------------------------------------------------
# ordered map (`std::map`)


In C++, `std::map` is a sorted associative container that contains key-value pairs with unique keys. Here are some of the most commonly used member functions and methods of `std::map`:

1. **insert()**: Inserts an element into the map.
2. **erase()**: Removes an element from the map.
3. **find()**: Searches for an element with a given key.
4. **size()**: Returns the number of elements in the map.
5. **empty()**: Checks if the map is empty.
6. **begin()**: Returns an iterator to the beginning of the map.
7. **end()**: Returns an iterator to the end of the map.
8. **lower_bound()**: Returns an iterator to the first element not less than the given key.
9. **upper_bound()**: Returns an iterator to the first element greater than the given key.
10. **equal_range()**: Returns a range containing all elements with the given key.


Here's an example demonstrating the usage of these methods:

```cpp
#include <iostream>
#include <map>

int main() {
    std::map<int, std::string> myMap;

    // Inserting elements into the map
    myMap.insert(std::make_pair(1, "One"));
    myMap.insert(std::make_pair(2, "Two"));
    myMap.insert(std::make_pair(3, "Three"));

    // Accessing elements
    std::cout << "Value associated with key 2: " << myMap[2] << std::endl;

    // Erasing an element
    myMap.erase(2);

    // Finding an element
    auto it = myMap.find(2);
    if (it != myMap.end())
        std::cout << "Element found: " << it->second << std::endl;
    else
        std::cout << "Element not found" << std::endl;

    // Checking size and emptiness
    std::cout << "Size of the map: " << myMap.size() << std::endl;
    std::cout << "Is map empty? " << (myMap.empty() ? "Yes" : "No") << std::endl;

    // Iterating over the map
    std::cout << "Map elements: ";
    for (auto& pair : myMap) {
        std::cout << "{" << pair.first << ": " << pair.second << "} ";
    }
    std::cout << std::endl;

    // Using lower_bound and upper_bound
    auto lower = myMap.lower_bound(1); // Iterator to the element with key 1
    auto upper = myMap.upper_bound(3); // Iterator to the element with key 3
    std::cout << "Elements between keys 1 and 3: ";
    for (auto it = lower; it != upper; ++it) {
        std::cout << "{" << it->first << ": " << it->second << "} ";
    }
    std::cout << std::endl;

    return 0;
}
```

This example demonstrates various methods of `std::map` such as insertion, erasure, finding elements, checking size and emptiness, iterating over elements, and using `lower_bound` and `upper_bound` for range-based operations.

----------------------------------------------------------------------------------------------------------------------------

# Stack

Stacks are commonly used in various types of data structure and algorithm (DSA) problems where you need to keep track of elements in a last-in-first-out (LIFO) manner.

We can use stacks for : 
1. Next greater element
2. Next smaller element
3. Previous greater element
4. Previous smaller element


----------------------------------

`Monotonic stack` is a specialized stack data structure used in problems where you need to find the next greater or next smaller element for each element in an array, maintaining a certain monotonic order (either increasing or decreasing).

In simple words, a monotonic stack is a stack that maintains either a strictly increasing or strictly decreasing order of elements. The key idea is that elements are pushed onto or popped from the stack in such a way that it always preserves the desired monotonic order. This property enables efficient computation of the next greater or next smaller element for each element in an array.

For example, in the problem where you need to find the next greater element for each element in an array, you can use a monotonic stack to efficiently find the solution by maintaining a strictly decreasing order of elements in the stack. Similarly, if you need to find the next smaller element, you would maintain a strictly increasing order of elements in the stack.

Monotonic stacks are particularly useful in problems involving finding the nearest greater or smaller element for each element in an array, and they often lead to efficient solutions with O(n) time complexity.

----------------------------------------------------------------------------------------------------------------------------

# std::set :

In C++, the `std::set` container from the Standard Template Library (STL) is a sorted associative container that contains unique elements only. Here are some of the most commonly used member functions and methods of `std::set`:

1. **insert()**: Inserts an element into the set.
2. **erase()**: Removes an element from the set.
3. **find()**: Searches for an element in the set.
4. **size()**: Returns the number of elements in the set.
5. **empty()**: Checks if the set is empty.
6. **begin()**: Returns an iterator to the beginning of the set.
7. **end()**: Returns an iterator to the end of the set.
8. **lower_bound()**: Returns an iterator to the first element not less than the given key.
9. **upper_bound()**: Returns an iterator to the first element greater than the given key.
10. **equal_range()**: Returns a range containing all elements with the given key.

Here's an example demonstrating the usage of these methods:

```cpp
#include <iostream>
#include <set>

int main() {
    std::set<int> mySet;

    // Inserting elements into the set
    mySet.insert(3);
    mySet.insert(1);
    mySet.insert(2);
    mySet.insert(2); // Ignored because 2 is already in the set

    // Displaying elements
    std::cout << "Set elements: ";
    for (auto& elem : mySet) {
        std::cout << elem << " ";
    }
    std::cout << std::endl;

    // Erasing an element
    mySet.erase(2);

    // Finding an element
    auto it = mySet.find(2);
    if (it != mySet.end())
        std::cout << "Element found: " << *it << std::endl;
    else
        std::cout << "Element not found" << std::endl;

    // Checking size and emptiness
    std::cout << "Size of the set: " << mySet.size() << std::endl;
    std::cout << "Is set empty? " << (mySet.empty() ? "Yes" : "No") << std::endl;

    // Iterating over the set
    std::cout << "Set elements: ";
    for (auto it = mySet.begin(); it != mySet.end(); ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    // Using lower_bound and upper_bound
    auto lower = mySet.lower_bound(1); // Iterator to the element with key 1
    auto upper = mySet.upper_bound(3); // Iterator to the element with key 3
    std::cout << "Elements between keys 1 and 3: ";
    for (auto it = lower; it != upper; ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

This example demonstrates various methods of `std::set` such as insertion, erasure, finding elements, checking size and emptiness, iterating over elements, and using `lower_bound` and `upper_bound` for range-based operations.

-----------------------------------

# std::unordered_set:

In C++, the `std::unordered_set` container from the Standard Template Library (STL) is an unordered associative container that contains unique elements only. Here are some of the most commonly used member functions and methods of `std::unordered_set`:

1. **insert()**: Inserts an element into the unordered set.
2. **erase()**: Removes an element from the unordered set.
3. **find()**: Searches for an element in the unordered set.
4. **size()**: Returns the number of elements in the unordered set.
5. **empty()**: Checks if the unordered set is empty.
6. **begin()**: Returns an iterator to the beginning of the unordered set.
7. **end()**: Returns an iterator to the end of the unordered set.
8. **bucket_count()**: Returns the number of buckets in the unordered set.
9. **bucket_size()**: Returns the number of elements in a specific bucket.
10. **load_factor()**: Returns the average number of elements per bucket.
11. **max_load_factor()**: Sets or gets the maximum load factor of the unordered set.

Here's an example demonstrating the usage of these methods:

```cpp
#include <iostream>
#include <unordered_set>

int main() {
    std::unordered_set<int> mySet;

    // Inserting elements into the unordered set
    mySet.insert(3);
    mySet.insert(1);
    mySet.insert(2);
    mySet.insert(2); // Ignored because 2 is already in the set

    // Displaying elements
    std::cout << "Unordered set elements: ";
    for (auto& elem : mySet) {
        std::cout << elem << " ";
    }
    std::cout << std::endl;

    // Erasing an element
    mySet.erase(2);

    // Finding an element
    auto it = mySet.find(2);
    if (it != mySet.end())
        std::cout << "Element found: " << *it << std::endl;
    else
        std::cout << "Element not found" << std::endl;

    // Checking size and emptiness
    std::cout << "Size of the unordered set: " << mySet.size() << std::endl;
    std::cout << "Is unordered set empty? " << (mySet.empty() ? "Yes" : "No") << std::endl;

    // Iterating over the unordered set
    std::cout << "Unordered set elements: ";
    for (auto it = mySet.begin(); it != mySet.end(); ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    // Get the number of buckets and elements in each bucket
    std::cout << "Number of buckets: " << mySet.bucket_count() << std::endl;
    for (size_t i = 0; i < mySet.bucket_count(); ++i) {
        std::cout << "Bucket " << i << " has " << mySet.bucket_size(i) << " elements." << std::endl;
    }

    // Get load factor
    std::cout << "Load factor: " << mySet.load_factor() << std::endl;

    // Set or get the maximum load factor
    mySet.max_load_factor(0.7);
    std::cout << "Maximum load factor: " << mySet.max_load_factor() << std::endl;

    return 0;
}
```

This example demonstrates various methods of `std::unordered_set` such as insertion, erasure, finding elements, checking size and emptiness, iterating over elements, and accessing properties such as bucket count, bucket size, load factor, and maximum load factor.


### Explanation:

- Both `std::set` and `std::unordered_set` support operations like `insert`, `erase`, and `find`.
- The main difference lies in the underlying data structure:
  - `std::set` is implemented as a balanced binary search tree (usually Red-Black Tree), which provides O(log n) time complexity for insert, erase, and find operations.
  - `std::unordered_set` is implemented as a hash table, providing O(1) average time complexity for insert, erase, and find operations.
- Because of hashing, the elements in `std::unordered_set` are not ordered, while `std::set` maintains elements in sorted order.
- The examples provided demonstrate basic usage of these operations.
