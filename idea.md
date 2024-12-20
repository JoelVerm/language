# Ideas

## Steps

- Start with imports
- Then parse all types in the file
- Parse only names and arguments for let declarations
- Finally you can start parsing function chains

## Ideas

- `Option` and `Result` have to be defined in language itself
  - Could be union type with forced labelling:
    - `type Option A = None | Some A` where `None` and `Some` are labels
    - `type Result A B = Ok A | Err B` where `Ok` and `Err` are labels
    - Should be able to early return when expecting certain label
      - `let Some name = an_option` returns `an_option` from current context if it isn't `Some`
  - Function `or` required to be defined for both
- Pattern matching
  - Allow inline
- `==` means same value, not same instance
- Great error messages
- Currying any of the parameters
- Type inference
  - If a function is used, the type must allow the function to be used
    - Example: if all numbers define `f`, and `f x` is called, `x` must be a number
- Ranges `[1..20]`
- List spread `..[1, 2, 3]`
- All functions infix by default
  - Add `!` to the end to make it prefix, eg `my_func! a b c` instead of `a my_func b c`
- Easy concurrency
  - Some way of communicating??
- Tuple destructuring
- Test blocks (also ran at compile) `test "name" { code }`
  - `mock name =` in test block can override previous definitions for mocking
- Write tests in doc comments (required)
- Import from url -> don't need package registry
- String interpolation `"{some_value}"` value with `Display` trait
- Explicit `export` or `pub`
- Typeclasses / go-like interfaces / traits (without impl block)
- Don't allow unqualified imports (`module.function` instead of `function`)
- Labelled constructing and destructuring
- Shadowing immutable assignments
- `todo` keyword
- Super good StdLib
- Auto constructors
- Auto derive

- Test blocks support Tiger-Style Deterministic Simulation Testing (DST)
  - Inside test block `seed` is a random int
  - Run tests with `language file.lang --test 300` to get 300 random tests
  - Compile error if some asserts in code aren't called in any test block
- Number overflow and underflow trips asserts
- Asserts also run in production functions
  - Stop complete program if assert fails
    - Print what and why but also complete stack, functions and values (using default type formatting because program is gone)

- Import from C and maybe Rust?
- `use <-` from Gleam? Could be useful for async I/O
- Custom iterators not necessarily based on lists
- Built-in code formatter
- Tail call optimization
