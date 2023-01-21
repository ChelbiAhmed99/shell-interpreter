# shell-interpreter

A Unix shell is a command interpreter for Unix and Unix-like operating systems that 
provides access to internal operating system functionality. 

It comes in the form of a command line interface accessible from the console or a terminal.
In this program we implement a shell script that can be executed on bash or alternative mode.

# Config File Structure

Process management: The program uses the fork() and exec() system calls to
create a new process to run each command, and wait() to wait for the command to
complete before returning the prompt to the user.

String tokenization: The program uses the strtok() function to split the user's
input into tokens (i.e. individual words or commands) for parsing.

Command composition: The program uses tokenize_buffer() to decompose the
user's input into tokens, which are then passed to execvp() to execute the
commands.

Redirection: The program uses the dup2() system call to redirect the standard
output or standard input of a process to a specified file descriptor. This allows for
redirecting the output of a command to a file or the output of a file to a command.

Piping: The program uses pipe() system call to create a named pipe that connects
the standard input of one process to the standard output of another process. This
allows for connecting multiple commands to perform more complex tasks. 

Error handling: The program uses the perror() function to display error messages
when an invalid command is entered or if an error occurs during execution. The
ANSI_COLOR_RED macro is used to change the color of the error message to red
to make it more noticeable. 

Historic.

❖ Array of pointer to strings (char **) are used to store the parameters of each
command. The commands are then parsed using the strtok() function to break up
the parameters on a specified delimiter character. 

❖ The nr is the number of piped commands ( limited to 10 in this program ). 

❖ The fd array is used to store the file descriptor of the pipes.

❖ The argv array is used to store the tokenized commands.

❖ The pc variable is used to keep track of the number of parameters for each
command.

# Running the program
At first, To delete all the object files and executables we use the command
clean.you have to run: 

-make clean 
Next, To run the shell we’ll create the executables by running a simple
makefile using the command. 
-make 
./exec 

