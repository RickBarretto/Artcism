# Rule Set from Exercism's Documentation

I've created this Rule Set based on [Exercism's Documentation for Runners Interface](https://exercism.org/docs/building/tooling/test-runners/interface).

This Rule Set help me to track requirements and make sure everything was right-ly done.

## Rule #1 - Output

The output must be `results.json`.

## Rule #2 - Default Top-Level attributes

- `version:` must be an `:integer` between 1, 2 and 3.
- `status:` should be `"pass"` by default and changed if something go wrong.
- `message:` should not exist, unless there is an `error`.
- `tests:` must be empty by default.

## Rule #3 - Status attribute
- `status:` must be `pass`, `fail` or `error`

## Rule #4 - No Unitt file must be there
- `.unitt/` cache directory must no exist.

## Rule #5 - Runtime errors
- `status:` must be `error`
- `message:` must exist and display Arturo's output.

