---
title: "Setup Chutzpah to Run Javascript Tests in VisualStudio"
date: 2015-03-14T00:00:00+00:00
publishdate: 2015-03-14T00:00:00+00:00
lastmod: 2015-03-14T00:00:00+00:00
image: "/images/banners/bricks.jpg"
tags: ["Unit Testing", "JavaScript", "Visual Studio"]
type: "post"
comments: true
draft: true
---


<p>First thing first, install Chutzpah <a href="https://visualstudiogallery.msdn.microsoft.com/71a4e9bd-f660-448f-bd92-f5a65d39b7f0" target="_blank">Test Runner</a>&nbsp;and <a href="https://visualstudiogallery.msdn.microsoft.com/f8741f04-bae4-4900-81c7-7c9bfb9ed1fe" target="_blank">Test Adaptor for the Test Explorer</a>.</p>
<p>Next, setup your projects in Visual Studio. I personally like to keep my test code in a separate project for JavaScript as well so my project and folder structure looks like this:</p>
<p style="text-align: left;">&nbsp;<img src="/blog/images/setup-chutzpah-to-run-javascript-tests-in-visualstudio/image1.PNG" alt="" /></p><!-- more -->
<p style="text-align: left;">This allows you&nbsp;to restrict testing frameworks and libraries like Jasmine only to&nbsp;the test project. I use JavaScript&nbsp;libraries directly from the main project when it is needed in test projects as well rather then adding them again in the test project (some people have different view on this but it works for me).</p>
<p style="text-align: left;">Now, add all the JavaScript files required for your test. This includes<br/>

1. testing library/framework files<br/>
2. code under test file(s)<br/>
3. any additional files required to run code under test<br/>
</p>
<p>When you are done, your homeSpec.js might look like this</p>

``` lang:js
/// <reference path="../../../myapplication.web/scripts/jquery-1.10.2.min.js" />

/// <reference path="../../../myapplication.web/app/app.js" />
/// <reference path="../../../myapplication.web/app/home/homecontroller.js" />


describe('home page', function() {

    it('should return tile as Home', function() {

        expect('home').toBe('home');

    });

```
<p>You can use right click on a test in the code window to run tests in the context or you can right click on a file, folder or project in the solution explorer to run all the tests available in the selected file, folder or project using Chutzpah.</p>
<p>We have not applied any custom configurations for this example because it works out of the box but you can configure Chutzpah by creating chutzpah.json file. The tests can be run using command line as well.</p>
<p>You can find everything you can do with Chutzpah <a href="https://github.com/mmanela/chutzpah" target="_blank">here</a>.</p>


