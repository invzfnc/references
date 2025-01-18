**Variables**
```bash
foo=bar
echo $foo

foo = bar
# This does not work because
# space is a reserved character
# for separating program and arguments
# foo here is not a program
```

Output of command as variable
```bash
foo=$(pwd)
# Store output of pwd to foo

echo "We are in $(pwd)"
# Use output of command in string
```

Reserved variables
`$0` - Name of bash script/program  
`$1` - First argument  
`$?` - Error code from the previous command  
`$_` - Last argument from the previous command  
`!!` - "bang bang", Last command executed  
`true` - Equal to `0`  
`false` - Equal to `1`  
`$a` - All argv  

Example:
```bash
echo "Hello"
echo $?
# 0 because everything went fine

false
echo $?
# 1

# $_
mkdir test
cd $_

# !!
mkdir /mnt/new  # Permission denied
sudo !!         # == sudo mkdir /mnt/new 
```

**Strings**
```bash
echo "Value is $foo"
# Value is bar
echo 'Value is $foo'
# Value is $foo
```

**Functions**
```bash
func() {
	echo "Hello, world"
	echo "$1"  # argv[1]
}
```

**Script**
```bash
vim hello_world.sh
source hello_world.sh
```
Functions and variables defined in script will remain in shell environment after executing the script

`;` - Separator
```bash
mkdir $1; cd $_
```

**Conditionals**
Or
```bash
false || echo "Failed"
# Failed
# if first condition is false execute the right statement
true || echo "This will not be printed"
```

And
```bash
true && echo "This will be printed"
false && echo "This will not be printed"
```

---

Reference: https://missing.csail.mit.edu/2020/shell-tools/