# MVC - lecture demos and examples

## Introduction
In this solution will show all of the things that was describe on lecture. Here you will can find some general information about how to create project and information about where find content you are looking for.

## What you can find here

- [MVC Template project .Net 6.0](#mvc-template-project-net-60)
- [MVC Template project .Net 5.0](#mvc-template-project-net-50)




## MVC Template project .Net 6.0

How to create it? By VS/Rider create project and choose correct template or via dotnet CLI
command
`dotnet new mvc -n Project.Name`

Project name in solution: **MiNI.Example.MvcWeb.Template**

Has structure:
- Properties => folder containing project properties. Important file is lunchSettings.json in which you can specify IISExpress configuration, run profiles (with or without IIS Express)
- Controllers => all controllers should be put here
- Models => All UI model should be put here
- Views => All views should be put here (due to default view location resolution). Convention is View/[ControllerName]/Method.cshtml for pages. And for shared components View\Shared\Components\[ComponentModelName]\[ViewName]
- appsettings.json => configuration file 
- appsettings.Development.json => configuration file for Development environment
- Program.cs => entry point of application. Contains configuration and starts web app

Use:
- WebApplication.CreateBuilder() => from .net 6.0
  * it already add UseRouting and UseEndpoint 
  * it has minimal configuration approach
  * all added middlewares will be add on the end of the middleware queue

## MVC Template project .Net 5.0

How to create it? By VS/Rider create project and choose correct template (with correct c# version) or via dotnet CLI if you don't have install .net 6.0 sdk
command
`dotnet new mvc -n Project.Name`
if you had install .net 6.0 sdk there is additional step that need to be done before proper framework version will be created. 
You need to create global json file with specified sdk version something like that `dotnet new globaljson --sdk-version "5.0.408"` the use `dotnet new mvc -n Project.Name`. Be aware that from now every project that you create inside folder with this globaljson file will be created in .net 5

ProjectName in solution: **MiNI.Example.MvcOldWeb.Template**

Has structure:
- Properties => folder containing project properties. Important file is lunchSettings.json in which you can specify IISExpress configuration, run profiles (with or without IIS Express)
- Controllers => all controllers should be put here
- Models => All UI model should be put here
- Views => All views should be put here (due to default view location resolution). Convention is View/[ControllerName]/Method.cshtml for pages. And for shared components View\Shared\Components\[ComponentModelName]\[ViewName]
- appsettings.json => configuration file
- appsettings.Development.json => configuration file for Development environment
- Program.cs => entry point of application. Contains configuration of it 
- 

[Program and Startup responsibilities](./static_files/ProgramStartupExplanation.png)

Use:
- WebApplication.CreateBuilder() => from .net 6.0
  * it already add UseRouting and UseEndpoint
  * it has minimal configuration approach
  * all added middlewares will be add on the end of the middleware queue
