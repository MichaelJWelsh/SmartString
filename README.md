# SmartString
A Lightweight C Library Meant To Mimic String Functionality In C++ 


## Ideology
The goal of this library is to provide string-like functionality similar to C++'s STL string class.  Every "smart" string worries about memory management and data organization for you, letting you better focus on your task ahead.  The "smart" string type is "s_str".  Every s_str function has the prefix "s_str\_" and takes in the memory address of the s_str that it will operate on as the first argument (with the exception of the *create* functions).  Every s_str that is created **must** be later destroyed with a call to *destroy*.


## API
The following is a list of available functions. Refer to the greatly commented header for details.
- create, create_from_char, create_from_multi_char, create_from_c_str, create_from_s_str
- destroy
- c_str
- c_substr
- assign_char, assign_multi_char, assign_c_str, assign_s_str
- at
- remove_at
- find_char, find_c_str, find_s_str
- rfind_char, rfind_c_str, rfind_s_str
- capacity
- reserve
- size
- length
- empty
- clear
- trim
- shrink_to_fit
- push_back
- pop_back
- append_c_str, append_s_str
- first_word
- remove_first_word
- last_word
- remove_last_word
- erase
- insert_char, insert_c_str, insert_s_str
- sepwith_char, sepwith_c_str, sepwith_s_str
- replace
- replace_all
- swap
- foreach
- foreach_all
- compare_c_str, compare_s_str
- sort


## Example
```
s_str foo = s_str_create_from_c_str("  wow ");

s_str_trim(&foo);
s_str_pop_back(&foo);

// Output: First print:wo.
printf("First print:%s.\n", s_str_c_str(&foo));

s_str_append_c_str(&foo, "bar");
s_str_insert_char(&foo, 2, ' ');

// Output: Second print:wo bar.
printf("Second print:%s.\n", s_str_c_str(&foo));

s_str_remove_first_word(&foo);
s_str_remove_at(&foo, 1); 

// Output: Third print:br.
printf("Third print:%s.\n", s_str_c_str(&foo));

s_str_destroy(&foo);

```
