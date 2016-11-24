# shell_bush
Bush's unlike bash

bush-- is a very simple (and extremely limited) shell for Unix born as
a simplified version of Chiola's bush which, in turn, is a simplified version of bash
(bush is the recursive acronym of: "bush's unlike bash").

bush-- understands the following four built-in commands (square-brackets denote
optionality):

- @cd [pathname]
- @set identifier = name
- @show-variables
- @quit

and, as other shells, it can run any external command, redirecting its input
and/or output with the following syntax:
executable-name [arg1] [arg2] ... [< input-filename] [> output-filename]

Note that, for simplicity sake, input redirection, when present, must occur
before output redirection.

A variable name must be a "standard" identifier, while other names consist
of a non-empty sequence of:
- strings (without special characters); e.g.: foo 
- value of variables; e.g.: $foo or ${bar}
- string literals, between single quotes; e.g.: '$foo is not a variable'
- escaped chars; e.g. \$ \n

A simple example session of bush-- is the following:

bush-- $ @set foo=SET
bush-- $ @set foo=${foo}'2015/2016'
bush-- $ echo $foo
SET2015/2016
bush-- $ ls -l 
total 104
-rwxrwxr-x 1 gio gio 93904 nov  7 16:12 bmm
drwxrwxr-x 2 gio gio  4096 nov  7 15:47 Debug
bush-- $ ls -l | grep ebu > foobar
bush-- $ cat < foobar
drwxrwxr-x 2 gio gio  4096 nov  7 15:47 Debug
bush-- $ @cd Debug
bush-- $ pwd
[...]/bin/Debug
bush-- $ 


