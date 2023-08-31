# Log library

# Log library

The Log library provides functions for emmiting log messages, which can be helpful to developers. All of these functions are contained in the “Log” Lua table found in the “log.lua” unit.

&nbsp;

Usage example:

| *\-- First, you need to use the “log.lua” unit* require("log.lua");    *-- Now you can access the functions of the library.* Log.LIBRARY\_FUNCTION(Argument1, Argument2, ...); |
| --- |


&nbsp;

# Where the log messages goes to?

&nbsp;

The log messages emmited by this library are sent to:

&nbsp;

* &nbsp;
  * The Firecast's console. Use the /console command to reveal the console.
  * The Firecast's debug log files (also known as "LogErrors")

&nbsp;

## Log library functions

&nbsp;

| **function** Log.e(tag, msg) **function** Log.w(tag, msg) **function** Log.i(tag, msg) **function** Log.d(tag, msg) **function** Log.v(tag, msg) |
| --- |


&nbsp;

Emmit log message

&nbsp;

Arguments:

* &nbsp;
  * tag - Used to identify the source of a log message. It usually identifies the location or activity where the log call occurs.
  * msg - The message you would like to be logged

&nbsp;

Log severity:

| Log.e | **Error message** A situation that represents an unhandled error that may interrupt some operation&nbsp; |
| --- | --- |
| Log.w | **Warning message** A situation that can be handled but may cause some unintended behavio&nbsp; |
| Log.i | **Informational/Notice message** A normal but significant condition that may require special handling.&nbsp; |
| Log.d | **Debug message** A developer debug message&nbsp; |
| Log.v | **Verbose message** Algorithm steps message, very low priority messages.&nbsp; Remarks: Messages of this severity are not emitted in the Firecast’s log files In the Firecast’s console, you need to execute the command “filter add \*” to be able to see these messages.&nbsp; |



***
_Created with the Personal Edition of HelpNDoc: [Leave the tedious WinHelp HLP to CHM conversion process behind with HelpNDoc](<https://www.helpndoc.com/step-by-step-guides/how-to-convert-a-hlp-winhelp-help-file-to-a-chm-html-help-help-file/>)_
