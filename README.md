# Iterator_ADT_C

## **Iterator**

An iterator offers an easy way to traverse through a collection, add new elements, delete and modify existing elements. Iterators are widely supported by langauges like C++ and Java. However, C does not offer iterators. In this code, I have implemented list iterator that allow the programmer to traverse the list in either direction, modify the list during iteration, and obtain the iterator's current position in the list.

A List Iterator has no current element; its cursor position always lies between the element that would be returned by a call to previous and the element that would be returned by a call to next. An iterator for a list of length n has n+1 possible cursor positions

The following interface specifications are drawn from Java (7) ListIterator API and adapted for C implementations.


## **Interface**

* IteratorInt IteratorIntNew()

  Creates a new list iterator that can store integer values.


* int add(IteratorInt it, int v)

  Inserts the specified value v into the list iterator it. The element is inserted immediately before the element that would be returned by next(), if any, and after the element that would be returned by previous(), if any. (If the list contains no elements, the new element becomes the sole element on the list.) The new element is inserted before the implicit cursor: a subsequent call to next would be unaffected, and a subsequent call to previous would return the new element.
  Returns 1 if successful, 0 otherwise.


* int hasNext(IteratorInt it)

  Returns 1 if the given list iterator has more elements when traversing the list in the forward direction, returns 0 otherwise.


* int hasPrevious(IteratorInt it)

  Returns 1 if the given list iterator has more elements when traversing the list in the reverse direction, returns 0 otherwise.


* int *next(IteratorInt it)

  Returns the pointer to the next value in the given list iterator and advances the cursor position. This method may be called repeatedly to iterate through the list, or intermixed with calls to previous to go back and forth. (Note that alternating calls to next and previous will return the same element repeatedly.)
  The method returns NULL if it has no next value.


* int *previous(IteratorInt it)

  Returns the pointer to the previous value in the given list iterator and moves the cursor position backwards. This method may be called repeatedly to iterate through the list backwards, or intermixed with calls to next to go back and forth. (Note that alternating calls to next and previous will return the same element repeatedly.)
  The method returns NULL if it has no previous value.


* int deleteElm(IteratorInt it)

  Deletes from the list iterator the last value that was returned by next or previous or findNext or findPrevious.
  
  *Precondition:* A call to deleteElm must be IMMEDIATELY preceded by a successful call to one of next or previous or findNext or findPrevious.
  
  Returns 1 if successful, 0 otherwise (for example, invalid deleteElm call).


* int set(IteratorInt it, int v)

  Replaces the last element returned by next or previous or findNext or findPrevious with the specified element (v).
  
  *Precondition:* A call to set must be IMMEDIATELY preceded by a successful call to one of next or previous or findNext or findPrevious.
  
  Returns 1 if successful, 0 otherwise (for example, invalid set call).


* int *findNext(IteratorInt it, int v)

  Returns pointer to the next value in it that matches the given value v and advances the cursor position past the value returned.
  The method returns NULL if there is no such next value and the cursor is not moved from the current position.


* int *findPrevious(IteratorInt it, int v)

  Returns pointer to the previous value in it that matches the given value v and moves the cursor position backwards before the value returned.
  The method returns NULL if there is no such previous value and the cursor is not moved from the current position.


* void reset(IteratorInt it)

  Resets it to the start of the list.


* void freeIt(IteratorInt it)

  Deletes all the nodes in it and frees associated memory.

