# Projects
![line](Pictures/line.jpg)
[Home](README.md) | [Resume](resumes.md) | [Certificates](certificates.md) | [Projects](projects.md)
![line](Pictures/line.jpg)

## Excel Data Organizer with Python Pandas
```python
# Work in Progress
import pandas as pd
import matplotlib.pyplot as plt


df = pd.read_csv("xyz.txt",sep="\t",error_bad_lines=False, index_col=0, encoding='cp1252',)
df.to_csv('newcsv.csv')
a = df.iloc[:,0].max()
print(df)
sn = df.groupby('           Slice')


writer = pd.ExcelWriter('Mag.xlsx', engine='xlsxwriter')

for i in range(int(a)):
    sn.get_group(i+1).to_excel(writer, index=False, sheet_name='Slice ' + str(i+1))

writer.save()
```
## Anti-Theft Tag
![Gif](Pictures\tag\tag.gif)
![big](Pictures\tag\big.JPG)
![flat](Pictures\tag\flat.jpg)

## Spartan Superway
![b1](Pictures\ss\b1.png)
![b2](Pictures\ss\b2.png)
![b3](Pictures\ss\b3.png)
