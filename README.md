# Implementing Lex/Yacc

This project implements a basic calculator language using Flex (Lexical Analyzer) and Yacc/Bison (Parser). The language supports basic arithmetic operations, variable assignments, and expressions. (Error handling and prompting in Spanish)

## Features

- Arithmetic operations (+, -, *, /)
- Variable assignments
- Number literals
- Expression evaluation
- Error handling for undefined variables and division by zero

## Project Structure

```
.
├── Dockerfile
├── buildLanguage.sh
├── files/
│   ├── simple_language.l  (Lexical rules)
│   └── simple_language.y  (Grammar rules)
└── grammar               (Grammar specification)
```

## Requirements

- Docker

## Building and Running

1. Build the Docker image and run the container:
```bash
docker build --rm . -t lab1-image && docker run --rm -ti -v "$(pwd)":/home lab1-image
```

2. Inside the container, build the calculator:
```bash
sh buildLanguage.sh
```

3. Run the calculator:
```bash
./calc
```

## Language Syntax

- Assign values to variables:
```
x = 42;
```

- Print expressions (using ':'):
```
x + 5:
```

- Combine operations:
```
y = 10;
x = 5;
x + y:
z = x * y;
z:
```

## Error Handling

The calculator handles several types of errors:
- Division by zero
- Undefined variables
- Invalid syntax

## Examples

```
x = 10;        # Assign 10 to x
y = 5;         # Assign 5 to y
x + y:         # Prints 15
x * y:         # Prints 50
z = x / y;     # Assigns 2 to z
z:             # Prints 2
```

## Notes

- All statements must end with a semicolon (;)
- Use colon (:) to print expression results
- Variables are automatically initialized to 0 if undefined

