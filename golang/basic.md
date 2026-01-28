--Basic -- 
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
   ## init and main function Role 
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
