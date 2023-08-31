# Promise object

# Promise object

This object represents the eventual outcome of an asynchronous operation and its return data.

&nbsp;

A promise can be in one of the following state:

&nbsp;

* &nbsp;
  * Pending - The asynchronous operation is still in progress
  * Success - The asynchronous operation concluded with success
  * Failed - The asynchronous operation concluded with error or failure

&nbsp;

Once a Promise has been resolved to either “Success” or “Failed”, its state is sealed along with its associated data or error message

## Characteristics

### Properties

| **Propriedade** | Tipo | Descrição |
| --- | --- | --- |
| &nbsp; | &nbsp; | &nbsp; |


&nbsp;

&nbsp;

### Methods

| **Método** | Descrição |
| --- | --- |
| **promise:thenDo(successCallback)**&nbsp; | Set a continuation callback function that will be called when the Promise resolves to success.&nbsp; Arguments: successCallback - A function that will be called when the Promise resolves to success. The first argument of the callback function will receive the associated success data.&nbsp; Remarks: If the Promise is already in a success state, the successCallback will be called as soon as possible&nbsp; Return: A new [Promise object](<Promiseobject.md>) that will be resolved asynchronously with the execution of the successCallback.&nbsp; Example:&nbsp; local promise = Firecast.asyncOpenUserNDB("name");   promise:thenDo(     function(node)         *-- This function will be called when the Promise is resolved*&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; *-- successfully. The first argument, "node", contains the* &nbsp; &nbsp; &nbsp; &nbsp; *-- Promise success data, which in this case is an opened* &nbsp; &nbsp; &nbsp; &nbsp; *-- nodeDatabse*     end); &nbsp; |
| **promise:thenDo(successCallback, failureCallback)** | Set continuation callback functions that will be called when the Promise resolves to success or failure.&nbsp; Arguments: successCallback - A function that will be called if the Promise resolves to success. The first argument of the callback function will receive the associated success data failureCallback - A function that will be called if the Promise resolves to failure. The first argument of the callback function will receive the error message.&nbsp; Remarks: This will monitor the Promise for both success and failure states at the same time If the Promise is already in a success state, the successCallback will be called as soon as possible.&nbsp; If the Promise is already in a failure state, the failureCallback will be called as soon as possible If the “successCallback” is called, “failureCallback” will never be called and vice versa.&nbsp; Return: A new [Promise object](<Promiseobject.md>) that will be resolved asynchronously with the execution of either the successCallback or failureCallback&nbsp; Example:&nbsp; local promise = Firecast.asyncOpenUserNDB("name");   promise:thenDo(     function(node)         *-- This function will be called when/if the *         *-- Promise is resolved successfully. The first argument, *         *-- "node", contains the Promise success data, *         *-- which in this case is an opened nodeDatabase*     end,    &nbsp;     function(errorMsg)         *-- This function will be called when/if the *         *-- Promise is resolved to failure. The first argument, *         *-- "errorMsg", contains the associated error message,*         *-- which in this case is the message explaining why*         *-- it was not possible to open the nodeDatabase*     end); &nbsp; |
| **promise:onError(failureCallback)** | Set a continuation callback function that will be called when the Promise resolves to failure.&nbsp; Arguments: failureCallback - A function that will be called if the Promise resolves to failure. The first argument of the callback function will receive the error message.&nbsp; Remarks: If the Promise is already in a failure state, the failureCallback will be called as soon as possible&nbsp; Return: A new [Promise object](<Promiseobject.md>) that will be resolved asynchronously with the execution of failureCallback&nbsp; Example:&nbsp; local promise = Firecast.asyncOpenUserNDB("name");   promise:onError(     function(errorMsg)         *-- This function will be called when/if the *         *-- Promise is resolved to failure. The first argument, *         *-- "errorMsg", contains the associated error message,*         *-- which in this case is the message explaining why*         *-- it was not possible to open the nodeDatabase*     end); &nbsp; |



***
_Created with the Personal Edition of HelpNDoc: [Qt Help documentation made easy](<https://www.helpndoc.com/feature-tour/create-help-files-for-the-qt-help-framework>)_
