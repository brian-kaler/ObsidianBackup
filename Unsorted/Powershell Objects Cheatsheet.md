

## PowerShell Objects

- `[string]`: Represents a string of characters.
- `[int]`: Represents a 32-bit integer.
- `[long]`: Represents a 64-bit integer.
- `[decimal]`: Represents a decimal number with up to 28 significant digits.
- `[double]`: Represents a double-precision floating-point number.
- `[bool]`: Represents a Boolean value (`$true` or `$false`).
- `[array]`: Represents an ordered collection of items.
- `[hashtable]`: Represents a collection of key/value pairs.
- `[pscustomobject]`: Allows you to create custom objects with properties that you define.
- `[datetime]`: Represents a date and time value.

## Special Objects

- `$null`: Indicates the absence of any object value.
- `$_`: Refers to the current object in the pipeline.
- `$args`: Contains an array of arguments passed to the script or function.

## Other Objects

There are many other PowerShell objects available, including:

- `System.IO.FileInfo` and `System.IO.DirectoryInfo`, which represent files and directories on disk
- `Microsoft.Win32.RegistryKey`, which allows you to work with Windows Registry keys
- `System.Diagnostics.Process`, which represents running processes on your computer
- `System.Management.Automation.PSCredential`, which represents credentials used for authentication purposes

Note that many .NET Framework classes can be used as PowerShell objects as well.