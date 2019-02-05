{:title "Found conflicts between different versions of FSharp.Core"
  :layout :post
  :draft? false
  :tags ["fsharp", "linux", "dotnet core", "wtf"]}

## Hey, how is it going?
well, Life of coding fsharp in Linux is not that pleasant in June of 2018, well, most of the time to be honest. I mean, I love ML languages  but I guess maintaining the tooling around it is hard.

## what happened?
I got the following warning when runing an F# console application built by dotnet cli version 2.1.4 on linux 16.04 :

```bash
/usr/share/dotnet/sdk/2.1.4/Microsoft.Common.CurrentVersion.targets(2041,5): warning MSB3277: 
Found conflicts between different versions of "FSharp.Core" that could not be resolved.
```

which leads to the following error when running: `dotnet run`

```bash
Unhandled Exception: System.IO.FileLoadException: Could not load file or assembly 'FSharp.Core, Version=4.4.3.0, 
Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'. The located assembly's manifest definition does not match the assembly 
reference. (Exception from HRESULT: 0x80131040)
```

## and what did you do about it?

I defined the version of FSharp.Core to 4.4.*. at the end of the project file. This file has .fsproj extension:

```XML 
  <ItemGroup>
    <PackageReference Include="FSharp.Core" Version="4.4.*" />

  </ItemGroup>

```

## nice catch
I do not remember where I found the answer. 



