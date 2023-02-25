# CodeIgniter 2 for PeachPie

Customized CodeIgniter 2 framework for PeachPie projects.

## PeachPie Web Server

Edit the 'Program.cs' file and replace the following content:
```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    RewriteOptions rewriteOptions = new();

    rewriteOptions.AddRewrite(@"^(favicon\.ico)$", "assets/ico/$1", skipRemainingRules: true);
    rewriteOptions.AddRewrite(@"^assets/(.*)/(.*)$", "assets/$1/$2", skipRemainingRules: true);
    rewriteOptions.AddRewrite(@"^(.*)$", "index.php/$1", skipRemainingRules: true);

    app.UseRewriter(rewriteOptions);            

    app.UseSession();

    app.UsePhp("/");            

    app.UseDefaultFiles();
    app.UseStaticFiles();
}
```

## Sample

[This project](https://github.com/daleffe/CodeIgniter2PeachPie-sample) provides REST API, pages with Bootstrap 5/JQuery and authentication.

## CodeIgniter 2

Open Source PHP Framework (originally from EllisLab)

For more info, please refer to the user-guide at http://www.codeigniter.com/userguide2/  
(also available within the download package for offline use)

**WARNING:** *CodeIgniter 2.x is no longer under development and only receives security patches until October 31st, 2015.
Please update your installation to the latest CodeIgniter 3.x version available
(upgrade instructions [here](http://www.codeigniter.com/userguide3/installation/upgrade_300.html)).*
