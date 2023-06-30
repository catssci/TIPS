## basic ast example

```python
import ast

# Define a Python code snippet as a string
code = """
def multiply(a, b):
    return a * b

result = multiply(3, 5)
print(result)
"""

# Parse the code string into an AST (Abstract Syntax Tree)
tree = ast.parse(code)

# Execute the code and capture the variables
exec(compile(tree, filename='<ast>', mode='exec'), globals(), locals())

# Traverse the AST to extract information
for node in ast.walk(tree):
    if isinstance(node, ast.FunctionDef):
        print("Function definition:", node.name)
    elif isinstance(node, ast.Call) and isinstance(node.func, ast.Name) and node.func.id == "print":
        print("Print statement with arguments:", node.args)
        for arg in node.args:
            if isinstance(arg, ast.Name):
                print("Execution result:", locals()[arg.id])
```

```
15
Function definition: multiply
Print statement with arguments: [<_ast.Name object at 0x7f282c8bd650>]
Execution result: 15
```

## string to list

```python
ast.literal_eval('[123123, 543534, 12313, 54353, 5464]')

```

```markdown
'[123123, 543534, 12313, 54353, 5464]' -> [123123, 543534, 12313, 54353, 5464]
```
