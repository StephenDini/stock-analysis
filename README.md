# Module 2 Challenge
## Refactoring Performance Analysis 
Using the stock analysis data from the classwork, we compare the speed at which the computer completes the equivilent functions. The original function should run slower since the program crawls throught the entire set of data twelve times. The refactored equivilent will only run through the data one time, which should mean that the refactored function will be completed quicker.

## Results

**stock comparion between 2017 and 2018**

*2017*
![2017 Results](/Resources/2017-all-stocks.png)

*2018*
![2018 Results](/Resources/2018-all-stocks.png)

**2017 function comparison:**

*Original:*

![VBA Challenge 2017](/Resources/VBA_Challenge_2017.png)

*Refactored:*

![Refactored first run](/Resources/VBA_Challenge_2017%20-%20refactored.png)

*Refactored Second:*

![Refactored second run](/Resources/VBA_Challenge_2017%20-%20refactored%20-%20second%20run.png)

**2018 function comparison:**

*Original:*

![VBA Challenge 2018](/Resources/VBA_Challenge_2018.png)

*Refactored:*

![Refactored first run](/Resources/VBA_Challenge_2018%20-%20refactored.png)

*Refactored Second:*

![Refactored second run](/Resources/VBA_Challenge_2018%20-%20refactored%20-%20second%20run.png)


## Summary

### Refactoring Code
#### Advantages
#### Disadvantages
Depending on the situation, it might not be worth the time investment. A time savings of .003 seconds would not be justified if it took weeks to refactor. 

### Refactoring This Code

#### Advantages
The code runs quicker, this can be seen in the screen shots above which clearly show less computational time for the refactored code.



#### Disadvantages
The refactored code will need more work if the data is unorganized. If one ticker is our of place it will get missed. 