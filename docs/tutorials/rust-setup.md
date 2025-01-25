# Setting up a dev container for Rust

* Primary author: [James McNeill](http://github.com/jamesbmc1)
* Reviewer: [Charles Wilt](https://github.com/crwilt)

## Prerequisites
Before moving on to the tutorial, make sure you have the following completed: 

1. **Git**: Install Git if you haven't already. 
2. **Visual Studio Code (VS Code)**: Download and Install [VSCode](https://code.visualstudio.com/) if necessary.
3. **Docker**: Necessary to run the dev container. 


## Part 1: Creating the Repository
### Step 1: Initializing Git and Creating a Local Repository
1. Open Terminal or Command Prompt
2. Create a new directory for your project
 ```bash
 mkdir rust-tutorial-comp423
 cd rust-tutorial-comp423
 ```
 3. Initialize a new git repository
```bash
git init
```

## Part 2: Setting Up the Development Environment
### Step 2: Add Development Container Configuration
1. Install the Dev Containers extension in VSCode.
2. In VSCode, open your rust-tutorial-comp423 directory. 
3. Create a .devcontainer directory in the root of your project. 
4. Add the following file to the "hidden" configuration directory: 
```bash
.devcontainer/devcontainer.json
```
5. Add the following information to the devcontainer.json : 

```bash
{
    "name": "Rust Development Environment",
    "image": "mcr.microsoft.com/devcontainers/rust:latest",
    "customizations": {
        "vscode": {
            "extensions": [
                "rust-lang.rust-analyzer"
            ]
        }
    }
}
```
!!! Tip "Make Sure You Save `devcontainer/devcontainer.json` before launching dev conatiner"


**"name":** This is the name for your dev container.

**"image":** The docker image to use, which is the latest version of Rust.

**"customizations":** A list of VSCode extensions. In this case, it is the rust-analzayer.


## Part 3: Opening Dev Container and Verifying Installation
### Step 3: Opening Dev Container
Open the project in the container by pressing `Ctrl+Shift+P` (or `Cmd+Shift+P on Mac`), typing "Dev Containers: Reopen in Container," 
and selecting the option. This may take a few minutes while the image is downloaded and the requirements are installed.

### Step 4: Check Installation
Once the Dev Container is running, open up a terminal (Terminal -> New Terminal). Run the following command: 
```bash
rustc --version
```

This displays the current version of Rust that you have, confirming that you have properly installed it!

## Part 4: Creating a New Rust Project and Creating/Running a Program
### Part 5: Creating a new Rust Project
Use Cargo to create a new project:
```bash
cargo new --vcs none hello_comp423
cd hello_comp423
```
The **--vcs none** flag makes it to where Cargo does not create a new git repository

### Part 6: Writing the "Hello COMP423" Program
1. Open the main file in the src folder ('src/main')
2. Replace the contents of **main** with the following: 
```bash
fn main() {
    println!("Hello COMP423");
}
```
### Part 7: Building and Running the Program
Use the following command to compile the program: 
```bash
cargo build
```
<!-- is there a way to print Hello 423 by using build -->

This compiles your code and creates the folder **target\debug** and creates an executable. This is similar to GCC in 211 as you compile first and then run the executable file. 


You could also use the following command to **run** the program: 
```bash
cargo run
```

!!! note "Distinction"
    **cargo run** can be used to build and compile the program at the same time instead of doing two separate steps. 

Your Program should output "Hello COMP423" in the terminal. This means that you have properly installed and made a Rust function!

### **Citation:**

**Title:**  Starting a Static Website Project with MkDocs

**Author:** Kris Jordan

**Link:** https://comp423-25s.github.io/resources/MkDocs/tutorial/