# LanzhouBeefNoodles
ASP.NET Core MVC网站应用 - 兰州拉面

来自慕课网(https://www.imooc.com/learn/1188)

前端：*.cshtml

后端：C#, ASP.NET Core

数据库：SQLServer

开发环境：VS 2019社区版本，ASP.NET Core 2.2

用户认证、用户授权：采用ASP.NET内置模版。

安装部署：

1.下载安装VS2019社区版本(免费)；

2.下载安装.NET Core 2.2；

3.打开本工程解决方案“LanzhouBeefNoodles.sln”

4.编译(Ctrl+Shift+B)

5.生成数据库表

  打开菜单“视图”、“其它窗口”，“程序包管理器控制台”，输入：update-database

6.运行(F5)

  会自动打开浏览器并显示本应用页面(localhost:3000)。
  
cshtml为带Razor语法的 ASP.NET 网页有特殊的文件扩展名。Razor是一种简单的编程语法，用于在网页中嵌入服务器端代码。Razor 语法基于 ASP.NET 框架，该框架是微软的 .NET 框架特别为 web 应用程序开发而设计的组成部分。

代码示例如下：
```

@*@model IEnumerable<LanzhouBeefNoodles.Models.Noodle>*@

@model LanzhouBeefNoodles.ViewModels.HomeViewModel

@{
    ViewData["Title"] = "Index";
}

<h2>产品列表</h2>

@foreach (var noodle in Model.Noodles)
{
    <div class="col-sm-4 col-lg-4 col-md-4">
        <div class="thumbnail">
            <img src="@noodle.ImageUrl" alt="">
            <div class="caption">
                <h3 class="pull-right">￥@noodle.Price</h3>
                <h3>
                    <a 
                       asp-controller="Home" 
                       asp-action="Detail" 
                       asp-route-id="@noodle.Id"
                    >@noodle.Name</a>
                </h3>
                <p>@noodle.ShortDescription</p>
            </div>
        </div>
    </div>
}

```