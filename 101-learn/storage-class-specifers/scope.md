### Scope 
### What is Scope?

*Scope* describes the region or regions of a program that can access an identifier.

A C variable has one of the following scopes:

- block scope
- function scope
- function prototype scope
- file scope

A *block* is a region of code contained within an opening brace and the matching closing brace. 

##### Function Scope

The entire body of a function is a block. Any compound statement within a function also is a block. A varible defined inside a block has a *block scope*, and it is visible form the point it is defined until the end of the block containing the definition.

Formal function parameters, even though they occur before the opening brace of a function, have block scope and belong to the block contaning the function body. Therefore, the varibles **apple** and **quantity** in the following code both have block scope extending to the closing brace.

```c

double blocky(double apple)
{
    double quantity = 0.0;
    ...
    return quantity;
}
```


Variables declared in an inner block have scope restricted just to that block:

```c
double blocky(double apple)
{
    double quantity = 0.0;
    int i;

    for (i=0; i<10; i++)
    {
        double q = apple * i;       // start of scope for q
        ...
        quantity *= q;              // end of scope of q
    }
    ...
    return quantity;
}
```

In this example, the scope of **q** is limited to the inner block and only code within the block can access **q**.

*Function scope*  applies just to labels used with **goto** statements. This means that even if a lable first appears inside an inner block in a function, its scope extends to the whole function. It would be confusing 