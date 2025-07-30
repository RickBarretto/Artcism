# Rule Set from Exercism's Documentation

I've created this Rule Set based on [Exercism's Documentation for Runners Interface](https://exercism.org/docs/building/tooling/test-runners/interface).

This Rule Set help me to track requirements and make sure everything was right-ly done.

## Runner Rules

### Rule #1 - Output

The output must be `results.json`.

### Rule #2 - Default Top-Level attributes

- `version:` must be an `:integer` between 1, 2 and 3.
- `status:` should be `"pass"` by default and changed if something go wrong.
- `message:` should not exist, unless there is an `error`.
- `tests:` must be empty by default.

### Rule #3 - Status attribute
- `status:` must be `pass`, `fail` or `error`

### Rule #4 - No Unitt file must be there
- `.unitt/` cache directory must no exist.

### Rule #5 - Runtime errors
- `status:` must be `error`
- `message:` must exist and display Arturo's output.

### Rules #6 - Tests at Runtime errors

Since Arturo won't get syntax errors before execute the code, but during its execution due to its own nature, I decided to break some rules.
So instead of `status:` be `error` only when no test run, this will be when Arturo's Interpreter fail.

- `tests:` must be empty when `status:` is `error`.


## API Rules

### Rule #7 - Name Attribute
- `name:` must be a human-readable `:string`

### Rule #8 - Test Code Attribute
- `test_code:` must be a `:string` with the code itself.

### Rule #9 - Status Attribute
- `status:` must be `pass`, `fail` or `error`
- must be `pass` by default
- must be `error` is test has uncaught exception
- must be `error` if this is empty or skipped
- must be `fail` is this fails

## Rule 10 - Output Attribute & Debugging

The API must provide a `debug` function
- This function must take any value, optionally a format string, write into `output:` and then return the value it back.

For instance:

```
test "Some test" [

    variable: debug.fmt: "Debug: |value|" expression
    ; => Debug: <value> :type

]
```

## Rule 11 - Output Truncate
`output:` must be truncated to 500 characters.


## Rule 12 - Message Attribute
Tests always must have `message:`.