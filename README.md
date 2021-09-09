# TwinCAT-Abstract-Data-Structures
Exploring Abstract Data Structures in Structured Text for use in PLCs

**This project looks at the implementation of the following data structures in TwinCAT:**

* Dynamic Arrays
* Linked Lists **[Singly, Doubly, Circular]**
* Queues **[Dynamic Array, Linked List]**
* Stacks **[Dynamic Array, Linked List]**

- - - -
### Dynamic Array
Zero indexed array that can change its size at run-time. The array will automatically resize itself when inserting an element in a position out of it's bounds.
Examples are included on the POU called `P_Dynamic_Array`. Listed below are some, not all, functionalities for manupulating data in the dynamic array. 
Just run the program and the appropriate boolean data.

**Declaration:** 
```Pascal
(* <name of array> : FB_Dynamic_Array(<Interger to Initialisation array with>) *)

//Initalise array with 10 elements type 
fbDyn_Array : FB_Dynamic_Array(10);
```
**Insertion:**
```Pascal
(* <name of array>.Insert(<element to insert>, <position to insert element>) *)

// Insert element of value 33 in the 10 position in array
fbDyn_Array.Insert(33,10); 
```

**Accessing:**
```Pascal
(* <name of array>.Access(<position of element>) *)

// Get in the 3rd element on the array
IF bAccess THEN nAccess := fbDyn_Array.Access(2); bAccess := 0; END_IF
```

**Resizing:**
```Pascal
(* <name of array>.Resize(<new size>) *)

// Changes number of elements in array to five
fbDyn_Array.Resize(5);
```