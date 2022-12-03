# x64-Executable-that-scan-open-ports

Here is a simple example of how to write an x64 executable that scans open ports in the internal network using the netstat command in Windows:

```
#include <stdio.h>
#include <string.h>

int main(void) {
  // Use the netstat command to list all open ports in the internal network
  char command[256] = "netstat -an | findstr :";
  
  // Run the command and save the output in a string
  FILE *output = popen(command, "r");
  char result[1024];
  fgets(result, sizeof(result), output);

  // Print the list of open ports
  printf("List of open ports: %s\n", result);

  return 0;
}
```

To compile this code, you can use a C compiler like gcc:

```
$ gcc -m64 -o scan_ports scan_ports.c
```


This will create an executable file called scan_ports that you can run on your system to scan open ports in the internal network.

Note: This code is just an example and may not work on all systems. It is also important to mention that scanning ports on a network without permission can be considered a security violation, so be sure to use this code responsibly.
