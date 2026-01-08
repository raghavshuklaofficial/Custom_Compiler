# 🎯 Custom Compiler

This repository contains a **custom-built compiler** developed in `C`, created as part of our **Project-Based Learning (PBL)** assignment for the *Compiler Design* course at **Graphic Era University** 🏫.

📄 The compiler follows the rules defined in the provided `Language_Specifications.pdf` and processes input source files accordingly. If the input passes **both syntax and semantic checks**, the compiler generates equivalent **assembly-level output** 🛠️.
👉 Sample input programs are available in the `Compiler/testcases/` folder.

> ✅ **Note:** The compiler is built for **GCC 5.4.0** and tested on **Ubuntu 16.04**.  
> 🪟 For Windows, install [Cygwin](https://www.cygwin.com/) to run the compiler.

---

## ⚙️ How to Build the Compiler

```bash
cd Compiler
make
```

✔️ This creates an executable named `compiler` in the same directory.

---

## 🚀 Running the Compiler with Testcases

```bash
./compiler <path-to-testcase-file> <output-asm-file-name>
```

📋 After running, a menu appears with 11 options.
🔢 Select the option to perform the task:

* Choose `10` to generate **assembly code**.
* Choose `0` to **exit** safely.
  *(Note: Ctrl + C may leave the `.asm` file empty)*

## 🧩 Menu Options – Custom Compiler

*Select an option when prompted in the terminal interface:*

| **Option** | **Action**                        | **Description**                                                                 |
|-----------:|-----------------------------------|---------------------------------------------------------------------------------|
| `0`        | ❌ **Exit**                        | Graceful shutdown *(⚠ Avoid Ctrl+C — it may leave `.asm` file empty)*          |
| `1`        | 📝 **Remove Comments**             | Displays source code with all comments stripped                                |
| `2`        | 🧾 **Print Token Stream**          | Shows all tokens recognized by the lexer                                       |
| `3`        | 📚 **Parse Source Code**           | Checks syntax using the parser                                                 |
| `4`        | 🌳 **Print Parse Tree**            | Displays the parse tree in in-order traversal                                  |
| `5`        | 📊 **Memory Stats**                | Compares memory usage of Parse Tree vs AST                                     |
| `6`        | 📋 **Print Symbol Table**          | Displays scopes, identifiers, and types                                        |
| `7`        | 🧠 **Activation Record Size**      | Prints the size of activation records per function                             |
| `8`        | 🧬 **Print AST**                   | Displays the Abstract Syntax Tree (AST)                                        |
| `9`        | ✅ **Semantic Checks**             | Performs type checking, identifier validation, etc.                            |
| `10`       | ⚙️ **Generate Assembly Code**      | Produces `.asm` file from AST                                                  |


🛠️ Example to compile and run the generated ASM:

```bash
nasm -felf64 code.asm
gcc code.o
./a.out
```

---

## 📁 **Project Structure**

```plaintext
Custom_Compiler/
├── Compiler/
│   ├── ast.c               # Implements AST traversal and utility functions
│   ├── ast.h               # Declarations for AST structures and functions
│   ├── astNode.c           # Defines various types of AST nodes
│   ├── astNode.h           # Header for AST node definitions
│   ├── codeGen.c           # Converts AST into target assembly instructions
│   ├── codeGen.h           # Header for code generation functions
│   ├── compiler.c          # Main entry point for invoking compilation phases
│   ├── driver.c            # CLI input handling, integrates different modules
│   ├── driver.h            # Header for driver module
│   ├── grammar.c           # Loads and processes grammar rules
│   ├── grammar.h           # Grammar rule structure definitions
│   ├── lexer.c             # Tokenization logic for source code
│   ├── lexerDef.h          # Definitions and enums for lexer tokens
│   ├── lexerFun.c          # Lexer helper functions
│   ├── parser.c            # Syntax analysis (parsing) logic
│   ├── parserDef.h         # Data structures used by the parser
│   ├── parserFun.c         # Parser utility and recursive functions
│   ├── semantic.c          # Semantic analysis and validation
│   ├── semanticDef.h       # Semantic analysis data structures
│   ├── semanticFun.c       # Helper functions for semantic checks
│   ├── stack.c             # Generic stack implementation
│   ├── stack.h             # Header for stack operations
│   ├── symbolTable.c       # Manages identifiers and their scopes/types
│   ├── symbolTable.h       # Symbol table structures and declarations
│   └── syntaxTree.c        # Builds syntax tree from tokens using grammar
├── Conventions.txt         # Guidelines on code styling and formatting
├── Language specifications.pdf  # Formal language grammar and rules
├── License                 # MIT License for open-source usage
└── README.md               # Project documentation and setup guide

```

## 🧩 Compiler Workflow (Option 10)

| 🔄 **Phase**         | 📝 **Description**                                                                |
| -------------------- | --------------------------------------------------------------------------------- |
| 🧊 Lexical Analysis  | Scans input and breaks it into tokens based on the defined rules.                 |
| 🧱 Syntax Analysis   | Builds a parse tree from tokens. Halts on any syntax errors.                      |
| 🧠 Semantic Analysis | Forms an Abstract Syntax Tree (AST) and builds a symbol table.                    |
| ⚙️ Code Generation   | Produces x86-64 assembly for valid programs. Supports only `main()` and integers. |

---
## 👨‍💻 **Author**

**Raghav Shukla**
📌 [GitHub Profile](https://github.com/raghavshuklaofficial)

---

## 📄 **License**

This project is licensed under the **MIT License**. See the [LICENSE](https://github.com/raghavshuklaofficial/Custom_Compiler/blob/main/License) file for details.

---
---

📌 *Academic project focused on compiler design using C — highlighting all major compilation phases from lexical to code generation.*
