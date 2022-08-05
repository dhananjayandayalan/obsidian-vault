# Javascript Engine

1. There're multiple javascript engine like V8, Spidermonkey etc. 
2. Javascript Engine is just a compiler which compiles javascript code to run on the browser (basically it's a browser's compiler).
3. Compiles any javascript code to the browser understandable code. Compatibilities may vary according to the browser's engine.

![[Screenshot (7).png]]

## Parser 
- Performs Lexical Analysis -> Breaks code to Tokens (Tokens: meaningful to the compiler).

## Abstract Syntax Tree 
- After parsing the code to tokens -> Forms a tree like structure. (Ref. https://astexplorer.net)
- Example
```js
	function foo(x) {
		if (x > 10) {
			var a = 2;
			return a * x;
		}
		return x + 10;
	}
```

- The AST will look like this

![[Screenshot (7) 1.png]]

- The Pictorial Representation
![](https://miro.medium.com/max/1050/0*mSOIiWpkctkD0Gfg.)

- It breaks every part of the code, which may look like a flowchart.


### We can use both *Interpreter and Compiler* in Javascript
## Interpreter
- Transcripts the code line by line
- It's quick at running, executes in single step.
- But, if you run a piece of code multiple times, it'll be slow (because of translating a single piece of code multiple times).
## Profiler
- Optimizes the code like, the types were used, no. of times running, possiilites of optimization etc. 
## Compiler
- Multiple Passes to segregates the type of code we've written
![[Pasted image 20220805064631.png]]
- Compiler simplifies the code, won't repeat the translation like interpreter (called optimization).

## Optimized Code

### Javascript uses both compiler and interpreter in their engine, called as JIT (Just In Time) Compiler (It's for V8 Engine, it may vary amongst various engines)
- Interpreter in V8 engine is called ***Ignition***, takes ASD and converts into bytecode. Bytecode is just a prelevel code to the machine level code. 
- Then it sends to profiler (in V8 it's called as monitor), in which it sends to compiler (it's Turbofan), which translates the code which runs multiple times (like loop, event loop etc.,).
- It optimize the process and runs the code fastly.

# ECMAScript
- Standardization to create the js engine which works universally, (it's entirely upto the developers how they're gonna fullfil the requirements).



