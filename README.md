# Module 2 Challenge
## Refactoring Performance Analysis 
Using the stock analysis data from the classwork, we compare the speed at which the computer completes the equivilent functions. The original function should run slower since the program crawls throught the entire set of data twelve times. The refactored equivilent will only run through the data one time, which should mean that the refactored function will be completed quicker.

## Results
**stock comparion between 2017 and 2018**

The analysis of the stocks in question for the years 2017 and 2018 shows us that there was only two stocks which maintained positive growth in both years. The stock ticker symbol for these are RUN and ENPH.

*2017*

![2017 Results](/Resources/2017-all-stocks.png)

*2018*

![2018 Results](/Resources/2018-all-stocks.png)


**2017 function comparison:**

Refactoring the code has proven to be benifitial as well. If a larger set up data is provided the new refactored code will be able to quickly run through the data once. Comparing the computational time captued in the images below clearly shows the improvements. 

*Original:*

![VBA Challenge 2017](/Resources/VBA_Challenge_2017.png)

*Refactored:*

![Refactored first run](/Resources/VBA_Challenge_2017%20-%20refactored.png)

*Refactored Second:*

![Refactored second run](/Resources/VBA_Challenge_2017%20-%20refactored%20-%20second%20run.png)

**2018 function comparison:**

A special note, the frst run will always take longer to run because memory has not been allocated just yet. We can see this when looking at the 2018 first and second runs.

*Original:*

![VBA Challenge 2018](/Resources/VBA_Challenge_2018.png)

*Refactored:*

![Refactored first run](/Resources/VBA_Challenge_2018%20-%20refactored.png)

*Refactored Second:*

![Refactored second run](/Resources/VBA_Challenge_2018%20-%20refactored%20-%20second%20run.png)


## Summary
### Refactoring Code
#### Advantages
The computational time can be improved by simplifying functions. The legibility can be improved by addressing the following concerns. Can function process information in one pass? Are you reusing code instead of creating functions. Can you add comments to clear up code blocks intent? Answering these questions as you go through your code will lead to more maintainable code as well.

#### Disadvantages
Depending on the situation, it might not be worth the time investment. A time savings of .003 seconds would not be justified if it took weeks to refactor. 

### Refactoring This Code
#### Advantages
The code runs quicker, this can be seen in the screen shots above which clearly show less computational time for the refactored code.

#### Disadvantages
The newly refactored code will only run through the data once, previously it ran through the data each time the ticker index was switched. Now that the code has been refactored it will run through the data in one pass, this means that any out of place row will cause problems. In order to compensate for this the data should be organized bfore running the software.