# Sublime-lime-project
Project completed on Codecademy through their Data Science certificaiton program. This allows me to view one of Codecademy's libraries and plot how many page visits and lime sales were had over a montly trend.


import pandas as pd
from matplotlib import pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]

visits_per_month = [9695, 7909, 10831, 12942, 12495, 16794, 14161, 12762, 12777, 12439, 10309, 8724]

# numbers of limes of different species sold each month

key_limes_per_month = [92.0, 109.0, 124.0, 70.0, 101.0, 79.0, 106.0, 101.0, 103.0, 90.0, 102.0, 106.0]

persian_limes_per_month = [67.0, 51.0, 57.0, 54.0, 83.0, 90.0, 52.0, 63.0, 51.0, 44.0, 64.0, 78.0]

blood_limes_per_month = [75.0, 75.0, 76.0, 71.0, 74.0, 77.0, 69.0, 80.0, 63.0, 69.0, 73.0, 82.0]

fig, (ax1, ax2) = plt.subplots(1 ,2, figsize=(12,8))
 
x_values = range(len(months))

# Left Chart Total Page visits per month

ax1.plot(x_values, visits_per_month, marker='o', color='blue')

ax1.set_title('Monthly Visits')

ax1.set_xlabel('Months')

ax1.set_ylabel('Visits Per Month')

ax1.set_xticks(x_values)

ax1.set_xticklabels(months)

# Right chart: lime sales

ax2.plot(x_values, key_limes_per_month, label="Key Limes", marker='o', color='green')

ax2.plot(x_values, persian_limes_per_month, label="Persian Limes", marker='o', color='orange')

ax2.plot(x_values, blood_limes_per_month, label="Blood Limes", marker='o', color='red')

ax2.set_title("Monthly Lime Sales")

ax2.set_xlabel("Month")

ax2.set_ylabel("Limes Sold")

ax2.legend()

ax1.set_xticks(x_values)

ax1.set_xticklabels(months)

# Adjust layout

plt.tight_layout()

plt.savefig('sublime_limes_monthly_trends.png')

plt.show()
