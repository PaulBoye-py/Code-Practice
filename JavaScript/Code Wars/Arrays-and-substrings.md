
**Given two arrays of strings a1 and a2 return a sorted array r in lexicographical order of the strings of a1 which are substrings of strings of a2**

### Example 1: a1 = ["arp", "live", "strong"]

a2 = ["lively", "alive", "harp", "sharp", "armstrong"]

returns ["arp", "live", "strong"]

### Example 2: a1 = ["tarp", "mice", "bull"]

a2 = ["lively", "alive", "harp", "sharp", "armstrong"]

returns [ ]

**Notes: Arrays are written in "general" notation. See "Your Test Cases" for examples in your language.**

In Shell bash a1 and a2 are strings. The return is a string where words are separated by commas.

Beware: r must be without duplicates.

## **Thought Process**

1. Declare newArray;
2. loop through each item in array1 to see if it is a substring of any item in array2, and push to a newArray;
3. Sort newArray to have the items in a lexicographical order, and store in a new array called q;
4. To prevent duplicate entries, make r a set.

## **Solution**

```javascript
function inArray(array1,array2){
  //Declare newArray 
  let newArray = [];
  //loop through each item in array1 to see if it is a substring of any item in array2, and push to a newArray
  for ( let i=0; i < array1.length; i++) {
    for ( let j=0; j < array2.length; j++) {
      if (array2[j].includes(array1[i])) {
        newArray.push(array1[i])
      };
    };
  };
  
  //Sort newArray to have the items in a lexicographical order, and store in a new array called q
  let q = newArray.sort();
  
  //To prevent duplicate entries, make r a set
  let r = [...new Set(q)]
  return r;
  //  
}
```
