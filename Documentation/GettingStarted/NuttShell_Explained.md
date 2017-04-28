# The NuttShell

The built in applicaition NuttShell (NSH) allows for invoking custom applications
through the command line.  Applictions must be registered in 
`apps/builtin/builtin_list.h` in order to be launched via NSH, but once registered
the applications will be available via the NSH command line.  If you type 'help'
at the NSH prompt you will see a list of the registered commands

By Default built-in commands started from the NSH command line will run
asynchronously with NSH.  If you want to force NSH to execute commands then wait
for the command to execute you can enable the functionality by setting 
`CONFIG_SCHED_WAITPID=y` in the .config file of the build. This configuration
options enables support for the waitpid() RTOS interface.  Even with waitpid() 
specific commands can *still* be launched asynchronosuly by adding the ampersand
`&` to the command.


