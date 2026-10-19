# NDTA631 20 (Year-End Examination 2025): MEMORANDUM

**Total: 100 Marks**

| Question | Marks |
|---|---|
| Question 1 | 10 |
| Question 2 | 10 |
| Question 3 | 20 |
| Question 4 | 27 |
| Question 5 | 33 |

---

## Question 1 [10 Marks]

| Q | Answer | Reason |
|---|---|---|
| 1.1 | **C) Structured data** | Rows and labelled columns (Fruit, Units Sold, Price per Unit) form a tabular, structured layout. |
| 1.2 | **C) Favourite colour** | Categories, not measured numbers. |
| 1.3 | **D) Read** | Workflow starts with reading the dataset, then spotting errors. |
| 1.4 | **B) Pie charts cannot show changes over time** | Pies show part to whole at one point in time. Line charts show trends. |
| 1.5 | **B) Comparing numerical values across categories** | Bar heights make categories easy to compare. |
| 1.6 | **C) Pie chart** | Shows each part as a share of the whole. |
| 1.7 | **C) Most frequent value** | Mode is the value that appears most often. |
| 1.8 | **See note** | Lecture 5: sorting only rearranges rows, removes no data and changes viewing order. Filtering is what hides rows. The wording is ambiguous, so confirm the lecturer's key. |
| 1.9 | **D) Dissemination** | Explaining what a chart shows is communicating findings. |
| 1.10 | **C) Error checking** | Real data is messy, so errors are checked before anything is drawn. |

---

## Question 2 [10 Marks]

| Q | Answer | Reason |
|---|---|---|
| 2.1 | **False** | Pie charts show part to whole. Line charts show change over time. |
| 2.2 | **True** | Mode is the most frequent value. |
| 2.3 | **False** | Cleaning comes before charting. |
| 2.4 | **True** | Bar charts compare categories. Line charts show trends. |
| 2.5 | **False** | Sorting reorders rows and removes none. |
| 2.6 | **True** | Headline thinking: titles state the conclusion, like a news headline. |
| 2.7 | **False** | Filtering on Product = Tea keeps the tea rows and hides the others. |
| 2.8 | **True** | The connecting line shows progression or trend. |
| 2.9 | **False** | A missing label makes a chart harder to interpret. |
| 2.10 | **False** | Charts reveal trends faster than tables. |

---

## Question 3 [20 Marks]
*2 marks each: 1 mark for the correct point, 1 mark for the justification.*

**3.1** 
Salary data is skewed by a few extremely high earners (outliers). The mean is pulled towards them and overstates the typical salary. The median is the middle value, so extreme values do not affect it.

**3.2**
Bar chart. Each item gets its own bar, so values are easy to compare by height. A pie chart makes similar slices hard to compare, especially with many slices.

**3.3** 
Errors such as duplicates, missing values and inconsistent labels distort totals, counts and groupings. A chart built on dirty data gives misleading visuals and wrong conclusions.

**3.4** 
Use mode for categorical data (e.g. favourite colour) or when finding the most popular or frequent value. Mean and median cannot be calculated for categories.

**3.5** 
It exaggerates small differences, making them look dramatic. The viewer is misled about the true size of the difference.

**3.6** 
It states logic in plain language, independent of any programming language, so non-programmers can read it. It lets teams plan and check the steps and spot logic errors before building anything.

**3.7** 
Missing, vague or ambiguous labels leave readers unsure what an axis or series represents. For example, "Price" could mean price per kg or total price, so they misread the data.

**3.8** 
It works with categorical data, shows the most popular choice, is easy to understand and is not affected by outliers. It supports decisions such as which item to restock.

**3.9** 
When the whole chart needs explanatory text that guides interpretation and reinforces the key message. An annotation or arrow points at one specific element, such as a single outlier.

**3.10** 
Outliers may reveal important events, errors or opportunities. Showing them keeps the presentation honest and avoids hiding important values or cherry picking data.

---

## Question 4 [27 Marks]
*3 marks each: 1 mark for the correct choice or answer, 2 marks for justification and example.*

**4.1** 
**Bar chart.** "Favourite Subject" is categorical and the count per subject is compared. The tallest bar shows the most liked subject.

**4.2** 
**Bar chart.** Item names are categories and quantities sold are values to compare. Sorting highest to lowest makes the best seller obvious.

**4.3** 
**Line chart.** Temperature is recorded over time (days). Connected points show the trend and progression across the month.

**4.4**
**Bar chart** (a pie chart is acceptable if there are few colours). Colour is categorical and the responses are counted per colour. Bars let you compare which colour is most popular, which is the mode.

**4.5**
**Median.** The ZAR1 million value is an outlier that pulls the mean far upward. The median depends on position, not size, so it stays representative.

**4.6** 
It puts rows that share a category into groups. You can then count, total or average each group, compare categories and see which sells most.

**4.7**
Mark the cell as missing. If the value can be determined from other records, fill it in. If not, flag the row for removal or label it "Unknown", and document the decision.

**4.8** 
Colour alone is not accessible to colour blind viewers, and with no text labels or legend the viewer cannot tell what the colours or values mean.

**4.9** 
A method for presenting chart insights:
- **Tell:** state the main finding clearly.
- **Show:** present the visual evidence.
- **Label:** mark the key elements.
- **Explain:** give the context and what it means.

---

## Question 5 [33 Marks]

### 5.1 Count "Coffee" in a column [6 Marks]

```
FUNCTION CountCoffee(column):
    coffeeCount = 0

    FOR EACH value IN column:
        IF value == "Coffee":
            coffeeCount = coffeeCount + 1
        END IF
    END FOR

    RETURN coffeeCount

END FUNCTION
```


### 5.2 Remove rows where "City" is missing [6 Marks]

```
FUNCTION RemoveMissingCities(dataset):
    cleanedData = empty list

    FOR EACH row IN dataset:
        IF row.City IS NOT empty:
            ADD row TO cleanedData
        END IF
    END FOR

    RETURN cleanedData

END FUNCTION
```



### 5.3 Find the mode in a list of strings [11 Marks]

```
FUNCTION FindMode(stringList):
    frequencyCount = empty dictionary

    FOR EACH word IN stringList:
        IF word IN frequencyCount:
            frequencyCount[word] = frequencyCount[word] + 1
        ELSE:
            frequencyCount[word] = 1
        END IF
    END FOR

    maxFrequency = 0
    modes = empty list

    FOR EACH word, count IN frequencyCount:
        IF count > maxFrequency:
            maxFrequency = count
            modes = empty list
            ADD word TO modes
        ELSE IF count == maxFrequency:
            ADD word TO modes
        END IF
    END FOR

    RETURN modes

END FUNCTION
```


### 5.4 Find the maximum value in "Marks" [5 Marks]

```
FUNCTION FindMaxMark(dataset):
    maxMark = dataset[0].Marks

    FOR EACH row IN dataset:
        IF row.Marks > maxMark:
            maxMark = row.Marks
        END IF
    END FOR

    RETURN maxMark

END FUNCTION
```



### 5.5 Capitalise the first letter of every "City" [5 Marks]

```
FUNCTION CapitaliseCities(dataset):
    FOR EACH row IN dataset:
        city = row.City

        IF city IS NOT empty:
            firstLetter = UPPERCASE(city[0])
            remainingLetters = LOWERCASE(city[1 TO END])

            row.City = firstLetter + remainingLetters
        END IF
    END FOR

    RETURN dataset

END FUNCTION
```
