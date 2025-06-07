# 🖥️ Bash Scripting Guide

A bash script always starts with the following line of code at the top of the script to indicate it’s a bash script:

```bash
#!/bin/bash
```

Here’s a simple example:
```bash
#!/bin/bash
echo 'Hello world.'
whoami
id
```

To run a bash script, you must first give it executable permissions using:
```bash
chmod +x yourfile.sh
```
Then, execute it with:
```bash
./yourfile.sh
```

### 📌 Variables

```bash
#!/bin/bash
name="Arthur"
echo 'Hello world, ' $name
whoami
id
```

### 🔧 Parameters
```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Hello world, ' $name
echo 'I’m a param:' $param
whoami
id
```

Run the script with a parameter:
```bash
bash ./script-bash.sh param
```

#### For interactive input, use the `read` command:

```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Hello world, ' $name
read param
```

- **Number of arguments**: Use `$#` to get the number of arguments supplied.
- **Script filename**: Use `$0` to get the name of the current script.

### 📚 Arrays

```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Hello world, ' $name
array=('obj1' 'obj2')
echo ">>>>>>>>>>>" ${array[0]}
unset array[0]
echo ">>>>>>>>>>>" ${array[0]}
array[0]='obj0'
echo ">>>>>>>>>>>" ${array[0]}
```
### ⚖️ Conditionals

```bash
#!/bin/bash
name="Arthur"
if [ $name = "Arthur" ] && [ 1 -eq 1 ]
then
   echo "true"
else
   echo "false"
fi
```

#### Common Operators
| Operator | Description |
|----------|-------------|
| `-eq`    | Checks if two operands are equal; if yes, condition is true. |
| `-ne`    | Checks if two operands are not equal; if yes, condition is true. |
| `-gt`    | Checks if the left operand is greater than the right; if yes, condition is true. |
| `-lt`    | Checks if the left operand is less than the right; if yes, condition is true. |
| `-ge`    | Checks if the left operand is greater than or equal to the right; if yes, condition is true. |