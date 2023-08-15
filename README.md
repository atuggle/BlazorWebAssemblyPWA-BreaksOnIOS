# .NET 8 Preview 7 bug executing on iPhone or iPad

## Summary

This is a sample repo project created using Visual Studio 2022 Preview (Version 17.8.0 Preview 1.0)

This project has two commits.  The first commit is the defaul sample project created when using "Create new project" and the second commit has the two lines of code that creates the bug.

## Steps to create sample project and then verify the bug

### Create the project

1. Open Visual Studio 2022 preview Edition
2. Choose "New Project" to create a new project
3. Find and choose "Blazor WebAssembly App"
4. Name the App and choose "Next"
5. Ensure ".NET 8.0 (Preview)" is selected as the framework and check "Progressive Web Application"

### Add code that breaks it on iPhone & iPad

1. Turn on AOT by adding ```<RunAOTCompilation>true</RunAOTCompilation>``` to the project file
2. Add an <InputText .../> element in the index.razor page
  - ```<InputText id="emailText" class="form-control" />```

Deploy the above code and see it fails on IOS with the error 

## Error shown in console log

```text
[Error] Error: AggregateException_ctor_DefaultMessage (Arg_IndexOutOfRangeException) — dotnet.runtime.8.0.0-preview.7.23375.6.hh1fgtyrm9.js:3:29648
	(anonymous function) (blazor.webassembly.js:1:40595)
```