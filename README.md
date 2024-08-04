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
