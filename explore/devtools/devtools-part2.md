1. The bug was that `num1` and `num2` come from input fields as strings. In `calculateSum(num1, num2)`, using `num1 + num2` caused string concatenation (for example, `"2" + "3" = "23"`) instead of numeric addition.

2. Convert the inputs to numbers before adding:

`let result = Number(num1) + Number(num2);`

