1. Line 12 prints `3`, the loop runs with `i = 0, 1, 2` for the three elements in `prices`. Because `i` is declared with `var` with function scope, it is still accessible outside the `for` block and able to be printed.

2. Line 13 prints `150`.`discountedPrice` is declared with `var` inside the loop, so it is function-scoped and available outside the loop. After the last iteration, `discountedPrice` is `300 * (1 - 0.5) = 150`.

3. Line 14 prints `150`.`finalPrice` is declared with `var` at function scope and updated every loop iteration. On the last iteration it is set to `Math.round(150 * 100) / 100 = 150`.

4. The function returns `[50, 100, 150]`. Each item in `prices` gets multiplied by `(1 - 0.5) = 0.5` (`discount = 0.5`), giving `50`, `100`, and `150`. These values are pushed into `discounted` in that order and then gets returned.

5. The code will cause an error. `i` is declared with `let` in the `for` loop, so it is block-scoped and only exists inside the loop block. It cannot be accessed by line 12.

6. The code will cause an error. `discountedPrice` is declared with `let` inside the `for` loop block, so it is block-scoped and only exists inside the loop block. It cannot be accessed by line 13.

7. Line 14 prints `150`. `finalPrice` is declared with `let` but in the scope of the function `discountPrices`, so it is still accessible after the for loop. Its final value after processing `[100, 200, 300]` with `0.5` discount is `150`.

8. The function returns `[50, 100, 150]`. Each price is multiplied by `(1 - 0.5) = 0.5`, so the values added to `discounted` are `50`, `100`, and `150`. `discounted` was declared with `let` in the scope of the function so it is still accessible after the for loop.

9. The code will cause an error. `i` is declared with `let` in the `for` loop, so it is block-scoped and only exists inside the loop block. It cannot be accessed by line 11.

10. Line 12 prints `3`. `length` is declared with `const` in the scope of the function, so it is accessible at line 12. It is set to the value of `prices.length`, and since `prices` has three elements, `length` is `3`.

11. The function returns `[50, 100, 150]`. Each element in `[100, 200, 300]` is multiplied by `(1 - 0.5) = 0.5`, producing `50`, `100`, and `150`, which are pushed into `discounted` in that order.  Even though `discounted` is delcared `const`, it can still be mutated, so no error is thrown.

**Data Types**

12. 
A. `student.name`
B. `student['Grad Year']`
C. `student.greeting()`
D. `student['Favorite Teacher'].name`
E. `student.courseLoad[0]`

**Basic Operators & Type Conversion**

13. 
A. `'3' + 2` -> `'32'` , string concatenation because one operand is a string; safer than coercing `'3'` to number
B. `'3' - 2` -> `1` , subtraction coerces `'3'` to number 
C. `3 + null` -> `3`, `null` coerces to `0` in numeric addition
D. `'3' + null` -> `'3null'`, string concatenation; `null` becomes `'null'`
E. `true + 3` -> `4`, `true` coerces to `1`
F. `false + null` -> `0`, `false` -> `0`, `null` -> `0`
G. `'3' + undefined` -> `'3undefined'`, string concatenation; `undefined` becomes `'undefined'`
H. `'3' - undefined` -> `NaN`, `undefined` coerces to `NaN` in numeric operation

14. 
A. `'2' > 1` -> `true`, '2'` coerces to number `2`
B. `'2' < '12'` -> `false`, string comparison is lexicographic, and `'2'` is greater than `'1'`
C. `2 == '2'` -> `true` , `==` does type coercion
D. `2 === '2'` -> `false`, `===` doesn't prompt coercsion; checks value and type; number and string are different
E. `true == 2` -> `false`,  `true` coerces to number `1`, and `1 == 2` is false
F. `true === Boolean(2)` -> `true` , Boolean(2)` is `true` because any non-zero number is true; same type and value

15. 
`==` compares values after possible type coercion, while `===` compares both value and type without coercion. 

**Functions**

17. The result is `[2, 4, 6]`.

`modifyArray` loops through `[1, 2, 3]` and calls `doSomething` on each value. Since `doSomething(num)` returns `num * 2`, the mapped values are `2`, `4`, and `6`, which get pushed into `newArr` and are returned.

**setInterval(), setTimeout(), clearTimeout()**

19. The output order is:
`1`
`4`
`3`
`2`

`1` and `4` run immediately. The callback with delay `0` for `3` runs next after the call stack clears. The callback with delay `1000` for `2` runs last, about one second later.