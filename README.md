# Java notes :relaxed:

### Table of Contents
- :see_no_evil:  
- [ArrayList](#arraylist)  
- [LinkedList](#linkedlist)
- [Stack](#stack)
- [Vector](#vector)
- :hear_no_evil:  
- [HashSet](#hashset)  
- [LinkedHashSet](#linkedhashset)  
- [TreeSet](#treeset) 
- :speak_no_evil:  
- [Priority Queue](#priority-queue)  
- [Array Deque](#arraydeque)  
- [LinkedList DeQue](#linkedlist-deque)  
- :baby:  
- [HashMap](#hashmap)  
- [HashLinkedMap](#hashlinkedmap)  
- [HashTable](#hashtable)  
- [TreeMap](#treemap)  
- :angel:  
- [BFS](#bfs)  
- [DFS](#dfs)  
- [String and Char](#string--char)  
- [Basic Operators](#basic-operators)  
- [Math Operators](#math-operators)  
- [Sorting algorithems](#sorting-algorithems)
- [Balls into Bins problem](#balls-into-bins-problem)

<img src="https://cdncontribute.geeksforgeeks.org/wp-content/uploads/java-collection.jpg" width="800" />

___ 
###  ArrayList           
    //the size can increase if collection grows or shrunk if objects are removed from the collection.
    public static void main(String[] args) 
                        throws IOException 
    { 
        int n = 5; 
        ArrayList<Integer> arrli = new ArrayList<Integer>(n); 
 
        for (int i=1; i<=n; i++) 
            arrli.add(i); // Appending the new element at the end of the list 
  
        System.out.println(arrli); 
        
        arrli.remove(3); // Remove element at index 3 

        System.out.println(arrli); 

        for (int i=0; i<arrli.size(); i++) 
            System.out.print(arrli.get(i)+" "); 
    } 
    
    output:
    [1, 2, 3, 4, 5]
    [1, 2, 3, 5]
    1 2 3 5 

___
### LinkedList
<img src="https://www.geeksforgeeks.org/wp-content/uploads/gq/2013/03/Linkedlist.png" width="600" />

    //Like arrays, Linked List is a linear data structure. Unlike arrays, linked list elements are not stored at the contiguous location 
    //LinkedList can be represented as a class and a Node as a separate class. 
    class LinkedList { 
	Node head; // head of list 

	/* Linked list Node*/
	class Node { 
		int data; 
		Node next; 

		// Constructor to create a new node 
		// Next is by default initialized 
		// as null 
		Node(int d) { data = d; next = null;} 
	} 
___
### Stack

    // last-in-first-out
    // Stack is a subclass of Vector.
    
    Object push(Object element) : Pushes an element on the top of the stack.
	Object pop() : Removes and returns the top element of the stack. An ‘EmptyStackException’ exception is thrown if we call pop() when the invoking stack is empty.
	Object peek() : Returns the element on the top of the stack, but does not remove it.
	boolean empty() : It returns true if nothing is on the top of the stack. Else, returns false.
	int search(Object element) : It determines whether an object exists in the stack. If the element is found, it returns the position of the element from the top of the stack. Else, it returns -1.


    // Pushing element on the top of the stack 
    static void stack_push(Stack<Integer> stack){ 
        for(int i = 0; i < 5; i++){ 
            stack.push(i); 
        } 
    } 
      
    // Popping element from the top of the stack 
    static void stack_pop(Stack<Integer> stack){ 
        System.out.println("Pop :"); 
        for(int i = 0; i < 5; i++) { 
            Integer y = (Integer) stack.pop(); 
            System.out.println(y); 
        } 
    } 
  
    // Displaying element on the top of the stack 
    static void stack_peek(Stack<Integer> stack) { 
        Integer element = (Integer) stack.peek(); 
        System.out.println("Element on stack top : " + element); 
    } 
      
    // Searching element in the stack 
    static void stack_search(Stack<Integer> stack, int element) { 
        Integer pos = (Integer) stack.search(element); 
        if(pos == -1) 
		System.out.println("Element not found"); 
        else
		System.out.println("Element is found at position " + pos);
	}
	
	public static void main (String[] args){ 
		Stack<Integer> stack = new Stack<Integer>(); 

		stack_push(stack); 
		stack_pop(stack); 
		stack_push(stack); 
		stack_peek(stack); 
		stack_search(stack, 2); 
		stack_search(stack, 6); 
	} 

___
### Vector

	https://www.geeksforgeeks.org/java-util-vector-class-java/
	Vector implements a dynamic array that means it can grow or shrink as required. 
	Like an array, it contains components that can be accessed using an integer index
	They are very similar to ArrayList but Vector is synchronised and have some legacy method 
	which collection framework does not contain.
	
	Constructor:

	Vector(): Creates a default vector of initial capacity is 10.
	Vector(int size): Creates a vector whose initial capacity is specified by size.
	Vector(int size, int incr): Creates a vector whose initial capacity is specified by size 
		and increment is specified by incr. It specifies the number of elements to allocate 
		each time that a vector is resized upward. (If increment is specified, Vector will 
		expand according to it in each allocation cycle but if increment is not specified 
		then vector’s capacity get doubled in each allocation cycle.)
	Vector(Collection c): Creates a vector that contains the elements of collection c.
	
	class Vector_demo { 
	    public static void main(String[] arg) 
	    { 

		// create default vector 
		Vector v = new Vector(); 

		v.add(1); 
		v.add(2); 
		v.add("geeks"); 
		v.add("forGeeks"); 
		v.add(3); 

		System.out.println("Vector is " + v); 
	    } 
	}
	
	//Vector is: [1, 2, geeks, forGeeks, 3]

___      
### HashSet
   
	https://www.geeksforgeeks.org/hashset-in-java/
    Java HashSet class is used to create a collection that uses a hash table for storage. 
    It inherits the AbstractSet class and implements Set interface.  
    
    The important points about Java HashSet class are:  
    1. HashSet is implemented using a hash table 
    2. HashSet contains unique elements only.  
	3. Elements are not ordered.    
	4. NULL elements are allowed in HashSet.  
	5. The add, remove, and contains method have constant time complexity O(1).
	
    Constructors:
	HashSet h = new HashSet();  // HashSet<Integer> h = new HashSet<Integer>();  //Default initial capacity is 16 and default load factor is 0.75.
	HashSet h = new HashSet(int initialCapacity); //default loadFactor of 0.75
	HashSet h = new HashSet(int initialCapacity, float loadFactor);
	HashSet h = new HashSet(Collection C);
    
     public static void main(String[]args) 
    { 
        HashSet<String> h = new HashSet<String>(); 
  
        // Adding elements into HashSet usind add() 
        h.add("India"); 
        h.add("Australia"); 
        h.add("South Africa"); 
        h.add("India");// adding duplicate elements 
  
        // Displaying the HashSet 
        System.out.println(h); 
        System.out.println("List contains India or not:" + 
                           h.contains("India")); 
  
        // Removing items from HashSet using remove() 
        h.remove("Australia"); 
        System.out.println("List after removing Australia:"+h); 
  
        // Iterating over hash set items 
        System.out.println("Iterating over list:"); 
        Iterator<String> i = h.iterator(); 
        while (i.hasNext()) 
            System.out.println(i.next()); 
    } 
    
    Output:
   	[South Africa, Australia, India]
	List contains India or not:true
	List after removing Australia:[South Africa, India]
	Iterating over list:
	South Africa
	India
	
	Methods:
	boolean add(E e) //Used to add the specified element if it is not present, if it is present then return false.
	void clear() //Used to remove all the elements from set.
	boolean contains(Object o) //Used to return true if an element is present in set.
	boolean remove(Object o) //Used to remove the element if it is present in set.
	Iterator iterator() //Used to return an iterator over the element in the set.
	boolean isEmpty() //Used to check whether the set is empty or not. Returns true for empty and false for non-empty condition for set.
	int size() //Used to return the size of the set.
	Object clone() //Used to create a shallow copy of the set.

___
### LinkedHashSet

    //TODO

___
### TreeSet

    //TODO

___ 
### Priority Queue
    https://www.javatpoint.com/java-priorityqueue

___
### ArrayDeque

    //TODO
___
### LinkedList Deque

    //TODO
___ 
### HashMap

    A HashMap store items in "key/value" pairs, and you can access them by a key (e.g. a String). 
    (有点像python的dictionary)

    Create HashMap Obj:
        import java.util.HashMap; // import the HashMap class
        HashMap<String, String> xxx = new HashMap<String, String>();
        HashMap<String, Integer> xxx= new HashMap<String, Integer>();

    Add keys and values:
        xxx.put("England", "London");

    Access an Item:
        xxx.get("England");

    Remove an Item:
        xxx.remove("England");

    Remove all items:
        xxx.clear();

    Hashmap Size:
        xxx.size();

    Loop through a HashMap:
        for (String i : xxx.keySet()) {
          System.out.println(i);
        }
        for (String i : xxx.values()) {
          System.out.println(i);
        }
        for (String i : xxx.keySet()) {
          System.out.println("key: " + i + " value: " + xxx.get(i));
        }
    
    An example:
        Map<Integer, Integer> map = new HashMap<Integer, Integer>();
        if (map.containsKey(target - nums[i])) { 
            result[0] = map.get(target - nums[i]);
        }

___
### HashLinkedMap

    //TODO
___
### HashTable

    //TODO
___
### TreeMap
    //TODO
___ 
### BFS
    List<Double> result = new ArrayList<>();
    Queue<TreeNode> nodes = new LinkedList<>();

    nodes.add(root);
    while(!nodes.isEmpty())
    int n = nodes.size();

    if(node.left != null) nodes.offer(node.left);
    if(node.right != null) nodes.offer(node.right);
    
___ 
### DFS
    pre-order traversal 
        Check if the current node is empty / null.
        Display the data part of the root (or current node).
        Traverse the left subtree by recursively calling the pre-order function.
        Traverse the right subtree by recursively calling the pre-order function.

    in-order traversal
        Check if the current node is empty / null.
        Traverse the left subtree by recursively calling the in-order function.
        Display the data part of the root (or current node).
        Traverse the right subtree by recursively calling the in-order function.

    post-order traversal
        Check if the current node is empty / null.
        Traverse the left subtree by recursively calling the post-order function.
        Traverse the right subtree by recursively calling the post-order function.
        Display the data part of the root (or current node).

___ 
### String && Char
    String.valueOf(i)
    String[] keyboard = {"QWERTYUIOP","ASDFGHJKL","ZXCVBNM"};
    
    String s
    String[] parts = s.split(" ");
    
    char[] arr = s.toCharArray();
    
    System.out.println(Character.isUpperCase('c'));
    false
        
    String s;    
    int index=s.indexOf('a');
    
    //delete a char in a string
    String s;
    s = s.substring(0, index) + s.substring(index + 1);

    


___ 
### basic operators
    https://www.tutorialspoint.com/java/java_basic_operators.htm

    **Assume integer variable A holds 10 and variable B holds 20

    +(addition)         A+B gives 30
    -(subtraction)      A-B gives -10
    *(multiplication)   A*B gives 200
    /(division)         B/A gives 2
    %(modulus)          B%A gives 0
    ++(increment)       B++ gives 21
    --(decrement)       B-- gives 19


    ==(equal to)        A==B is not true
    !=(not equal to)    A!=B is true
    >(greater than)     A>B is not true
    <(less than)        A<B is true
    >=(greater than or equal to)
    <=(less than or equal to)

    =====================================================================
    the bitwise operators
    =====================================================================
    **assume a=60 and b=13
    a = 0011 1100
    b = 0000 1101

    a&b = 0000 1100
    a|b = 0011 1101
    a^b = 0011 0001             0 ^ N = N        N ^ N = 0
    ~a  = 1100 0011
    <<(left shift)               a<<2 will give 1111 0000
    >>(right shift)              a>>2 will give      1111
    >>>(zero fill right shift)   a>>>2 will give 0000 1111    


    ======================================================================
    logical operators
    ======================================================================
    assume A holds true and B holds false
    &&(logical and)  A&&B is false
    ||(logical or)   A||B is true
    ! (logical not)  !(A&&B) is true
___     
### math operators

    http://tutorials.jenkov.com/java/math-operators-and-math-class.html
    int abs1 =  Math.abs(10);  // abs1 = 10 (absolute value)
                Math.abs(int)
                Math.abs(long)
                Math.abs(float)
                Math.abs(double)
    int min = Math.min(10, 20);
    int max = Math.max(10, 20);
    double random = Math.random();
___ 
### Sorting algorithems

#### Arrays.sort in java
    https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html
    e.g.
        import java.util.Arrays; 
        int[] nums
        Arrays.sort(nums);
#### Sorting algorithms
    https://www.geeksforgeeks.org/sorting-algorithms/#algo

#### Sorting algorithms time complexity
    http://bigocheatsheet.com/
___ 
### Balls into Bins problem

        Give m balls and n bins. Find out how many ways to assign balls to bins. Notice the buckets has no order. Like (1,2,3) and (3,2,1) are considered the same. 
        eg, m = 3, n = 2, return 2. (1, 2) and (3, 0)


        int assignBalls(int m, int n) {
                if (m == 0 || n == 1) {
                    return 1;
                }
                if (n > m) {
                    return assignBalls(m, m);
                } else {
                    return assignBalls(m, n - 1) + assignBalls(m - n, n);
                }
            }
___ 
## TODO
### Binary Search Tree
### olymorphism, inheritance, encapsulation, etc
