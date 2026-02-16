# DATA-HANDLING-USING-DATA-FRAMES.PY

pip install pandas
import pandas as pd

df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'David'],
    'Age': [25, 32, 47],
    'City': ['NY', 'LA', 'NY'],
    'Salary': [70000, 90000, 120000]
})
print(df)

print(df.head(), df.shape)
print(df.sort_values('Age'))
print(df[df['Age'] > 30])
dept = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'David'],
    'Dept': ['HR', 'Eng', 'Eng']
})
merged = pd.merge(df, dept, on='Name')
print(merged)
print(df.groupby('City')['Salary'].mean())

Output:

    Name  Age City  Salary
0  Alice   25   NY   70000
1    Bob   32   LA   90000
2  David   47   NY  120000

    Name  Age City  Salary
0  Alice   25   NY   70000
1    Bob   32   LA   90000
2  David   47   NY  120000 (3, 4)

    Name  Age City  Salary
0  Alice   25   NY   70000
1    Bob   32   LA   90000
2  David   47   NY  120000

   Name  Age City  Salary
1    Bob   32   LA   90000
2  David   47   NY  120000

    Name  Age City  Salary Dept
0  Alice   25   NY   70000   HR
1    Bob   32   LA   90000  Eng
2  David   47   NY  120000  Eng

City
LA    90000.0
NY    95000.0
Name: Salary, dtype: float64
