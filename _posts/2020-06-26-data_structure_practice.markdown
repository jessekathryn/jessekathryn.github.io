---
layout: post
title:      "Data Structure Practice"
date:       2020-06-26 17:57:00 -0400
permalink:  data_structure_practice
---


This blog is dedicated to Arrays.  A friend who works at FBK suggested to become very good at all of the basic data structures.  For the next few posts, I will write about the different types of structures to store data and the best time to use each one.

Array 101 on LeetCode describes an array as:

> An Array is a collection of items. The items could be integers, strings, DVDs, games, books—anything really. The items are stored in neighboring (contiguous) memory locations. Because they're stored together, checking through the entire collection of items is straightforward.
> 

### Java

**An example of a very simple array in Java**

```
// The actual code for creating an Array to hold DVD's.
DVD[] dvdCollection = new DVD[15];


// A simple definition for a DVD.
public class DVD {
    public String name;
    public int releaseYear;
    public String director;

    public DVD(String name, String releaseYear, String director) {
        this.name = name;
        this.releaseYear = releaseYear;
        this.director = director;
    }

    public String toString() {
        System.out.println(
            this.name + ", directed by " + this.director + ", released in " + this.releaseYear));
    }
}
```

**To add or to manipulate the array in Java; primitive actions**
```
// Firstly, we need to actually create a DVD object for The Avengers.
DVD avengersDVD = new DVD("The Avengers", 2012, "Joss Whedon");

// Next, we'll put it into the 8th place of the Array. Remember, because we
// started numbering from 0, the index we want is 7.
dvdCollection[7] = avengersDVD;
```

### JavaScript Common Definitions (MDN)
**The following actions are recommended when manipulating arrays in JS.  Resourced from MDN**

**Create an Array**

```
let fruits = ['Apple', 'Banana']

console.log(fruits.length)
// 2
```

**Access an Array item using the index position**

```
let first = fruits[0]
// Apple

let last = fruits[fruits.length - 1]
// Banana
```
**Loop over an Array
**
```
fruits.forEach(function(item, index, array) {
  console.log(item, index)
})
// Apple 0
// Banana 1
```
**Add an item to the end of an Array**

```
let newLength = fruits.push('Orange')
// ["Apple", "Banana", "Orange"]
```
**Remove an item from the end of an Array**

```
let last = fruits.pop() // remove Orange (from the end)
// ["Apple", "Banana"]
```
**Remove an item from the beginning of an Array**

```
let first = fruits.shift() // remove Apple from the front
// ["Banana"]
```
**Add an item to the beginning of an Array
**
```
let newLength = fruits.unshift('Strawberry') // add to the front
// ["Strawberry", "Banana"]
```
Find the index of an item in the Array
```
fruits.push('Mango')
// ["Strawberry", "Banana", "Mango"]

let pos = fruits.indexOf('Banana')
// 1
```

**Remove an item by index position**

```
let removedItem = fruits.splice(pos, 1) // this is how to remove an item
                                        
// ["Strawberry", "Mango"]
```

**Remove items from an index position**

```
let vegetables = ['Cabbage', 'Turnip', 'Radish', 'Carrot']
console.log(vegetables)
// ["Cabbage", "Turnip", "Radish", "Carrot"]

let pos = 1
let n = 2

let removedItems = vegetables.splice(pos, n)
// this is how to remove items, n defines the number of items to be removed,
// starting at the index position specified by pos and progressing toward the end of array.

console.log(vegetables)
// ["Cabbage", "Carrot"] (the original array is changed)

console.log(removedItems)
// ["Turnip", "Radish"]
```

**Copy an Array**

```
let shallowCopy = fruits.slice() // this is how to make a copy
// ["Strawberry", "Mango"]
```


