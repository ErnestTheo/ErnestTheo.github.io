# Projects
![line](Pictures/line.jpg)
[Home](README.md) | [Resume](resumes.md) | [Certificates](certificates.md) | [Projects](projects.md)
![line](Pictures/line.jpg)

## Excel Data Organizer with Python Pandas
```python
# Work in Progress
import pandas as pd

df = pd.read_csv("data.txt",error_bad_lines=False, sep ='\t', index_col = 0, encoding='cp1252')

length = len(df)



df = df.drop(df.columns[[8, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33]], axis=1)

a = df.iloc[:,0].max()
print(df.iloc[:,0])
sn = df.groupby('           Slice')


filename = 'report.xlsx'

writer = pd.ExcelWriter(filename, engine='xlsxwriter')

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
