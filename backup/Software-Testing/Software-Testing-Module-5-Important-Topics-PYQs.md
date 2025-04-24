# *Software-Testing-Module-5-Important-Topics-PYQs*

> [!question] For more notes visit 
> https://rtpnotes.vercel.app


## 1. Write the difference between Regression Testing and Orthogonal Array Testing.

## 2. What is Parameterized Unit testing.

## 3. State the advantages of Grey box testing

## 4. Explain the use of pattern testing

## 5. Symbolic execution is a midway of program proving and program testing. Justify.

## 6. Write the need for grey box testing and list the steps in grey box methodology. 

## 7.  Explain symbolic testing and symbolic execution tree

## 8. Why grey box testing is chosen and write  the methodology behind it.

## 9. Discuss any 2 techniques of grey box testing
## 10. Draw the symbolic execution tree for the following program code and execution of testme (α1,α2)

```c
int twice(int v) {
    return 2 * v;
}

void testme(int x, int y) {
    int z = twice(y);
    if (z == x) {
        if (x > y + 10) {
            ERROR;
        }
    }
}

int main() {
    int x = sym_input();
    int y = sym_input();
    testme(x, y);
    return 0;
}
```

## 11. Explain Matrix Testing and Regression Testing in detail

## 12. Outline the need for Grey Box Testing

## 13. Explain Orthogonal Array Testing and Pattern Testing in detail

## 14. Explain briefly about parameterized unit testing
## 15. What is parameterized unit testing? How Pex is useful in generating parameterized unit tests?

## 16. Discuss orthogonal array testing and explain how it reduces the number of test cases with a suitable example.

## 17. For the following program code, perform symbolic execution intExp(A,N). Draw symbolic execution tree and give any three concrete test cases.

```c
int intExp(int a, int n) {
    if (n < 0) {
        throw new ArithmeticException();
    } else {
        int out = 1;
        while (n > 0) {
            out = out * a;
            n--;
        }
        return out;
    }
}
```

## 18. Write a short note about regression testing