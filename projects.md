# Projects
![line](Pictures/line.jpg)
[Home](README.md) | [Resume](resumes.md) | [Certificates](certificates.md) | [Projects](projects.md)
![line](Pictures/line.jpg)

## Excel Data Organizer with Python Pandas
```python
import pandas as pd
import xlsxwriter
from openpyxl import load_workbook
from openpyxl.chart import (ScatterChart, Reference, Series)

df = pd.read_csv("data.txt",error_bad_lines=False, sep ='\t', encoding='cp1252')
df = df.drop(df.columns[[9, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34]], axis=1)

a = df.iloc[:,0].max()
sn = df.groupby(df.iloc[:,0])

filename = 'report.xlsx'

writer = pd.ExcelWriter(filename, engine='xlsxwriter')

for i in range(int(a)):
    sn.get_group(i+1).to_excel(writer, index=False, sheet_name='Slice ' + str(i+1))

writer.save()

wb = load_workbook(filename)

sheetlist = wb.sheetnames
for j in sheetlist:
    ws = wb[j]
    len = ws.max_row
    chart = ScatterChart()
    chart.title = "title"
    chart.style = 2
    chart.x_axis.title = 'x'
    chart.y_axis.title = 'y'

    xvalues = Reference(ws, min_col=3, min_row=2, max_row=len)
    for i in (9, 10):
        values = Reference(ws, min_col=i, min_row=1, max_row=len)
        series = Series(values, xvalues, title_from_data=True)
        chart.series.append(series)

    ws.add_chart(chart, "k2")



wb.save('report.xlsx')
```
Takes a txt file containing data, organizes data based on index value, and createschart for each sheet
## Anti-Theft Tag
![Gif](Pictures\tag\tag.gif)
![big](Pictures\tag\big.JPG)
![flat](Pictures\tag\flat.jpg)

## Spartan Superway
![b1](Pictures\ss\b1.png)
![b2](Pictures\ss\b2.png)
![b3](Pictures\ss\b3.png)
