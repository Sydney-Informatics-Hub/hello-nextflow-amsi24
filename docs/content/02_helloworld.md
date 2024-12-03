# Hello World!

!!! info "Learning objectives"

    1. Utilise simple bash commands to manipulate strings
    2. Create and run a bash script that creates a text file

A **Hello, World!** is a minimalist example that is meant to demonstrate the basic syntax and structure of a programming language or software framework. The example typically consists of printing the phrase 'Hello World!' to the output, such as the console or terminal, or writing it to a file.

Let's demonstrate this with simple commands that you can run directly in the terminal.

## Print a string

The **`echo`** command in Linux is a built-in command that allows users to display lines of text or strings that are passed as arguments. It is commonly used in shell scripts and batch files to output status text to the screen or a file.

The most straightforward usage of the `echo` command is to display a text or string on the terminal. To do this, you simply provide the desired text or string as an argument to the `echo` command:

```bash
echo <string>
```

!!!question "Exercise"

    Use the `echo` command to print the string `'Hello World!'` to the terminal.

    ??? Solution

        ```bash
        echo 'Hello World!'
        ```

## Redirect outputs

The output of the `echo` can be redirected to a file instead of displaying it on the terminal. You can achieve this by using the **`>`** operator for output redirection. For example:

```bash
echo 'Welcome!' > output.txt
```

This will write the output of the echo command to the file name `output.txt`.

!!!question "Exercise"

    Use the `>` operator to redirect the output of echo to a file named `output.txt`.

    ??? "Solution"

        ```bash
        echo 'Hello World!' > output.txt
        ```

## List files

The Linux shell command **`ls`** lists directory contents of files and directories. It provides valuable information about files, directories, and their attributes.

`ls` will display the contents of the current directory:

```bash
ls
```

!!!question "Exercise"

    List the files in the working directory to verify `output.txt` was created.

    ??? Solution

        ```bash
        ls
        ```

        A file named `output.txt` should now be listed in your current directory.

## View file contents

The **`cat`** command in Linux is a versatile companion for various file-related operations, allowing users to view, concatenate, create, copy, merge, and manipulate file contents.

The most basic use of `cat` is to display the contents of a file on the terminal. This can be achieved by simply providing the filename as an argument:

```bash
cat <file name>
```

!!!question "Exercise"

    Use the `cat` command to print the contents of `output.txt`.

    ??? "Solution"

        ```bash
        cat output.txt
        ```

        You should see `Hello World!` printed to your terminal.

## Writing a bash script  

When we need to run the same command multiple times, it is useful to
include it in a (bash) script and run the script instead. This avoids having
to re-type the command each time and makes it reproducible. 

!!!question "Exercise"

    1. Create a new file called `hello_world.sh`  
    2. Copy and paste the following into `hello_world.sh`:  

        ```bash linenums="1"
        #!/bin/bash
        echo 'Hello AMSI!'
        ```
    3. **Save the file!**

## Setting file permissions

If we try running the script now, the following error will be returned:  

```console
-bash: ./hello_world.sh: Permission denied
```

This is because it does not have a correct file permissions to be executed. 

The **`chmod`** command in Linux is used to chance the access permissions of files and directories. It allows you to determine whether files/directories can be read, written, and executed, and by whom.  

!!!question "Exercise"

    Make the script executable using the `chmod -x` command.

    ???note "Solution"

        ```bash
        chmod +x hello_world.sh
        ```

## Running the bash script  

We are finally ready to run the bash script!  

!!!question "Exercise"

    Run the `hello_world.sh` script and redirect the output to a file named
    `output.txt`.

    ???note "Solution"

        ```bash
        ./hello_world.sh > output.txt
        ```

!!!question "Exercise"

    Next, use `cat` to print the contents of `output.txt`.  

    ???note "Solution"

        ```bash
        cat output.txt
        ```

        You should see `Hello AMSI!` printed to your terminal.

In the following sections, we will convert this example into a small
Nextflow pipeline.

!!! abstract "Summary"

    In this step you have learned:

    1. How to use the `echo` command to print a string to the terminal
    2. How to use the `>` operator to redirect the output of `echo`
    3. How to use the `ls` command to list the files in your working directory
    4. How to use the `chmod` command to make a file executable
    5. How to create and run a bash script
