# daily-exercises

to be an active programmer  
(╯3╰)

___
## hiahiahia
    Integer.bitCount(m);
    
## BFS
    List<Double> result = new ArrayList<>();
    Queue<TreeNode> nodes = new LinkedList<>();

    nodes.add(root);
    while(!nodes.isEmpty())
    int n = nodes.size();


    if(node.left != null) nodes.offer(node.left);
    if(node.right != null) nodes.offer(node.right);

## SORT
    int[] nums
    Arrays.sort(nums);

## hashset
     HashSet<Integer> set = new HashSet<Integer>();


    Java HashSet class is used to create a collection that uses a hash table for storage. 
    It inherits the AbstractSet class and implements Set interface.

    The important points about Java HashSet class are:

    1. HashSet stores the elements by using a mechanism called hashing.
    2. HashSet contains unique elements only.

    UNIQUE ELEMENTS!!!!!!!!!!!!!!!!!!!!!!!

## String && Char
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

## construct an array list             
     List<Integer> list = new ArrayList<Integer>();

## hashmap
     Map<Integer, Integer> map = new HashMap<Integer, Integer>();
     if (map.containsKey(target - nums[i])) { 
     result[0] = map.get(target - nums[i]);
     

## [Priority Queue](https://www.javatpoint.com/java-priorityqueue)




## [java basic operators](https://www.tutorialspoint.com/java/java_basic_operators.htm)



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
## [java math operators and math class](http://tutorials.jenkov.com/java/math-operators-and-math-class.html)
    int abs1 = Math.abs(10);  // abs1 = 10 (absolute value)
                Math.abs(int)
                Math.abs(long)
                Math.abs(float)
                Math.abs(double)
    int min = Math.min(10, 20);
    int max = Math.max(10, 20);
    double random = Math.random();
## DFS
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
