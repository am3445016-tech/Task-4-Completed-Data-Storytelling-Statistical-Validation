# Task-4-Completed-Data-Storytelling-Statistical-Validation
As part of my data analytics journey, I completed Task 4, which focused on transforming analytical findings into a compelling business narrative and validating insights using statistical techniques. This phase helped bridge the gap between technical analysis and real-world business decision-making.


code
import pandas as pd
from scipy.stats import ttest_ind

# Load dataset
df = pd.read_excel("/content/Cleaned_Sales_Data.xlsx")

# Split data
high = df[df['High_Value_Customer'] == True]['Final_Amount']
low = df[df['High_Value_Customer'] == False]['Final_Amount']

# Perform T-test
t_stat, p_value = ttest_ind(high, low)

print("T-Statistic:", t_stat)
print("P-Value:", p_value)
rrelation
correlation = df[['Website_Visits', 'Final_Amount']].corr()

print(correlation)
from scipy.stats import chi2_contingency

# Create table
table = pd.crosstab(df['High_Value_Customer'], df['Delivery_Status'])

# Perform test
chi2, p, dof, expected = chi2_contingency(table)

print("Chi-Square:", chi2)
print("P-Value:", p)
