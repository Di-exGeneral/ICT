# SEMESTER TEST MEMO

## QUESTION 1


### 1.1. An analyst places football, basketball, swimming, and cricket in a “Sports” category. Which operation has occurred?

**b.** Grouping

---

### 1.2. Which statement does not describe bar charts?

**c.** Show proportions

---

### 1.3. Which pseudocode command could remove duplicate data?

**d.** clean_duplicates()

---

### 1.4. Which chart best shows monthly rainfall over a year?

**b.** Line chart

---

### 1.5. “Mean must be a value in the dataset.” Is this true or false?

**b.** Sometimes true

---

### 1.6. Which option helps most with chart accessibility?

**d.** Colour-blind-friendly palette

---

### 1.7. Which pseudocode command could create a chart?

**c.** create_chart()

---

### 1.8. In visual storytelling, what does “label key elements” mean?

**b.** Naming data points

---

### 1.9. Which visual best shows a part-to-whole relationship?

**c.** Pie chart


---

### 1.10. Which statement describes mode?

**b.** Most frequent value



## QUESTION 2

### 2.1. Pseudo-code must use correct indentation and syntax like Python or Java.

- False

---
### 2.2. Sorting by “Age” in ascending order places the oldest person first.

- False

---

### 2.3. “Data dissemination” means sharing insights with others.

- True

---

### 2.4. Data visualisation is only useful when it includes 3D effects.

- False

---

### 2.5. A dataset without labels can still produce a meaningful pie chart.

- False

---

### 2.6. “Read, Clean, Group, Chart, Explain” is a valid mini-project workflow.

- True

---

### 2.7. The highest bar in a bar chart always represents the worst value.

- False

---

### 2.8. Data tables always show proportions.

- False

---

### 2.9. Data tables always show proportions.

- False

### 2.10. Headings in data storytelling act like news headlines.

- True

---


## QUESTION 3

**3.1.** Why might someone misinterpret a pie chart without percentages?

**Answer**
- Without percentages, readers may struggle to judge slice sizes by sight, especially when slices look similar.

---

**3.2.** Why might raw data need processing before use?

**Answer**
- Raw data may contain errors or inconsistent values. Cleaning improves accuracy and consistency before analysis.

---

**3.3.** How can poor label choices confuse readers?

**Answer**
- Vague or missing labels can make an axis, category or value unclear.

---

**3.4.** Give one reason why non-technical teams use pseudo-code.

**Answer**
- Pseudo-code communicates logic clearly without requiring programming knowledge.

---

**3.5.** What is one benefit of using summaries such as mean or median?

**Answer**
- Mean or median reduces a large dataset to one simple value, making data easier to compare.

---

**3.6.** Why might a caption explain information better than a title?

**Answer**
- A caption can use full sentences to explain insights clearly, while a title usually stays short.

---

**3.7.** What is one key difference between grouping and linking?

**Answer**
- Grouping places similar items together. Linking connects related items across tables or datasets.

---

**3.8.** Why are peaks and dips annotated in line charts? 

**Answer**
- Annotations highlight important changes or events that readers might otherwise miss.

---

**3.9.** How does a legend help in a multicolour chart?

**Answer**
- A legend explains what each colour represents, helping readers decode a chart.

---

**3.10.** When is a textual explanation better than a visual explanation?

**Answer**
- Text works well when data are small, simple or too abstract for a visual to clarify.


---

## QUESTION 4

**4.1.** Read this case carefully. Answer clearly and concisely. Use examples and justification.
         Average test mark is 60, but most students scored between 70 and 90. What is happening?

**4.2.** Read this case carefully. Answer clearly and concisely. Use examples and justification.
         A user cannot tell what a chart measures. What is most likely missing?

---

### QUESTION 5

**5.1.** Instructions: Write clear, structured pseudocode or step-by-step logic. Show logic flow and reasoning.
         A student dataset contains these records. Each record stores Name, Age, and Hobby:

            James, 19, Football
            Emily, 20, Music
            William, 18, Reading
            Charlotte, 19, Football
            Harry, 21, Music
            Sophie, 20, Reading
            Oliver, 19, Football
            Amelia, 18, Music
            Write pseudocode that:

  i. Groups students according to Hobby. \
  ii. Counts how many students belong to each hobby group.\
  iii. Prints each hobby, student names in that group, and total students in that group.


Suggested solution:
```

FUNCTION GroupByHobby(students): 
    hobbyGroups = empty dictionary

    FOR EACH student IN students: 
        hobby = student.Hobby

        IF hobby NOT IN hobbyGroups: 
            hobbyGroups[hobby] = empty list
        END IF

        ADD student.Name TO hobbyGroups[hobby]

    END FOR

    FOR EACH hobby IN hobbyGroups: 
        PRINT hobby, hobbyGroups[hobby], LENGTH(hobbyGroups[hobby])
    END FOR

END FUNCTION

```

---

**5.2.** Instructions: Write clear, structured pseudocode or step-by-step logic. Show logic flow and reasoning.
         A dataset named DProducts contains eight products supplied by two companies:

            TechWorld supplies:
            Laptop
            Mouse
            Keyboard
            Monitor

            FurnCo supplies:
            Desk
            Chair
            Bookshelf
            Lamp
            Write pseudocode that:

  i. Creates a supplier-to-products relationship map, where each supplier links to all products it supplies. \
  ii. Prints this relationship as a text-based arrow diagram, showing each supplier pointing to its products.

Suggested solution:
```

FUNCTION BuildSupplierMap(products):  
    supplierProducts = empty dictionary

    FOR EACH product IN products:  
        supplier = product.Supplier

        IF supplier NOT IN supplierProducts:  
            supplierProducts[supplier] = empty list 
        END IF

        ADD product.Item TO supplierProducts[supplier]

    END FOR

    FOR EACH supplier IN supplierProducts:  
        FOR EACH item IN supplierProducts[supplier]:  
            PRINT supplier, "->", item 
        END FOR 
    END FOR

END FUNCTION  
```
---



