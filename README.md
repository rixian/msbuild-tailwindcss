[![NuGet package](https://img.shields.io/nuget/v/Rixian.MSBuild.TailwindCSS.svg)](https://nuget.org/packages/Rixian.MSBuild.TailwindCSS)

# Rixian.MSBuild.TailwindCSS

Welcome!

This NuGet package adds build targets required to work with TailwindCSS in your project. No need to manage any dependencies, and all Tailwind changes are compiled along with the project itself. When there are no changes the compilation is skipped.

## Prerequisites
The only prerequisites is that you have NodeJS installed on your machine and in your PATH:
https://nodejs.org

## How to Use
To get started you simply need to add a reference to this NuGet package: https://www.nuget.org/packages/Rixian.MSBuild.TailwindCSS

Once you have added the package you simply need to build your project. The first time the project is built it will add the require NPM packages, and if the `tailwind.css` file is not found, a basic version will be generated for you so that the build can succeed.

By default this package will look for an input file at `wwwroot/css/tailwind.css` and compile it to `wwwroot/css/tailwind.generated.css`. If you need to configure TailwindCSS, an optional configuration file located at the project root named `tailwind.config.js` may be provided.

Once the final file is produced you may include it in your ASP.NET Core project:
```html
<link rel="stylesheet" href="~/css/tailwind.generated.css" asp-append-version="true" />
```

## Overrides
You can add overrides for the default names and paths like so:

```
<PropertyGroup>
    <TailwindCssInput>wwwroot/css/tailwind.css</TailwindCssInput>
    <TailwindCssOutput>wwwroot/css/tailwind.generated.css</TailwindCssOutput>
    <TailwindCssConfig>tailwind.config.js</TailwindCssConfig>
    <TailwindCssDebug>true</TailwindCssDebug>
</PropertyGroup>
```
