## Back & Forth

When *Engine* see the program ```var a = 2;```

*Engine* sees two distinct statements, one which *Compiler* will handle during compilation, and one which *Engine* will handle during execution.

*Compiler* will proceed:

* Encountering ```var a```, *Compiler* asks *Scope* to see if a variable ```a``` already exists for that particular scope collection. If so, *Compiler* ignores this declaration and moves on. Otherwise, *Compiler* asks *Scope* to declare a new variable called ```a``` for that scope collection.

* *Compiler* then produces code for *Engine* to later execute, to handle the ```a = 2``` assignment. The code *Engine* runs will first ask *Scope* if there is a variable called a accessible in the current scope collection. If so, *Engine* uses that variable. If not, *Engine* looks elsewhere (see nested *Scope* section below)

To summarize: two distinct actions are taken for a variable assignment: First, *Compiler* declares a variable (if not previously declared in the current scope), and second, when executing, *Engine* looks up the variable in *Scope* and assigns to it, if found.

## Compiler Speak

The type of look-up *Engine* performs affects the outcome of the look-up.

"Left-hand Side" and "Right-hand Side". 

an LHS look-up is done when a variable appears on the left-hand side of an assignment operation, and an RHS look-up is done when a variable appears on the right-hand side of an assignment operation.

# Lexical Scope

## Look-ups

**Scope look-up stops once it finds the first match**

**Note**: Global variables are also automatically properties of the global object (window in browsers, etc.), so it is possible to reference a global variable not directly by its lexical name, but instead indirectly as a property reference of the global object