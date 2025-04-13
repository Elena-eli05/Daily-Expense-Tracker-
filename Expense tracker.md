import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

data = {
    'Category': ['Food', 'Transport', 'Shopping', 'Food', 'Bills', 'Transport'],
    'Amount': [150, 50, 300, 100, 200, 60]
}
df = pd.DataFrame(data)

total = np.sum(df['Amount'])
average = np.mean(df['Amount'])
print("Total Spent: ₹", total)
print("Average Expense: ₹", average)

category_expense = df.groupby('Category')['Amount'].sum()

category_expense.plot(kind='bar', color='orange')
plt.title('Expenses by Category')
plt.xlabel('Category')
plt.ylabel('Amount (₹)')
plt.grid(True)
plt.show()
