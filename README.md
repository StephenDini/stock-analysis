# Module 2 Challenge
## Refactoring Performance Analysis 
Using the stock analysis data from the classwork, we compare the speed at which the computer completes the equivilent functions. The original function should run slower since the program crawls throught the entire set of data twelve times. The refactored equivilent will only run through the data one time, which should mean that the refactored function will be completed quicker.

## Results
### Ctock Comparion Between 2017 and 2018

The analysis of the stocks in question for the years 2017 and 2018 shows us that there was only two stocks which maintained positive growth in both years. The stock ticker symbol for these are RUN and ENPH.

*2017*

![2017 Results](/Resources/2017-all-stocks.png)

*2018*

![2018 Results](/Resources/2018-all-stocks.png)


### Function Comparison
Refactoring the code has proven to be benifitial as well. If a larger set up data is provided the new refactored code will be able to quickly run through the data once. Comparing the computational time captued in the images below clearly shows the improvements. 

*Iterating through the data multiple times*

Before refactoring the data will be processed each time z is incremented by one.

```VBA
For Z = 0 To 11
    ticker = tickers(Z)
    
    startingPrice = 0
    endingPrice = 0
    totalVolume = 0
    Worksheets(yearValue).Activate
    
    For i = rowStart To rowEnd
        If Cells(i, 1).Value = ticker And Cells(i - 1, 1).Value <> ticker Then
            'set starting price
            startingPrice = Cells(i, 6).Value
        End If
        If Cells(i, 1).Value = ticker And Cells(i + 1, 1).Value <> ticker Then
            'set ending price
            endingPrice = Cells(i, 6).Value
        End If
        'increase totalVolume
        If Cells(i, 1).Value = ticker Then
            totalVolume = totalVolume + Cells(i, 8).Value
            
        End If
    
    Next i

    Worksheets("All Stocks Analysis").Activate
    Cells(4 + Z, 1).Value = ticker
    Cells(4 + Z, 2).Value = totalVolume
    Cells(4 + Z, 3).Value = endingPrice / startingPrice - 1
Next Z
```
*Iterating through the data once*

Since the refactored code is incrementing the tickerIndex by one using conditionals, the data will be processed only once. 

```VBA
For i = 2 To RowCount

    '3a) Increase volume for current ticker
    tickerVolume(tickerIndex) = tickerVolume(tickerIndex) + Cells(i, 8).Value
    
    '3b) Check if the current row is the first row with the selected tickerIndex.
    If Cells(i, 1).Value = tickers(tickerIndex) And Cells(i - 1, 1).Value <> tickers(tickerIndex) Then
        'set starting price
        tickerStartingPrice(tickerIndex) = Cells(i, 6).Value
    End If
    If Cells(i, 1).Value = tickers(tickerIndex) And Cells(i + 1, 1).Value <> tickers(tickerIndex) Then
        'set ending price
        tickerEndingPrice(tickerIndex) = Cells(i, 6).Value
        'Not necessary for another if statment if we find the ending price the new ticker is up next
        'Increases the tickerIndex by 1
        tickerIndex = tickerIndex + 1
    End If

Next i

```

#### 2017 Function Comparison:

*Original:*

![VBA Challenge 2017](/Resources/VBA_Challenge_2017.png)

*Refactored:*

![Refactored first run](/Resources/VBA_Challenge_2017%20-%20refactored.png)

*Refactored Second:*

![Refactored second run](/Resources/VBA_Challenge_2017%20-%20refactored%20-%20second%20run.png)

#### 2018 Function Comparison:

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
Now that the code has been refactored it will run through the data in one pass, this means that any out of place row will cause problems. In order to compensate for this the data should be organized before running the software.