# 🖥️ Bash Scripting Guide

## 🇬🇧 English

### 🚀 Introduction to Bash Scripting
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
Variables allow you to store and manipulate data. Here’s an example:

```bash
#!/bin/bash
name="Arthur"
echo 'Hello world, ' $name
whoami
id
```

### 🔧 Parameters
You can pass parameters to a script. The first parameter is accessed using `$1`:

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

**Output**:
```
Hello world, Arthur
I’m a param: param
artfrc
uid=1000(artfrc) gid=1000(artfrc) groups=1000(artfrc),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),100(users),101(netdev),116(bluetooth),121(lpadmin),124(wireshark),129(scanner),134(kaboxer)
```

For interactive input, use the `read` command:

```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Hello world, ' $name
echo 'I’m a param:' $param
echo "I’m a second param:"
read param
whoami
id
```

- **Number of arguments**: Use `$#` to get the number of arguments supplied.
- **Script filename**: Use `$0` to get the name of the current script.

### 📚 Arrays
Arrays allow you to store multiple values. Here’s an example:

```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Hello world, ' $name
echo 'I’m a param:' $param
echo "I’m a second param:"
read param
array=('obj1' 'obj2')
echo ">>>>>>>>>>>" ${array[0]}
unset array[0]
echo ">>>>>>>>>>>" ${array[0]}
array[0]='obj0'
echo ">>>>>>>>>>>" ${array[0]}
whoami
id
```

### ⚖️ Conditionals
Conditionals allow you to make decisions in your script. Example:

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

---

## 🇧🇷 Português

### 🚀 Introdução ao Bash Scripting
Um script bash sempre começa com a seguinte linha de código no topo para indicar que é um script bash:

```bash
#!/bin/bash
```

Aqui está um exemplo simples:
```bash
#!/bin/bash
echo 'Olá, mundo.'
whoami
id
```

Para executar um script bash, você deve primeiro dar permissões de execução com:
```bash
chmod +x seu_arquivo.sh
```
Em seguida, execute-o com:
```bash
./seu_arquivo.sh
```

### 📌 Variáveis
Variáveis permitem armazenar e manipular dados. Exemplo:

```bash
#!/bin/bash
name="Arthur"
echo 'Olá, mundo, ' $name
whoami
id
```

### 🔧 Parâmetros
Você pode passar parâmetros para um script. O primeiro parâmetro é acessado com `$1`:

```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Olá, mundo, ' $name
echo 'Sou um parâmetro:' $param
whoami
id
```

Execute o script com um parâmetro:
```bash
bash ./script-bash.sh param
```

**Saída**:
```
Olá, mundo, Arthur
Sou um parâmetro: param
artfrc
uid=1000(artfrc) gid=1000(artfrc) groups=1000(artfrc),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),100(users),101(netdev),116(bluetooth),121(lpadmin),124(wireshark),129(scanner),134(kaboxer)
```

Para entrada interativa, use o comando `read`:

```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Olá, mundo, ' $name
echo 'Sou um parâmetro:' $param
echo "Sou um segundo parâmetro:"
read param
whoami
id
```

- **Número de argumentos**: Use `$#` para obter o número de argumentos fornecidos.
- **Nome do script**: Use `$0` para obter o nome do script atual.

### 📚 Arrays
Arrays permitem armazenar múltiplos valores. Exemplo:

```bash
#!/bin/bash
name="Arthur"
param=$1
echo 'Olá, mundo, ' $name
echo 'Sou um parâmetro:' $param
echo "Sou um segundo parâmetro:"
read param
array=('obj1' 'obj2')
echo ">>>>>>>>>>>" ${array[0]}
unset array[0]
echo ">>>>>>>>>>>" ${array[0]}
array[0]='obj0'
echo ">>>>>>>>>>>" ${array[0]}
whoami
id
```

### ⚖️ Condicionais
Condicionais permitem tomar decisões no script. Exemplo:

```bash
#!/bin/bash
name="Arthur"
if [ $name = "Arthur" ] && [ 1 -eq 1 ]
then
   echo "verdadeiro"
else
   echo "falso"
fi
```S

#### Operadores Comuns
| Operador | Descrição |
|----------|-----------|
| `-eq`    | Verifica se dois operandos são iguais; se sim, a condição é verdadeira. |
| `-ne`    | Verifica se dois operandos não são iguais; se sim, a condição é verdadeira. |
| `-gt`    | Verifica se o operando à esquerda é maior que o da direita; se sim, a condição é verdadeira. |
| `-lt`    | Verifica se o operando à esquerda é menor que o da direita; se sim, a condição é verdadeira. |
| `-ge`    | Verifica se o operando à esquerda é maior ou igual ao da direita; se sim, a condição é verdadeira. |