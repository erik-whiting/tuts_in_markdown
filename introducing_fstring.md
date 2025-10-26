# String Interporlation in Python: The f-string

Frequently, you will need to insert the value of a variable into a string. The concept of doing this is called *string interpolation* and in Python it is accomplished with ***f-strings***. In this brief tutorial, you will learn the basic syntax of f-strings. Consider the following example of a basic savings calculator:

```py
money_saved_per_month = 10
months_gone_by = 6
total_saved = money_saved_per_month * months_gone_by
print(f"You have saved {total_saved} in {months_gone_by} months")
```

In the above code, the user's monthly savings is recorded in the variable `money_saved_per_month` and the number of months that have passed since the user started saving is recorded in the `months_gone_by` variable. The user's total savings is calculated by multiplying these two variables and assigning the value of the result to the `total_saved` variable. Finally, the script uses an f-string to print a message to the user.

In the above example, the f-string is this part:

```py
f"You have saved {total_saved} in {months_gone_by} months"
```

In Python, you indicate that a string is an f-string by prefixing it with the letter `f`, this is why you see an `f` outside of the first double-quotation mark.

The part that says `You have saved ` is just a string-literal. The next part, `{total_saved}`, is a variable you want inserted into the string.

When you use curly brackets inside an f-string, you're telling Python there is an *expression* inside these curly brackets, the result of which should be inserted here. So, if you ran the example script above, you would see the following:

```
You have saved 60 in 6 months
```

The `60` is the value of the `total_saved` variable (because 10 x 6 is 60) and the `6` is the value of the variable `months_gone_by`. Python took the values of the expressions inside the curly brackets of the f-string and replaced them with the value they evaluate to.

If we adjust the values of `money_saved_per_month` and `months_gone_by` and leave everything else alone, the script will correctly print the amount of money a user has saved. For example, if we changed `money_saved_per_month` to `20` and `months_gone_by` to `12`. The script would then print "You have saved 240 in 12 months" because even though the values of the variables changed, the expressions inside the f-string did not.

What is meant by an "expression" anyway? In Python, an expression is any combination of Python constructs that produce a single value. For example, `money_saved_per_month * months_gone_by` is an expression because it takes two values, multiplies them, and produces a single value.

Technically, just `months_gone_by` is an expression because it evaluates to a singe value (6 in the original example). In Python, f-strings can take any *expression* and still work--they don't just have to be variables you calculate beforehand. Consider this revised example:

```py
money_saved_per_month = 10
months_gone_by = 6
print(f"You have saved {money_saved_per_month * months_gone_by} in {months_gone_by} months")
```

In this example, you have replaced the `total_saved = money_saved_per_month * months_gone_by` statement and put the multiplcation expression directly inside the f-string. Running the script still results in the same output:

```
You have saved 60 in 6 months
```

Any valid Python expression can be inserted into an f-string and Python will return the string result of the expression at runtime.
