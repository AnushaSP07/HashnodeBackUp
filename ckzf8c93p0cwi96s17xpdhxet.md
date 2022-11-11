# Search — Algorithm in JAVA

Hey Reader!!!!

You’re here and you want to know more about the technical concepts of Data Structure.

 Contents of the blog include:

- Linear Search
- Binary Search

Searching is the process of finding some particular element in the list. If the element is present in the list, then the process is called successful, and the process returns the location of that element. Otherwise, the search is called unsuccessful.

Linear Search and Binary Search are the two popular searching techniques in Data — structure.

# **Linear Search**

- Linear search algorithm is simply a search algorithm

- Linear search algorithm is also known as Sequential search algorithm

- In this type of algorithm, we simply search for an element or a value in a given array by traversing all the array elements sequentially from the beginning of the array till the desired element or value is found.

- In Linear Search, each element is matched to find the desired search element.

- If a match found, then location of the matched item is returned else it return null/-1


![linear.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644338281220/w9h03uvj6.png)

**Algorithm**


- Step 1: Start

- Step 2: check array size is greater than or equal to zero

- Step 3: if size of array is less than zero return -1 / false

- Step 4: iterate each element in the array

- Step 5: if the target element is equal to the element in the iteration

- Step 6: return the index or element or true.

**Example 1: To return the index of the target element**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391137028/NHDW-r01D.png)

**Example 2: To return element of the target value**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391156544/EYehYWyRl.png)

**Example 3:To search target value in String and return Boolean**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391186546/s_JrGrmow.png)

**Example 4: To search for an element in the given range**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391210034/rYly5WYPw.png)

**Example 5: To search in 2 — Dimensional array**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391234546/4uV4xApRQ.png)

# **Binary Search**

- Binary search is the search technique that works efficiently on sorted lists.

- To search an element into some list using binary search technique, we must ensure that the list must be sorted.

- Binary search follows divide and conquer approach, in which the list is divided into two halves and the element is compared with the middle element of the list.

- If the element is found, then index or element is returned
Otherwise we search into either of the halves of the elements

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391305471/80bIE3Psi.png)

**Algorithm:**

- Step 1: Start
- Step 2: Take the start index from 0, and end index as the length of the array
- Step 3: Check till the start element is less than or equal to end element
- Step 4: Find the middle element
- Step 5: check if target element is less than mid element, then end element will be previous of the mid element
- Step 6: Check if the target element is greater than mid element, then start element will be next of the current mid element
- Step 7: Otherwise return the mid element.

**Example 1: Binary search for sorted element**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391385377/W3rYc_cCN.png)

**Example 2: Binary search for unsorted elements
**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391422968/W8C0C8qfG.png)

**Example 3: Binary search for 2 — dimensional array**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391460033/RBfiCcWDb.png)

**Example 4: Binary search for the floor of the element**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391494576/H5a-2o634.png)

**Example 5: Binary search for the ceiling of the element**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644391536234/Lw1vNuTzv.png)

*Thank you for reading, Please like the article, It will encourage me to write more such articles. Do share your valuable suggestions, I appreciate your honest feedback!!*

