# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls

#include <stdio.h>
#include <unistd.h>

int main() {
    pid_t pid, parent_pid;

    pid = getpid(); 
    parent_pid = getppid();

    printf("Process ID (PID): %d\n", pid);
    printf("Parent Process ID (PPID): %d\n", parent_pid);

    return 0;
}














## OUTPUT


![image](https://github.com/Hariveeraprasad-2006/Linux-Process-API-fork-wait-exec/assets/145049988/4ddc6d3f-5ac9-4ec8-8288-9e2db488fde4)












## C Program to create new process using Linux API system calls fork() and exit()

#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int main() {
    pid_t pid;
    pid = fork();
    if (pid < 0) { 
        fprintf(stderr, "Fork failed\n");
        return 1;
    } else if (pid == 0) {
        printf("Child process created with PID: %d\n", getpid());
        printf("Child process is terminating...\n");
        exit(0); 
    } else { 
        printf("Parent process created with PID: %d\n", getpid());
        printf("Parent process continues...\n");
    }
    return 0;
}












## OUTPUT


![image](https://github.com/Hariveeraprasad-2006/Linux-Process-API-fork-wait-exec/assets/145049988/e3387fe4-864b-47b2-84ed-241c83f24f15)






## C Program to execute Linux system commands using Linux API system calls exec() family

#include <stdio.h>
#include <unistd.h>

int main() {
    char *args[] = {"ls", "-l", NULL};
    
    printf("Before exec()\n");
    execvp("ls", args); // Execute "ls -l" command
    printf("After exec()\n"); // This line won't be executed if execvp() is successful

    return 0;
}
























## OUTPUT
![image](https://github.com/Hariveeraprasad-2006/Linux-Process-API-fork-wait-exec/assets/145049988/8fd77688-ca3a-4d27-adf9-3052c710df72)


















# RESULT:
The programs are executed successfully.
