```python
#https://datavizpyr.com/add-regression-line-per-group-with-seaborn-in-python/
```


```python
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
```


```python
penguins_data="https://raw.githubusercontent.com/datavizpyr/data/master/palmer_penguin_species.tsv"
```


```python
penguins_df = pd.read_csv(penguins_data, sep="\t")
penguins_df.head()
```


```python
# add regression line with lmplot()
sns.lmplot(x="culmen_length_mm", 
           y="flipper_length_mm", 
           data=penguins_df,
           height=10)
plt.xlabel("Culmen Length (mm)")
plt.ylabel("Flipper Length (mm)")
plt.savefig("How_To_Add_Regression_Line_in_Seaborn_with_lmplot.png",
                    format='png',dpi=150)
```


```python
# add regression line with regplot()
plt.figure(figsize=(10,8))
sns.regplot(x="culmen_length_mm", 
           y="flipper_length_mm", 
           data=penguins_df)
plt.xlabel("Culmen Length (mm)")
plt.ylabel("Flipper Length (mm)")
plt.savefig("How_To_Add_Regression_Line_in_Seaborn_with_regplot.png",
                    format='png',dpi=150)
```


```python
# add regression line per group Seaborn
sns.lmplot(x="culmen_length_mm", 
           y="flipper_length_mm", 
           hue="species",
           data=penguins_df,
           height=10)
plt.xlabel("Culmen Length (mm)")
plt.ylabel("Flipper Length (mm)")
plt.savefig("How_To_Add_Regression_Line_per_group_Seaborn.png",
                    format='png',dpi=150)
```
