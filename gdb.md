# general
break            // set breakpoint
break 5
break main
break hello.c:5

info breakpoints // list breakpoints
delete <num>     // delete breakpoints
clear <location> // delete breakepoint

tbreak           // set temporary breakpoint
next             // next line
step             // next line, stepping into functions
continue         // continue until next breakpoint
finish           // execute rest of function
until            // execute rest of loop
watch   <var>    // break when var is written to
rwatch  <var>    // break when var is read from
awatch  <var>    // break when var is written to or read from
display <var>    // always show value of <var>
print   <var>

info locals      // display all local variables and their values
info threads     // show all threads being run

thread <num>     // switch to thread

%% set variables
set variable i = 40
%% or
set (i = 40)

%% to look at prev variables
frame <num> // traverse call stack (0 = current, 1 = parent, 2 = parent's parent)

bt          // print backtrace of stack frames
bt full     // print backtrace of stack frames and values of local variables

list        // show C source
disass      // show assembly

%% commands at breakpoint
commands <breakpoint-number>
<commmands...>
end

%% use silent as first command to suppress gdb output
%% use continue as last command to continue to next iteration of loop automatically

# assembly
nexti       // next instruction
x           // examine memory
x $rip      // examine memory at register rip (instruction pointer)
x/o   x/x   // examine in octal, hex
x/u   x/c   // examine as unsigned int, character
x/i         // examine as instruction
x/s         // examine as string

i r rbp     //info register rbp

//DWORD 4bytes (int)

# registers
rip  // instruction pointer
rsp  // stack pointer
rbp  // base pointer

# other
%% toggle TUI
CTRL x a

%% conditional watchpoint
watch (z > 28)
