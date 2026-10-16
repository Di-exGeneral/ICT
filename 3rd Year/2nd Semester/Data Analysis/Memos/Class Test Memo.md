# CLASS TEST MEMO

## QUESTION 1   

### 1.1. A shop holds only 5 GB of sensor readings, images, and transactions. Its usual tools cannot combine or process them quickly. Which statement best describes this dataset?

**c.** It may be Big Data because normal technologies cannot meet its processing needs.


---
### 1.2. Data contains values such as "Tea", "tea", and "TEA". What issue does this show?

**b.** Case inconsistency

---

### 1.3. Which chart best shows hobby preferences across 100 students?

**c.** Pie chart

---

### 1.4. "Friday has 40% of all customers." What does this statement represent?

**d.** Data insight

---

### 1.5. What may make a chart misleading?

**a.** Truncated Y-axis

---

### 1.6. What does the pseudocode step "group_by_category(data)" mean?

**d.** Grouping

---

### 1.7. A dataset has several identical "Espresso" rows. What action does it need?

**b.** Duplicate removal

---

### 1.8. What does a pie chart always do?

**b.** Adds up to 100%

---

### 1.9. Which statement does not describe bar charts?

**d.** Show proportions

---

### 1.10. Which chart best shows monthly rainfall across one year?

**d.** Line chart



## QUESTION 2

### 2.1. Pie charts require mutually exclusive categories.

- True


### 2.2. Filtering data means removing it permanently.

- False


### 2.3. Data cleaning is unnecessary if data comes from a trusted source.

- False


### 2.4. A misleading chart might use a non-zero Y-axis to exaggerate differences.

- True


### 2.5. The title “Sales over Week” is more informative than “Bar Chart”.

- True


### 2.6. A table with missing column headers can still be used for analysis.

- False


### 2.7. Visualisation is more effective when labels are short and vague.

- False


### 2.8. A well-labelled bar chart requires both X-axis and Y-axis labels.

- True


### 2.9. All parts of a pie chart must sum to 360°.

- False


### 2.10. Grouping is best applied before data cleaning.

- False


## QUESTION 3 & 4

**a.** What happens when a chart has no axis labels?

**Answer** 
- A viewer cannot clearly understand what the chart measures.

---

**b.** How can misleading charts affect decision-making? Justify the reasoning clearly.

**Answer** 
* Misleading charts can create false impressions, which may cause poor business or policy choices.

---

**c.** A shop records daily temperature, weather conditions, ice-cream sales, and stock shortages. Design an analysis that helps its manager order suitable stock.
  Give clear examples and justify each choice.

**N.B** Use AI to get your answer, this was 10 marks😭😭

**My Answer**

* Clean the data Check for missing or incorrect temperatures, weather conditions, sales, or shortage records Example: If temperature is recorded as -500°C, correct or investigate it before using the data Why: Incorrect data could lead to wrong stock orders Group the data by weather condition Calculate the average ice-cream sales for conditions such as Sunny, Cloudy, and Rainy Example: Sunny: average 120 units Cloudy: average 70 units Rainy: average 40 units Why: This shows how weather affects demand Group temperatures into ranges For example: Below 15°C 15–25°C Above 25°C Calculate average sales for each range Why: Higher temperatures may result in higher ice-cream demand Analyse stock shortages Compare days with shortages against temperature, weather, and sales Example: If shortages frequently occur when temperatures are above 25°C and sales exceed 100 units, the shop should increase stock before hot days Why: Shortage patterns help identify when current stock levels are insufficient Create a chart Use a line chart to show temperature and ice-cream sales over time Use a bar chart to compare average sales across weather conditions Why: Visualisation makes demand patterns easier for the manager to identify Use the findings to order stock If the analysis shows that hot, sunny days consistently produce high sales, the manager should order more ice cream before those days If rainy or cool days have low sales, order less to avoid unnecessary stock and waste

---

**d.** Explain one risk of skipping the data-cleaning step in a project. Justify the reasoning clearly.

**Answer**

* Skipping data cleaning may leave errors, such as duplicates or typing mistakes, which can mislead results.

---

## QUESTION 5

A sorting service receives an original input sequence plus a proposed sorted output sequence.

Write clear, structured pseudocode or step-by-step logic which:

verifies that proposed output follows ascending order; and
confirms that no values were added, removed, or duplicated incorrectly.
Emphasise logic flow and reasoning.


```
FUNCTION VerifySort(original, proposed)
    IF LENGTH(original) != LENGTH(proposed) THEN
        RETURN false
    END IF


FOR position FROM 1 TO LENGTH(proposed) - 1
    IF proposed[position] > proposed[position + 1] THEN
        RETURN false
    END IF
END FOR

originalCounts = COUNT_EACH_VALUE(original)
proposedCounts = COUNT_EACH_VALUE(proposed)

IF originalCounts != proposedCounts THEN
    RETURN false
END IF

RETURN true


END FUNCTION

```


