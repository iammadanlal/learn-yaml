# Learn YAML

### What is YAML?
YAML is a human readable data serialization language, just like XML and JSON. it used for write configuration files and in application where data is being stored or transmitted.

It stand for YAML Ain't Markup Language but it is originally known as Yet Another Markup Language.

YAML is an official strict superset of JSON. Although it look very different from JSON.

YAML can do everything that JSON can and more. A valid YAML file can contain JSON, and JSON can transform into YAML.

YAML uses indentation to define structure in the file like Python.

```yml
Employees:
- name: Madan Lal
  department: Engineering
  country: India
- name: Shivam Mishra
  department: Engineering
  country: India
```
<br>

# Features and Basic Rules

### How to Create a YAML File?
To create a YAML file, use either `.yaml` or `.yml` file extension.

### Multi-Document Support
YAML allows you to have multiple document in a single YAML file which makes file organization easier.

To create multiple documents, you have to separate each document with three dashes (`---`):-

```yml
---
Employees:
- name: Madan Lal
  department: Engineering
  country: India
- name: Shivam Mishra
  department: Engineering
  country: India
---
Fruit:
 - Banana
 - Apples
 - Oranges
```

You can also use three dots (`...`) to show the end of document:-

```yml
---
Fruit:
 - Banana
 - Apples
 - Oranges
...
```

### Indentation in YAML

In YAML, indentation and line separation is very important because it define the levels and structure in data.

YAML doesn't use symbols such as curly braces, square brackets, or opening  or closing tags but you can write json which has curly braces, square brackets.

### Tabs in YAML

YAML doesn't allow you to use any tabs when creating indentation but modern code editors and autocomplete feature doesn't make you feel like that. It uses spaces instead.

### Whitespace in YAML

Whitespace doesn't matter if child elements are indented inside parent element.

### Comment in YAML

use `#` character to comment out a line of code

```yml
---
# Employees in organization
- name: Ramesh Kumar
  age: 27
- name: Jivan Raj
  age: 26
```

### Explicit Data Types in YAML

YAML auto-detects the data types in file.

To explicitly specify the type of data, use `!!` symbol and name of the data type before value:-

```yml
# parse this value as a integer (it will be 1 instead of 1.0)
likes: !!integer 1.0

# parse this value as a float (it will be 5.0 instead of 5)
rating: !!float 5

# parse this value as a string
phoneNumber: !!str 1234567890
```
<br>

# YAML Syntax

### Scalers

Scalers in YAML represent data on the page like strings, numbers booleans and nulls.

#### Strings

Strings can be written with single (`''`) or double (`""`) quotes or can be left unquoted.

```yml
Hello World
'Hello World'
"Hello World"
```

Using pipe symbol (`|`), you can write string in multiple lines and preserve its line breaks like `<pre>` tag in HTML:-

```yml
|
 A B C D E
 F G H I J
 K L M N O
 P Q R S T
 U V W X Y
 Z
```

<b>Note:</b> Notice, there is slightly indented the string in respect to pipe symbol (`|`)

Using `>` Character, you can write string multiple line but parser will interpret it as single line. It is actually replace each line break with a space:-

```yml
>
 Hello,
 myself Madan Lal,
 live in beautiful country India.
```

<b>Note:</b> Indentation is important.

#### Numbers

In YAML, numerical data include integers (whole numbers), floats (numbers with a decimal point), exponentials, octals and hexadecimals:

```yml
# integer
123

# float
4.5

# exponential
2.4e+02

# octal
0o32

# hexadecimal (0123456789ABCDEF)
0xBF
```

#### Booleans

In YAML, these are same as other programming language and represented as either `true` or `false`.

`true` and `false` are keywords in YAML. Use quotation marks if you want them interpreted as strings.

#### Null

Null values are represented with keyword `null` or the tilde `~` character.

### Collections

Collections in YAML can be:

- Sequences (list/arrays)
- Mappings (dictionaries/hashes)

1.) To write a sequence, use a dash (`-`) followed by a space:

```yml
- Mother
- Father
- Son
- Daughter
```

Each item in the sequence (list) is placed on a separate line, with a dash in front of the value. And each item in the list is on the same level. This is an example of simple 

Let's see how nested sequence will look like:-

```yml
- Mother
- Father
 - Son
 - Daughter
```

2.) Mappings allow you to list keys with values. Key/value pairs are the building blocks of YAML documents.

Use a colon (`:`) followed by a space to create key/value pairs:-

```yml
Students:
 name: Manoj Kumar
 age: 21
```

