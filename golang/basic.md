## what is GO? - Why Developers Choose Go?
     
Go (Golang) is a statically typed, compiled programming language designed by Google.
It is known for its simplicity, fast, and efficient, especially for building scalable backend systems.


Reasons for choosing Go:

1. Performance and Efficiency
Go is very fast because it runs directly on machine code. It can handle many requests at the same time without slowing down, which makes applications more responsive.

2. Cost Efficient
Go uses less memory and RAM, so applications need fewer servers. This helps companies reduce cloud and infrastructure costs, especially for high‑traffic systems.

3. Fast Development & Deployment
Go is easy to write and understand, and it compiles very quickly. It creates a single executable file, which makes deployment simple and reliable.

4. Strong Standard Library
Go comes with many built‑in features like HTTP servers, JSON handling, logging, and testing. This reduces the need for extra tools and saves development time.

5. Cloud & Microservices Friendly
Go is well suited for cloud applications and microservices. It scales easily, works well with Docker and Kubernetes, and is widely used in modern systems.

We chose Go because it is fast, cost‑effective, easy to develop and deploy, and works very well for cloud‑based microservices.




   
   ## How Run Go Code?
Running a Go application is simple because Go is a compiled language. When you build a Go program, it is compiled into a single static binary file. This means you do not need to install a Go runtime on the target machine — you only need the compiled file.

However, to compile Go code, you must install Go on your system (or download the Go compiler). You write your code in a file with the .go extension.

Every Go program starts from the main function. The main function is the entry point of the program, and execution always begins there.

To create an executable file, you use the go build command. By default, this command builds an executable for the current operating system and architecture.

If you want to build an executable for a different target system, you can specify the GOOS and GOARCH environment variables when running go build. This allows you to cross-compile for another operating system or CPU architecture.

Go also provides the go run command, which is used to quickly compile and run a Go program from the command line without creating a permanent executable file.

   
   ## init and main function Role 

main() :== The main() function is the entry point of the executable application, determining the program's primary logic and flow. 

init() :== In Go, the init() function is a special built‑in function that the Go runtime executes automatically once per package, before the main() function runs. It is commonly used for tasks such as initializing global variables, validating configuration, or setting up resources (for example, checking database connections).


   ## what is GOPATH | GOROOT
   ## Cli - go mod init | run | mod tidy | build | go install . 
   ## Go workspaces | How Create project workspaces
   ## mod and sum file
   ## Packages and module
   ## Exported and Unexported identifiers



go run main.go: This command directly executes your Go program. main.go refers to the name of your main Go file, which can be different.
go build: This command compiles your Go project and generates an executable file . The type of executable file depends on your operating system:
Mac: Generates a .DMG file .
Windows: Generates an .exe file .
Ubuntu: Generates a .deb file.
Note that an executable generated for one OS will only run on that OS . However, you can specify an environment to generate an executable for a different OS, even if you're on a different system.
go install: This command does the same as go build but also moves the generated executable file to your Go path variable, allowing you to run it from any directory.







Go is a statically typed language that requires setting up a workspace and compiling the code to run it .

Here are the common ways to run Go code:

Using the Command Line (Terminal/Command Prompt):

Install Go: Ensure Go is installed on your system.
Write Your Code: Create a .go file (e.g., main.go) with your Go program.
Navigate: Open your terminal and navigate to the directory where your .go file is located.
Run:
Use go run main.go to compile and execute the program immediately.
Use go build main.go to compile the code and create an executable file. You then run the executable directly.
Using an IDE (like VS Code):

Install Go Extension: Add the official Go extension for Visual Studio Code.
Open Your File: Open your Go project in VS Code.
Run: Use the Run and Debug view or search for "Go: Run" or "Go: Build" in the command palette.
