# Shell Scripting

## Objective
This lab covers shell scripting, which is a powerful tool that provides automation for redundant and tedious tasks in a daily workflow. The lab introduces common control structures and various uses of shell scripts to perform tasks related to incident response.

## Skills Learned
- Determining the shell used in a Linux environment.
- Writing and running basic shell scripts.
- Using variables, if statements, case statements, and loops in shell scripts.
- Creating and using functions in shell scripts.
- Using shell scripts for incident response tasks.

## Tools Used
### Materials:
- A virtual machine with Linux (e.g., Ubuntu)
- Another virtual machine with Linux or Windows
- Connectivity between the two VMs

### Resources:
1. [Bash Reference Manual](https://tiswww.case.edu/php/chet/bash/bashref.html)
2. [Shell Scripting Crash Course](https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/)

## Steps

### Running Your First Shell Script:
1. **Determine the Shell:**
   - Use `echo $SHELL` or check `/etc/passwd` to find the shell used.
2. **Create a New Script:**
   - Open a text editor and add the following lines:
     ```bash
     #!/bin/bash
     # This is a comment in my first ever script
     echo “Excited to join the world of Shell Scripting!”
     ```
   - Save the file as `my_first_script`.
3. **Set Permissions:**
   - Use `chmod 755 my_first_script` to set permissions.
4. **Run the Script:**
   - Use `./my_first_script` to run the script.

### Executing Your Script Without Specifying the Directory:
1. **Create a Subdirectory for Scripts:**
   - Create a subdirectory (e.g., `bin`) under your home directory and move `my_first_script` into it.
2. **Update PATH:**
   - Use `echo $PATH` to see current paths.
   - Add the script directory to PATH using `export PATH=$PATH:/full_path_to_your_subdirectory`.

### Using Variables:
1. **Create a Script with Variables:**
   - Example script:
     ```bash
     #!/bin/bash
     # A script to experiment with variables
     name=Steve
     department=Finance
     echo "The new employee is $name and his/her department is $department"
     ```

### IF Statements:
1. **Create a Script with IF Statements:**
   - Example script:
     ```bash
     #!/bin/bash
     # Testing IF statement
     num=1
     if [[ $num == 1 ]]; then
       echo "One"
     elif [[ $num == 2 ]]; then
       echo "Two"
     else
       echo "Undefined Value!"
     fi
     ```

### Case Statement:
1. **Create a Script with Case Statements:**
   - Example script:
     ```bash
     #!/bin/bash
     # Testing Case statement
     val=1
     case $val in
       1)
         echo "One"
         ;;
       2)
         echo "Two"
         ;;
       *)
         echo "Undefined Value!"
         ;;
     esac
     ```

### Loops:
1. **For Loop:**
   - Example script:
     ```bash
     #!/bin/bash
     # Testing For Loop
     for num in {1..10}
     do
       echo $num
     done
     ```
2. **While Loop:**
   - Example script:
     ```bash
     #!/bin/bash
     # Testing While Loop
     arg=no
     while [[ $arg != "yes" ]]
     do
       echo "Are you ready to continue? yes/no"
       read arg
     done
     echo "Continuing with the rest of the script"
     ```

### Creating a Function:
1. **Create a Script with a Function:**
   - Example script:
     ```bash
     # Define your function here
     echo_message(){
       name=empty
       echo "Please Enter a Name:"
       read name
       echo "The Name You Entered is $name"
     }
     # Invoke your function
     echo_message
     ```

### Shell Scripting for Incident Response:
1. **Pattern Detection Script:**
   - Example script:
     ```bash
     #!/bin/bash
     echo "Enter the full path of the file"
     read file
     echo "Enter the pattern you are looking for"
     read pattern
     grep $pattern $file
     ```
2. **List Bad Login Attempts:**
   - Create a script to list bad login attempts between two dates.
