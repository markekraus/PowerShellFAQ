# How do I pass parameters to PowerShell scripts?

Passing arguments in PowerShell is the same as in any other _shell_: you just type the command name, and then each argument, separated by spaces. If you need to specify the parameter name, you prefix it with a dash like `-Name` and then after a space (or a colon), the value. If the parameter is a "switch" then specifying it's name sets it to True, so you should not provide a value. Passing multiple values to the same parameter requires commas (and optionally, the `@(...)` array specifier).

Accepting parameters in a PowerShell script (or function) is done by adding a `param` block at the top with a comma-separated list of parameter names:

```posh
function Test-Script {
    param($Name,$Age)
    "$Name is roughly $Age years old"
}

Test-Script "The Doctor" "4.5 billion"
Test-Script -Name Mother -Age 29
```