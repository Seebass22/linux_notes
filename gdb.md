# general
break       //set breakpoint
tbreak      //set temporary breakpoint
next        //next line
step        //next line, stepping into functions
continue    //continue until next breakpoint
finish      //execute rest of function
until       //execute rest of loop
watch <var> //set watchpoint to alert you of changes to var (var must be in scope)
info locals //display all local variables and their values

bt          //print backtrace of stack frames
bt full     //print backtrace of stack frames and values of local variables

list        //show C source
disass      //show assembly

// commands at breakpoint
commands <breakpoint-number>
<commmands...>
end

// use silent as first command to suppress gdb output
// use continue as last command to continue to next iteration of loop automatically

# assembly
nexti       //next instruction
x           //examine memory
x $rip      //examine memory at register rip (instruction pointer)
x/o   x/x   //examine in octal, hex
x/u   x/c   //examine as unsigned int, character
x/i         //examine as instruction
x/s         //examine as string

i r rbp     //info register rbp

//DWORD 4bytes (int)

# registers
rip  //instruction pointer
rsp  //stack pointer
rbp  //base pointer
