# **Lab Report 5**
## **Part 1 - Debugging Scenario**

**Original Post by Student**
Hello!

I'm working on the method for my list where it suppose to add elements to the list that has reached the max capacity. However, I have encounter an `IndexOutOfBoundExcpetion`. I thought that the `ArrayList` would automatically be resize as being a part of the Java function. Here is the output of the error that I am getting attached below: 
![Image](error.png)
The list are specified with a capacity at the beginning, add I have added elements to check for the fullness of the list before adding a new element into the list. Could the bug being the fullness check is incorrect, or my understnading of the `ArrayList` that are handling full are wrong?

**Response from TA**
Hi there,

it seems like there might be a slightly misunderstanding about how the `ArrayList` capacity works in Java. However, the `ArrayList` does resize automatically, but when manually checking its capacity before adding elements, you might be comparing against the wrong value. Maybe you could try to use the `size()` method to check if the list is full?

**Follow-Up by Student**

Thanks for the suggestion! After reviewing my code, I did notice on my mistake, which is how the way I check for the fullness of the list. Here was the problematic part of my code:
![Image](errorCap.png)
I have realized that the `ArrayList` handles its own resizing, and my check for fullness was unnecessary and incorrect. With that, the corrected code would output the correct output:
![Image](correctOutput.png)
Thanks for the help!

**File and Directory Structure**
-   `List.java`
-   `run.sh`

**Contents of the Files**
- `List.java` with the bug before fixing
  ![Image](List.png)
- `run.sh`
  ![Image](run.png)

**Command to Trigger the Bug**
`bash run.sh`, are the command to run in the terminal for the bug to be triggered

**How to Fix the Bug**
- Fix the bug by 
  
