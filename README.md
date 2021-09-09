# TwinCAT-Abstract-Data-Structures
Exploring Abstract Data Structures in Structured Text for use in PLCs

**This project looks at the implementation of the following data structures in TwinCAT:**

* Dynamic Arrays
* Linked Lists **[Singly, Doubly, Circular]**
* Queues **[Dynamic Array, Linked List]**
* Stacks **[Dynamic Array, Linked List]**

- - - -
### Dynamic Array
Zero indexed array that can change its size at run-time. The array will automatically resize itself when inserting an element in a position out of its bounds.
See the POU called `P_Dynamic_Array` for examples. Listed below are some, not all, functionalities for manupulating data in the dynamic array. 
Just run the program and write the appropriate boolean variables whilst logged in.

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

- - - -
### Linked List
A zero indexed list of elements in unchained location in memory linked together. This list is dynamic so it can be resized at run-time. 
Unlike dynamic arrays, it only takes up as much space as needed. The examples below demostrates some of the functionalities available.
See `P_Singly_Linked_List` POU for more examples.

**Declaration:** 
```Pascal
(* <name of list> : FB_<Singly, Doubly, Circular>_Linked_List *)

//Initalise list
fbLinked_List : FB_Singly_Linked_List;
```

**Insertions:**
```Pascal
(* 
    <name of list>.Create(<element to insert>); // Insert element at the end of the list
    <name of list>.Push(<element to insert>);   // Insert element at the start of the list
    <name of list>.Insert(<element to insert>, <position to insert element>) // Insert element at a specified location 
*)

// Insert 3 elements into the list
fbLinked_List.Create(1);
fbLinked_List.Push(3);
fbLinked_List.Insert(2,1);
```

**Deletions:**
```Pascal
(* 
    <name of list>.Pop(); // Remove element at the start of the list
    <name of list>.Push(<position of element>); // Remove element at a specified location
 *)

// Remove the last and first element from the list
fbLinked_list.Remove(2);
fbLinked_List.Pop();
```