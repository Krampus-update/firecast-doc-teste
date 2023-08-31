# Async.Promise library

# Async.Promise library

The Async.Promise library provides functions for handling asynchronous operations, such as loading a remote node database. All of these functions are contained in the “Async.Promise” and/or “Promise” Lua tables found in the “async.lua” unit.

&nbsp;

Usage example:

| *\-- First, you need to use the “async.lua” unit* require("async.lua");    *-- Now you can access the functions of the library.* Async.Promise.LIBRARY\_FUNCTION(Argument1, Argument2, ...); or Promise.LIBRARY\_FUNCTION(Argument1, Argument2, ...); |
| --- |


&nbsp;

&nbsp;

## Async.Promise library functions

&nbsp;

| **function** Async.Promise.resolved(data) **function** Promise.resolved(data) |
| --- |


&nbsp;

Creates and returns a Promise object that has already been **successfully** resolved with the provided “data” argument

&nbsp;

Arguments:

* &nbsp;
  * data - the value that was successfully resolved. This can be any information you want to pass as a successful return value

&nbsp;

Return:

* &nbsp;
  * The new [Promise object](<Promiseobject.md>)

&nbsp;

&nbsp;

| **function** Async.Promise.withError(errorMsg) **function** Async.Promise.withException(errorMsg) **function** Promise.withError(errorMsg) **function** Promise.withException(errorMsg) |
| --- |


&nbsp;

Creates and returns a Promise object that has already been resolved with a **failure** state and the provided error message

&nbsp;

Arguments:

* &nbsp;
  * errorMsg - The error message that describes why the Promise resolved to a failed state.

&nbsp;

Return:

* &nbsp;
  * The new [Promise object](<Promiseobject.md>)

***
_Created with the Personal Edition of HelpNDoc: [Eliminate the Struggles of Documentation with a Help Authoring Tool](<https://www.helpndoc.com/news-and-articles/2022-09-27-why-use-a-help-authoring-tool-instead-of-microsoft-word-to-produce-high-quality-documentation/>)_
