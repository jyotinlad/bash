# Bash
An overview of Bash and training materials from courses.

## Shortcuts
* Arg List: `$*`
* Arg Array: `$@`
* Counter: `$#`
* Reuse Last Command: `!$`
  * `mkdir mydir`
  * `cd !$`

## Variables
* Set: `$MYVAR=value` - good practice to uppercase them
* Local: `local $MYVAR=value`
* Read Only: `readonly $MYVAR=value`
* Reuse: `export $MYVAR=value` - in another process
* Unset: `unset $MYVAR`
* Environment: `env`
* List: `declare`
* List Integers: `declare -i`
* List Arrays: `declare -a`

## Print
* Variable: `echo $MYVAR` or `echo ${MYVAR}` - latter is better practice
* Array Variable: `echo ${MYVAR[n]}`
* Subsitution: `echo "server: ${hostname}"`

## Process ID
Using variable `$PPID`.

## Glob
This is different to regex expressions.
* Expansion: `*`
* Filter Characters:
  * `[12]`
  * `[0-9]`
  * `[A-Z]`
* Any Character: `?`
* Dot Files/Folders - are hidden
  * `.file.txt`
  * `.dir`

## Output File
* Create: `echo "hello world" > output_file.txt` - using `>` character
* Append: `echo "hello world" >> output_file.txt` - using `>>` character

## File Contents
* All: `cat output_file.txt`
* Pagination: `less output_file.txt`

## Pipe Command
Redirects output to the next command.

`cat output_file.txt | grep -f "text"`

## File Descriptors
* `0` = Standard Input
* `1` = Standard Output (redirecting output using `1>`)
* `2` = Standard Error (redirecting output using `2>` or to standard output `2>&1`)

## Operators
* And: `&&`
* Or: `||`

## If/Else
`if .. then .. else fi`

## Loops
* While: `while .. do {}`
* For (C Style): `for ((i=0, i<10, i++)) do .. done`
* For (Alternative): `for file in $((ls *)) do .. done`

## Switches
```
case $a in
1) echo "value is one"
2) echo "value is two"
esac
```

## Test
`[ 1 == 1 ]` or `[[ 1 == 1 ]]`

## Exit Codes:
* `0` = Okay
* `1` = Error
* `2` = Misuse

## Pattern Matching
* Left to Right
  * Shortest: `#*/`
  * Longest: `##*/`
* Right to Left
  * Shortest: `%*/`
  * Longest: `%%*/`