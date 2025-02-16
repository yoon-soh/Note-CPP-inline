# inline (C++)
## 1. Explanation

>makes a function inline. Whole code of the inline function gets inserted or substituted at the point of the inline function call. This eliminates function call overhead.

<details>
<summary>Reference</summary>

- ["instead of executing the function call CPU instruction to transfer control to the function body, a copy of the function body is executed without generating the call."](https://en.cppreference.com/w/cpp/language/inline)
- ["substitute the code within the function definition in place of each call to that function."](https://learn.microsoft.com/en-us/cpp/cpp/inline-functions-cpp?view=msvc-170)
- ["whole code of the inline function gets inserted or substituted at the point of the inline function call."](https://www.geeksforgeeks.org/inline-functions-cpp/)
</details>

## 2. Advantage

>eliminates function call overhead.

<details>
<summary>Reference</summary>

- ["This avoids overhead created by the function call"](https://en.cppreference.com/w/cpp/language/inline)
- ["In theory, using inline functions can make your program faster because they eliminate the overhead associated with function calls."](https://learn.microsoft.com/en-us/cpp/cpp/inline-functions-cpp?view=msvc-170)
- ["Function call overhead doesn’t occur."](https://www.geeksforgeeks.org/inline-functions-cpp/)
</details>

## 3. Restriction

>The definition of an inline function must be in the same translation unit. In other words, any inline function must be defined in header.

ex1)
```
// header.h

class S
{
public:
    inline int square(int s) // redundant use of inline
    {
        // this function is automatically inline
        // function body
    }
};
```
ex2)
```
// header.h

class S
{
public:
    int square(int s); // declare the function
};

inline int S::square(int s) // use inline prefix
{
}
```

<details>
<summary>Reference</summary>

- ["The definition of an inline function or variable(since C++17) must be reachable in the translation unit where it is accessed (not necessarily before the point of access)."](https://en.cppreference.com/w/cpp/language/inline)
- ["A given inline member function must be declared the same way in every compilation unit. There must be exactly one definition of an inline function."](https://learn.microsoft.com/en-us/cpp/cpp/inline-functions-cpp?view=msvc-170)
</details>

## 4. Note

>inline keyword is suggestion. Therefore, compiler can ignore this suggestion depending on the situation. (ex. inline function that is called recursively)

<details>
<summary>Reference</summary>

["The compiler treats the inline expansion options and keywords as suggestions. There's no guarantee that functions will be inlined. You can't force the compiler to inline a particular function, even with the __forceinline keyword."](https://learn.microsoft.com/en-us/cpp/cpp/inline-functions-cpp?view=msvc-170)
</details>
