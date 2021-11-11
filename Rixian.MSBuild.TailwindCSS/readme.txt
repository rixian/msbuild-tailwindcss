Welcome!

This NuGet package adds build targets required to work with TailwindCSS in your project. The only requirement is that you have NodeJS installed on your machine:
https://nodejs.org

By default this package will look for an input file at `wwwroot/css/tailwind.css` and compile it to `wwwroot/css/tailwind.generated.css`. An optional configuration file located at the project root named `tailwind.config.js` may be provided.

Once the final file is produced you may include it in your ASP.NET Core project:
<link rel="stylesheet" href="~/css/tailwind.generated.css" asp-append-version="true" />


You can add overrides for the default names and paths like so:

<PropertyGroup>
    <TailwindCssInput>wwwroot/css/tailwind.css</TailwindCssInput>
    <TailwindCssOutput>wwwroot/css/tailwind.generated.css</TailwindCssOutput>
    <TailwindCssConfig>tailwind.config.js</TailwindCssConfig>
    <TailwindCssDebug>true</TailwindCssDebug>
</PropertyGroup>