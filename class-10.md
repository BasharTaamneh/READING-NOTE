# js debugger

The debugger statement invokes any available debugging functionality, such as setting a breakpoint. If no debugging functionality is available, this statement has no effect.

**Examples**

Using the debugger statement

The following example shows code where a debugger statement has been inserted, to invoke a debugger (if one exists) when the function is called.

    function potentiallyBuggyCode() {
    debugger;
    // do potentially buggy stuff to examine, step through, etc.
    }