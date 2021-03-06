If you are using both of **ASP.NET MVC** and **ASP.NET Web API** in your
application, you need to add
[**Abp.Owin**](https://www.nuget.org/packages/Abp.Owin) nuget package to
your project.

### Installation

Add [**Abp.Owin**](https://www.nuget.org/packages/Abp.Owin) nuget
package to your host project (generally, to the **Web** project).

    Install-Package Abp.Owin

### Usage

Then call **UseAbp()** extension method in your OWIN **Startup** file as
shown below:

    [assembly: OwinStartup(typeof(Startup))]
    public class Startup
    {
        public void Configuration(IAppBuilder app)
        {
            app.UseAbp();

            //your other configuration...
        }
    }

If you are only using OWIN (say, in a self hosted Web API project), you
can use override of UseAbp which takes a startup module to initialize
ABP framework. Notice that; this should be done only if ABP is not
initialized in another way.
