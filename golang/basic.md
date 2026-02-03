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


   ## what is GOROOT | GOPATH 

--GOROOT 

GOROOT points to the Go installation directory.
This is where the Go compiler, standard library, and tools present.
need to set GOROOT manually. The Go installer sets it automatically.

--GOPATH 

GOPATH is Where Go code dependencies, downloaded third‑party packages, and compiled binaries are stored.
Before Go 1.11 version , all Go projects have to required to reside the $GOPATH/src directory.

after introduced of stable production ready "'Go Modules'" on Go 1.16 version. GOPATH mode was effectively disabled by default. As a result, developers no longer need to place projects inside GOPATH, and Go projects can now live anywhere on the filesystem.  

However, GOPATH is still used internally by Go for purposes such as the module cache and installed binaries.

   ## Packages || Go Modules || Go workspaces 
   
   --Go Packages
   
  A package is a collection of one or more Go source files (.go files) located in the same directory that are compiled together and share the same package name. 
  
  Every Go source file must declare its package name at the very top of the file using a package declaration. 
  
  Packages is fundamental unit for organizing and reusing code in Go, enabling related source files to be grouped logically while helping structure programs, control visibility, and promote modular, maintainable code.
   
   --Go Modules 
   Go Modules are the official dependency management system for Go projects. They were introduced in Go 1.11 and became the default behavior starting with Go 1.16. Go Modules allow projects to be developed and maintained outside of GOPATH, enabling better version control, dependency management, and reproducible builds.

go mod init :
To create a Go module, the go mod init command is used in the root directory of a Go project. This command initializes the project as a module and prepares it for dependency tracking.

go.mod :
go mod init creates a go.mod file. This file defines the module’s import path, specifies the Go version the project supports, and lists all the direct dependencies required by the application.

go.sum :
Go Modules also use a go.sum file. This file is not a lock file, but a security file that stores cryptographic checksums for all direct and indirect dependencies used in the project. These checksums ensure the integrity and authenticity of downloaded modules by verifying that the dependencies have not been tampered with

go get :
The go get command is used to add, upgrade, or downgrade dependencies to a specific version. 

go mod tidy :
The go mod tidy command is used to maintain module files. It adds any missing dependencies, removes unused ones, and cleans up both the go.mod and go.sum files to keep the dependency list accurate and minimal.


   --Go workspaces
   
   
   ## Cli - go mod init | run | mod tidy | build | go install . 
   ## Go workspaces | How Create project workspaces
   ## mod and sum file
   ## Packages and module
   ## Exported and Unexported identifiers



