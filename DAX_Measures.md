# DAX Measures

```DAX
Total Employees =
COUNTROWS(HR_Employee_Data)

Active Employees =
CALCULATE(
    [Total Employees],
    HR_Employee_Data[Attrition] = "No"
)

Attrition Count =
CALCULATE(
    [Total Employees],
    HR_Employee_Data[Attrition] = "Yes"
)

Attrition Rate =
DIVIDE(
    [Attrition Count],
    [Total Employees],
    0
)

Average Salary =
AVERAGE(HR_Employee_Data[MonthlyIncome])

Average Age =
AVERAGE(HR_Employee_Data[Age])
```

## Calculated Column

```DAX
AgeGroup =
SWITCH(
    TRUE(),
    HR_Employee_Data[Age] < 25, "Under 25",
    HR_Employee_Data[Age] <= 34, "25-34",
    HR_Employee_Data[Age] <= 44, "35-44",
    "45+"
)
```
