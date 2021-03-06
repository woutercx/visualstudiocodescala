# visualstudiocodescala
Make it possible to execute a simple helloworld.scala program in Visual Studio Code on a Mac.

**1. Install Scala with a Package Manager, for example with brew:**

```bash
    brew update
    brew install scala
    brew install sbt
```
    
**2. Create a helloworld.scala program:**

```scala
object HelloWorld 
{	
	def main(args: Array[String]) 
	{
		println("Hello, world!")
	}
}
```

**3. Create a tasks.json file under the .vscode directory:**

```js
// Available variables which can be used inside of strings.
// ${workspaceRoot}: the root folder of the team
// ${file}: the current opened file
// ${fileBasename}: the current opened file's basename
// ${fileDirname}: the current opened file's dirname
// ${fileExtname}: the current opened file's extension
// ${cwd}: the current working directory of the spawned process

// A task runner that calls the Scala compiler and
// runs a HelloWorld.scala program
{
	"version": "0.1.0",

	// The command is scala.
	"command": "scala",

	// The command is a shell script
	"isShellCommand": true,

	// Show the output window always.
	"showOutput": "always",

	// args is the file currently being edited.
	"args": ["${file}"],

	// use the standard problem matcher to find compile problems
	// in the output. Didn't know what to fill in here since there is no
	// problem matcher for Scala yet.
	"problemMatcher": "$msCompile"
}
```

**4. Run the Scala program by pressing ⌘-P and typing**

```bash
    task scala
```

and hitting [ENTER]