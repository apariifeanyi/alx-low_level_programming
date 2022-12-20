A pointer is a variable which contains a memory address.



Types and memory

Every time you declare a variable, the computer will reserve memory for this variable. The memory reserved will then store the value of the variable.

Depending on the type of the variable, the computer will reserve more or less memory. The size of each type is generally defined in bytes (1 byte = 8 bits, each bit being 0 or 1). The sizes of the types also depend on the computer you are using. Here are the sizes of the most common types on most 64-bit Linux machines:



char -> 1 byte

int -> 4 bytes

float -> 4 bytes
Remember that a pointer can only point to a variable of the type it is supposed to point to. The following example is incorrect:
You could argue that so far, we could have used an integer (or a unsigned long int that is also 8 bytes long on most 64 bits computers) to store an address, since it is a number. The real power of pointers is that they can manipulate values stored at the memory address they point to. This is called dereferencing. To do this, you can use the dereference operator *.
Note that * has a different meaning depending on the context (declaring vs dereferencing pointers).



at declaration, it is used to declare a variable of type pointer to something. Example: int *n;

when used inside the code it is used to dereference pointers. Example *n = 98;

Functions parameters are passed by value

When we call a function in C, parameters are copied.
Arrays

Arrays in C are contiguous memory areas that hold a number of values of the same type. Unlike some other languages, in C, all elements of an array have the same type. To declare an array we use this syntax: type var_name[number_of_elements];, where number_of_elements is the number of elements of type type that we need.
Pointers vs Arrays

In C, an array is NOT a pointer, the variables we declare as arrays do not hold a memory address.



When we declare an array, we use a name to refer to it, but it is only a name. Array names are identifiers that identify the entire array object. They are not pointers to anything. That is why we can not change the value of a 'variable’ which is an array.
So what is happening here? If arrays are not pointers, why is it that the value of an array is the address of the first element of the same array. Isn’t this the definition of a pointer: “a variable which contains the address”? Well… YES, this is a pointer, but the variable a (the array) is NOT. This is why:



When the name of an array is used in an expression, the array type gets automatically implicitly converted to pointer-to-element type in almost all contexts (this is often referred to as “array type decay”). The resultant pointer is a completely independent temporary value, that is the address of the first element of the array.
here are two exceptions to this: when the array name is an operand of sizeof or unary & (address-of), the name of the array then refers to the array object itself.



sizeof



In the context of sizeof, the name of the array refers to the array object itself (composed of all its elements). Thus, sizeof an array will give you the amount of memory space used by all its elements.
Pointers Arithmetic

Another way to access different elements of an array, is to use this other notation: *(var + x), where var is the name of an array, and x is the (x+1)th element (starting counting elements at 0 of course) of this array. For instance if we declare:
Strings

Of course, we can also create an array of chars. It would work exactly the same way.
Data Structures

What is a data structure?

Data structures, as the term implies, are a way of structuring data in order to efficiently store, find, use, and create data, depending on the task at hand. If data is a plate of food, data structures are your utensils (algorithms would be how to effectively use those utensils in this analogy). Just as you will likely select a spoon to eat a bowl of soup rather than a knife, you will learn over time to select and properly use data structures which fit the nature of the data you are working with. When you begin learning basic data structures such as arrays and linked lists, you will start to conceptualize how data is stored, searched, and edited, and what these operations will contribute to the space/time complexity of your program at runtime (this will make more sense once you start to learn about Big O notation). As you continue to learn more complex data structures, you may notice that you need to think more abstractly and deliberately in order to properly implement them. But with patience and practice you will begin to see patterns emerge that will allow you to intuitively see which situation calls for which data structure, just as you know to pick up a spoon when you see a bowl of soup
