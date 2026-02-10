# Week 4 - Polymorphism, Linked List

Topics:

    * Running typescript on browser
    * Polymorphism
    * Linked List

## I. Running typescript on browser

Typically the browser API does not understand typescript.

_Parcel_ lets you write modern code (TypeScript, modules, CSS, images) and automatically makes it work in the browser with almost zero setup.

_Parcel_ is a web bundler that takes your TypeScript (and other files), turns them into browser-ready JavaScript, and serves or builds your website for you.


## II. Polymorphism

### 1. what is Polymorphism?

* Polymorphism means “many forms.”

>In object-oriented programming, polymorphism is the provision of one interface to entities of different data types.[^1]

>Basically, Same method name → different behavior.

**Polymorphism helps write flexible code, reduce duplication, and make code easier to extend and maintain**

### 2. Steps to polymorphism

1. Create a contract (Interface / abstract class)
2. Create Classes That Follow the Contract
3. Create Objects Using the Contract Type


## III. Linked List

### 1. what is a Linked List?

>A linked list is a collection of nodes, where each node contains the Data (the value you store) and a reference (pointer) to the next node in the list.  
>Instead of being stored in one continuous block of memory (like arrays), nodes are scattered in memory and linked together.

>Visualized: [10 | next] → [20 | next] → [30 | next] → null

> Each [] is a node, and null is the end of an LL.

**Types of linked list:**

* singly linked list
* doubly linked list
* circular linked list

in this week, we focus only on singly linked list.

### 2. Why and when Use Linked Lists Over Arrays?

* Arrays

    * ✔ Fast random access
    * ✔ Simple structure
    * ❌ Fixed size (in many languages)
    * ❌ Inserting/removing elements is expensive

* Linked Lists

    * ✔ Dynamic size
    * ✔ Fast insertions/deletions
    * ❌ No random access
    * ❌ Extra memory for pointers

In short, use arrays when you need fast index access, simple iteration, and efficient storage for mostly fixed-size data, and use linked lists when you need frequent insertions or deletions and don’t need random access.

### 3. How to write a singly linked list in Typescript.

```ts
//define a Node.
class Node {
  next: Node | null = null;
  data: number;
  constructor(data: number) {
    this.data = data;
  }
}
//define a linked list
class LinkedList {
  head: Node | null = null;
  //add() method adds a new value to the end of the linked list.
  add(data: number) {
    const node = new Node(data);
    if (!this.head) {
      this.head = node;
      return;
    }
    let tail = this.head;
    while (tail.next) {
      tail = tail.next;
    }
    tail.next = node;
  }

  //at() method walks the list node by node until it reaches the requested index.
  at(index: number) {
    if (!this.head) throw new Error("Index out of bounds");
    let counter = 0;
    let node: Node | null = this.head;
    while (node) {
      if (counter === index) {
        return node;
      }
      counter++;
      node = node.next;
    }
    throw new Error("Out of bounds");
  }

  //print() method iterates through the entire list and prints each value.
  print() {
    if (!this.head) {
      return;
    }
    let node: Node | null = this.head;
    while (node) {
      console.log(node.data);
      node = node.next;
    }
  }
}

//Create an empty linked list
const ll = new LinkedList();
```

## IV. Homework: Polymorphism Assignment.
today homework is titled "Polymorphism Lab". Because it's a lab, it introduces a few definition before starting on the actual todo.

### 1. Refactoring Code

Refactoring code is a task to be expected on a task board of a company.

Refactoring code is all about making code more maintainable. It requires you to often clean up and reorganize already-written code without modifying that code's behavior, a task usually belongs to senior developers that refactor code written by interns and junior developers.

### 2. Sorting Data

Sorting data is an extremely common task that needs to be done by Full Stack Web Developers. 

Almost every major web application will utilize behind the scenes some kind of sorting logic that sorts data in different ways.

The data being sorted may vary from strings (like a first name) to numbers(ex - sort by price, lowest price first) to binary pixel data within photos (ex - Shopping website that lets you sort by shirt color), etc.  

### 3. Actual assignment



[^1]: Wikipedia. _Polymorphism (computer science)_.    
https://en.wikipedia.org/wiki/Polymorphism_(computer_science)
