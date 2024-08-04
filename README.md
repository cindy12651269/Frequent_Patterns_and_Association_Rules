# Frequent Patterns and Association Rules

This project calculates frequent patterns using the Apriori algorithm and generates association rules from a given dataset. The implementation utilizes the `mlxtend` library in Python.

## Dataset

The dataset consists of transactions with various items:

```python
dataset = [
    ['Milk', 'Onion', 'Nutmeg', 'Kidney Beans', 'Eggs', 'Yogurt'],
    ['Dill', 'Onion', 'Nutmeg', 'Kidney Beans', 'Eggs', 'Yogurt'],
    ['Milk', 'Apple', 'Kidney Beans', 'Eggs'],
    ['Milk', 'Unicorn', 'Corn', 'Kidney Beans', 'Yogurt'],
    ['Corn', 'Onion', 'Onion', 'Kidney Beans', 'Ice cream', 'Eggs'],
]
```
## Code Explanation
1. **Data Preparation**: The dataset is converted into a format suitable for the apriori function using TransactionEncoder.
2. **Frequent Itemsets**: The apriori function is used to find itemsets with a minimum support of 0.6.
3. **Association Rules**: The association_rules function generates rules based on the lift metric with a minimum threshold of 1.
4. **Results Display**: The frequent itemsets and the generated association rules are printed.

## Requirements
- `mlxtend`
- `pandas`

You can install the required libraries using:
```bash
pip install mlxtend pandas
```
## Running the Code
Save the code in a file named **`Frequent_Patterns_and_Association_Rules.py`** and run it. The frequent itemsets and association rules will be displayed in the console.

```bash
python Frequent_Patterns_and_Association_Rules.py
```
## Sample Code
```python
from mlxtend.preprocessing import TransactionEncoder
from mlxtend.frequent_patterns import apriori, association_rules
import pandas as pd

# Given dataset
dataset = [
    ['Milk', 'Onion', 'Nutmeg', 'Kidney Beans', 'Eggs', 'Yogurt'],
    ['Dill', 'Onion', 'Nutmeg', 'Kidney Beans', 'Eggs', 'Yogurt'],
    ['Milk', 'Apple', 'Kidney Beans', 'Eggs'],
    ['Milk', 'Unicorn', 'Corn', 'Kidney Beans', 'Yogurt'],
    ['Corn', 'Onion', 'Onion', 'Kidney Beans', 'Ice cream', 'Eggs'],
]

# Convert the dataset to a format suitable for the apriori function
te = TransactionEncoder()
te_ary = te.fit(dataset).transform(dataset)
df = pd.DataFrame(te_ary, columns=te.columns_)

# Use the apriori function to find frequent itemsets
frequent_itemsets = apriori(df, min_support=0.6, use_colnames=True)

# Use the association_rules function to generate association rules
rules = association_rules(frequent_itemsets, metric="lift", min_threshold=1)

# Display results
print("Frequent Itemsets:")
print(frequent_itemsets)
print("\nAssociation Rules:")
print(rules)

```
## Output
The output will display the frequent itemsets and the corresponding association rules found in the dataset.
```css
This version improves readability and provides a clear structure for understanding the code and its execution.
```



