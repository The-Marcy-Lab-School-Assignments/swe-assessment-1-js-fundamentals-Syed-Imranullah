# Mod 1 Assessment - Short Response Section

Write your responses directly in this file. Follow markdown formatting guidelines.

---

## Section 1: Short Response

### Question 1
The code throws a ReferenceError. This happens because the variable currentStatus is declared inside the if and else blocks using let, so it only exists inside those blocks. When console.log(currentStatus) runs, it is outside those blocks, so JavaScript cannot find the variable and gives an error. To fix this, you can declare currentStatus before the if statement, then just assign a value inside the if and else. for example 

```javascript
const react = (isReuben) => {
  let currentStatus;
  if (isReuben) {
    currentStatus = 'Everything is just fine';
  } else {
    currentStatus = 'Time to panic.'
  }
  
  console.log(currentStatus);
}

react(true);

```

### Question 2
The following code generates "Michael Jordan" because the variable bestPlayer was named LeBron James before we created a new variable named theGoat and set it equal to bestPlayer. This means the variable theGoat is basically the best player. Then we declared the name for bestPlayer as Michael Jordan. When we called theGoat’s name, since theGoat is bestPlayer and bestPlayer’s new name we declared is Michael Jordan, therefore it’s printing Michael Jordan.

### Question 3
The code prints, Paul is the hardest working person in the room. Laisha is also the hardest working person in the room.
because at first we created a variable named theHustler and gave it a string value Laisha. Then we created another function named shoutout. Inside that function, we created another name for theHustler called Paul. Then we logged the function first inside teh function shoutout with the name and string:
```${theHustler} is the hardest working person in the room. `` theHustler prints Paul because we’re calling it first inside shoutout where we declared the name Paul. Then, when we console.log again outside of shoutout, it prints the name outside of shoutout, which is Laisha, and it prints the line "is also the hardest working person in the room." Together, it prints, Paul is the hardest working person in the room.
Laisha is also the hardest working person in the room.

### Question 4
Rest peremeter allows a function to accept any number in the argument as an array. With rest paremeter you can gather all the remaining argumnt into a single array. 


### Question 5


### Question 6


### Question 7


### Question 8

