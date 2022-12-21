# What Are stdin, stdout, and stderr on Linux?
stdin, stdout, and stderr are three data streams created when you launch a Linux command. You can use them to tell if your scripts are being piped or redirected.
In Linux, stdin is the standard input stream. This accepts text as its input. Text output from the command to the shell is delivered via the stdout (standard out) stream. Error messages from the command are sent through the stderr (standard error) stream.

> So you can see that there are two output streams, stdout and stderr, and one input stream, stdin. Because error messages and normal output each have their own conduit to carry them to the terminal window, they can be handled independently of one another.

> Each file associated with a process is allocated a unique number to identify it. This is known as the file descriptor. Whenever an action is required to be performed on a file, the file descriptor is used to identify the file.

These values are always used for stdin, stdout, and stderr:
* 0: stdin
* 1: stdout
* 2: stderr

> People with passion can change the world for the better.

> Those people who are crazy enough to think that they can change the world are the ones that actually do.
