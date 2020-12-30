# Bash

- [Shebang](#shebang)
- [Print](#print)
- [Input](#input)
- [Variables](#variables)
- [Control flow](#control-flow)

### Shebang

```bash
#!/bin/bash
```

### Print

```bash
echo $MY_VAR
```

### Input

```bash
echo -e "Please enter your name: "
read name
echo "Nice to meet you $name"
```

### Variables

```bash
my_variable=my_value
my_variable='hello world' # single quotes are not interpreted
my_variable="hello $name" # double quotes allow substitution
my_dir=/home/dev
variable=$( my_command ) # save output of command into a variable
timestamp=$(date +"%Y-%m-%d_%H:%M:%S")

$my_dir 
${my_dir} # variable expansion
${#my_string} # string length
${my_var=default_value}
${my_var1?my_var2} # use my_var2 if my_var1 is null

a{d,c,b}e # brace expansion: "ade ace abe"

# environment variable (export to all child processes created from that shell)
export my_var1="${my_var2}" 

# positional parameters
$0 # name of the script
$1 - $9 # first 9 arguments of the script
$# # number of arguments passed to the script
$? # the exit status of the most recently run process
$$ # the process ID of the current script
$USER # the username of the user running the script
$HOSTNAME # the hostname of the machine the script is running on
$SECONDS # the number of seconds since the script was started
$RANDOM # return a random number
$LINENO # returns the current line number in the script
```

### Control flow

```bash
# arithmetic operators inside [[ ]]: 
-eq, -ne, -lt, -gt, -le, -ge

# arithmetic operators inside (( )):
==, !=, <, >, <=, >=

# if-else
if (( $a < $b )); then
    # statement
elif (( $a == $b )); then
    # statement
else 
    # statement
    exit 0
fi


```
