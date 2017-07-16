# Angular-cli-cheetsheet

<b>What Is Angular CLI?</b><br>
Angular CLI is a Command Line Interface (CLI) to automate your development workflow. It allows you to:
<ul>
<li>create a new Angular application</li>
<li>run a development server with LiveReload support to preview your application during development</li>
<li>add features to your existing Angular application</li>
<li>run your application’s unit tests</li>
<li>run your application’s end-to-end (E2E) tests</li>
<li>build your application for deployment to production</li>
</ul>
<hr> 

<b>Prerequisites</b><br>
Must have <b>Node.js>=6.9.0</b> and <b>npm>=3.0.0</b> installed on your system.
<ul>
<li>If already installed then verify node version using command <b>node -v</b></li>
<li>If already installed then Verify npm version using command <b>npm -v</b></li>
<li>Else download the latest version of Node.js for your operating system using <a href="https://nodejs.org/en/">official Node.js website.</a></li>
<li>Once Node.js is installed, you can use the npm command to install <a href="http://www.typescriptlang.org/">TypeScript</a>: <b>npm install -g typescript@2.2.0</b></li>
</ul>
<b>NOTE:</b> Although <b>TypeScript</b> is technically not an absolute requirement, 
it is highly recommended by the Angular team, so I recommend you install it to make working with Angular as comfortable as possible.
<hr>

<b>Installing Angular CLI</b><br>
<ul>
<li>To install the ng command globally on your system run: <b>npm install -g @angular/cli</b> </li>
<li>To verify whether your installation completed successfully, run: <b>ng version</b></li>
</ul>
<hr> 


<b>Creating a New Angular Application</b><br>
There are two ways to create a new application using Angular CLI:
<ul>
<li><b>ng init</b>: create a new application in the current directory </li>
<li><b>ng new</b>: create a new directory and run <b>ng init</b> inside the new directory</li>
<li>So <b>ng new</b> is similar to <b>ng init</b> except that it also creates a directory for you.</li>
</ul>
Assuming you haven’t created a directory yet, let’s use ng new to create a new project:<br>
<b>ng new my-app</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a new directory <b>my-app</b> is created</li>
<li>all source files and directories for your new Angular application are created 
based on the name you specified <b>(my-app)</b> and 
best-practices from the <a href="https://angular.io/guide/styleguide">official Angular Style Guide</a></li>
<li>npm dependencies are installed</li>
<li>TypeScript is configured for you</li>
<li>the <a href="https://karma-runner.github.io/1.0/index.html">Karma</a> unit test runner is configured for you</li>
<li>the <a href="http://www.protractortest.org/#/">Protractor</a> end-to-end test framework is configured for you</li>
<li>environment files with default settings are created</li>
</ul>
<br><i>Available options</i>
<br><b>--dry-run boolean</b>, default <b>false</b>, perform dry-run so no changes are written to filesystem
<br><b>--verbose boolean</b>, default <b>false</b>, Output more information(Actally output all the things)
<br><b>--link-cli boolean</b>, default <b>false</b>, automatically link the @angular/cli package (<a href="https://karma-runner.github.io/1.0/index.html">more info</a>)
<br><b>--skip-install boolean</b>, default <b>false</b>, skip npm install
<br><b>--skip-git boolean</b>, default <b>false</b>, don’t initialize git repository
<br><b>--skip-tests boolean</b>, default <b>false</b>, skip creating tests
<br><b>--skip-commit boolean</b>, default <b>false</b>, skip committing the first git commit
<br><b>--mobile boolean</b>, default <b>false</b>, generate a Progressive Web App application
<br><b>--routing boolean</b>, default <b>false</b>, add module with routing information and import it in main app module
<br><b>--inline-style boolean</b>, default <b>false</b>, use inline styles when generating the new application
<br><b>--inline-template boolean</b>, default <b>false</b>, default false, use inline templates when generating the new application
<br><b>--directory string</b>, name of directory to create, by default this is the same as the application name
<br><b>--source-dir string</b>, default <b>'src'</b>, name of source directory
<br><b>--style string</b>, default <b>'css'</b>, , the style language to use <b>('css', 'less' or 'scss')</b>
<br><b>--prefix string</b>, default <b>'app'</b>, the prefix to use when generating new components
<hr>

<b>Running Your Application</b><br>
<ul>
<li>To preview your new application in your browser, navigate to its directory using cmd: <b>cd my-app</b> </li>
<li>Now to run the angular app, run: <b>ng serve</b></li>
<li>You can now navigate your favorite browser to <b>http://localhost:4200/</b> to see your application in action</li>
<li><b>NOTE:</b>The default port on which app is running is <b>4200</b></li>
</ul>
<br><i>Behind the scene</i><br>
<ol>
<li>Angular CLI loads its configuration from <b>.angular-cli.json</b></li>
<li>Angular CLI runs Webpack to build and bundle all JavaScript and CSS code</li>
<li>Angular CLI starts <a href="https://webpack.github.io/docs/webpack-dev-server.html">webpack dev server</a> to preview the result on localhost:4200</li>
</ol>
<b>NOTE:</b>The <b>ng serve</b> command does not exit and return to your terminal prompt after step 3.
Instead, because it includes LiveReload support, the process actively watches your <b>src</b> directory for file changes. 
When a file change is detected, step 2 is repeated and a notification is sent to your browser so it can refresh automatically.
To stop the process and return to your prompt, press <b>ctrl-c</b>.
<hr>

<b>Adding Features to Your Angular Application</b><br>
use the <b>ng generate</b> command to add features to your existing application:

<ul>
<li>Add a <b>class</b> to your application</li>
<ul>
<li>ng generate class my-new-class</li>
<li>ng g cl my-new-class</li>
</ul>
<li>Add a <b>component</b> to your application</li>
<ul>
<li>ng generate component my-new-component</li>
<li>ng g c my-new-component</li>
</ul>
<li>Add a <b>directive</b> to your application</li>
<ul>
<li>ng generate directive my-new-directive</li>
<li>ng g d my-new-directive</li>
</ul>
<li>Add an <b>enum</b> to your application</li>
<ul>
<li>ng generate enum my-new-enum</li>
<li>ng g e my-new-enum</li>
</ul>
<li>Add a <b>module</b> to your application</li>
<ul>
<li>ng generate module my-new-module</li>
<li>ng g m my-new-module</li>
</ul>
<li>Add a <b>pipe</b> to your application</li>
<ul>
<li>ng generate pipe my-new-pipe</li>
<li>ng g p my-new-pipe</li>
</ul>
<li>Add a <b>service</b> to your application</li>
<ul>
<li>ng generate service my-new-service</li>
<li>ng g s my-new-service</li>
</ul>
<li>Add an <b>interface</b> to your application</li>
<ul>
<li>ng generate interface my-new-interface</li>
<li>ng g i my-new-interface</li>
</ul>
</ul>

<hr>
<b>Adding a new class</b><br>
<b>ng generate class userProfile</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a file <b>src/app/user-profile.ts</b> is created that exports an empty class named <b>UserProfile</b></li>
</ul>
<br><i>Available options</i>
<br><b>--spec boolean</b>, default <b>false</b>, generate spec file with unit test
<br>
<br>

<b>Adding a new component</b><br>
<b>ng generate component site-header</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a directory <b>src/app/site-header</b> is created</li>
<li>inside that directory 4 files are generated:</li>
<ul>
<li>a CSS file for the component styles</li>
<li>an HTML file for the component template</li>
<li>a TypeScript file with a component class named <b>SiteHeaderComponent</b> and selector <b>app-site-header</b></li>
<li>a spec file with a sample unit test for your new component</li>
</ul>
<li><b>SiteHeaderComponent</b> is added as a declaration in the <b>@NgModule</b> decorator of the nearest module, 
in this case the <b>AppModule</b> in <b>src/app/app.module.ts</b></li>
</ul>
<br><i>Available options</i>
<br><b>--spec boolean</b>, default <b>true</b>, generate spec file with unit test
<br><b>--flat boolean</b>, default <b>false</b>, generate component files in <b>src/app</b> instead of <b>src/app/site-header</b>
<br><b>--inline-template boolean</b>, default <b>false</b>, use an inline template instead of a separate HTML file
<br><b>--inline-style boolean</b>, default <b>false</b>, use inline styles instead of a separate CSS file
<br><b>--prefix boolean</b>, default <b>true</b>, , use prefix specified in <b>.angular-cli.json</b> in component selector
<br><b>--view-encapsulation string</b>, specifies the view encapsulation strategy
<br><b>--change-detection string</b>, specifies the change detection strategy
<br>
<br>

<b>Adding a new directive</b><br>
<b>ng generate directive admin-link</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a file <b>src/app/admin-link.directive.ts is</b> created that exports a directive named <b>AdminLinkDirective</b> with a selector <b>appAdminLink</b></li>
<li>a file <b>src/app/admin-link.directive.spec.ts</b> is created with a unit test for the directive</li>
<li><b>AdminLinkDirective</b> is added as a declaration in the <b>@NgModule</b> decorator of the nearest module, in this case the <b>AppModule</b> in <b>src/app/app.module.ts</b></li>
</ul>
<br><i>Available options</i>
<br><b>--spec boolean</b>, default <b>true</b>, generate spec file with unit test
<br><b>--flat boolean</b>, default <b>true</b>, generate directive files in <b>src/app</b> instead of <b>src/app/admin-link</b>
<br><b>--prefix boolean</b>, default <b>true</b>, use prefix specified in <b>.angular-cli.json</b> in component selector
<br>
<br>

<b>Adding a new enum</b><br>
<b>ng generate enum Direction</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a file <b>src/app/direction.enum.ts</b> is created that exports an enum named <b>Direction</b></li>
</ul>
<br><i>Available options</i>
<br>There are no command line options available for this command.
<br>
<br>

<b>Adding a new module</b><br>
<b>ng generate module admin</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a directory <b>src/app/admin</b> is created</li>
<li>an <b>AdminModule</b> module is created inside <b>src/app/admin/admin.module.ts</b></li>
<li><b>Note: AdminModule</b> module is not added automatically to your main module <b>AppModule</b> in <b>src/app/app.module.ts</b>. It is up to you to import the module where you need it.</li>
</ul>
<br><i>Available options</i>
<br><b>--routing boolean</b>, default <b>false</b>, generate an additional module <b>AdminRoutingModule</b> with just the routing information and add it as an import to your new module
<br><b>--spec boolean</b>, default <b>false</b>, generate spec file with unit test
<br>
<br>

<b>Adding a new pipe</b><br>
<b>ng generate pipe convertToEuro</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a file <b>src/app/convert-to-euro.pipe.ts</b> is created that exports a pipe class named <b>ConvertToEuroPipe</b></li>
<li>a file <b>src/app/convert-to-euro.pipe.spec.ts</b> is created with a unit test for the pipe</li>
<li><b>ConvertToEuroPipe</b> is added as a declaration in the <b>@NgModule</b> decorator of the nearest module, in this case the <b>AppModule</b> in <b>src/app/app.module.ts</b></li>
</ul>
<br><i>Available options</i>
<br><b>--flat boolean</b>, default <b>true</b>, generate pipe files in <b>src/app</b> instead of <b>src/app/convert-to-euro</b> folder
<br><b>--spec boolean</b>, default <b>true</b>, generate spec file with unit test
<br>
<br>

<b>Adding a new service</b><br>
<b>ng generate service backend-api</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a file <b>src/app/backend-api.service.ts</b> is created that exports a service class named <b>BackendApiService</b></li>
<li>a file <b>src/app/backend-api.service.spec.ts</b> is created with a unit test for your new service</li>
<li><b>NOTE:</b>It is up to you to register the service as a provider by adding it to the <b>providers: []</b> array where you need it (e.g. in a module or component).</li>
</ul>
<br><i>Available options</i>
<br><b>--flat boolean</b>, default <b>true</b>, generate pipe files in <b>src/app</b> instead of <b>src/app/backend-api</b>
<br><b>--spec boolean</b>, default <b>true</b>, generate spec file with unit test
<br>
<br>
<b>Adding a new interface</b><br>
<b>ng generate interface VehicleInfo</b><br>
<br><i>Behind the scene</i><br>
<ul>
<li>a file <b>src/app/vehicle-info.ts</b> is created that exports an empty interface named <b>VehicleInfo</b></li>
</ul>
<br><i>Available options</i>
<br><b>--spec boolean</b>, default <b>false</b>, generate spec file with unit test
<hr>

<b>Special note</b><br>
<ul>
<li>Angular CLI does not just blindly generate code for you. 
It uses static analysis to better understand the semantics of your application.</li>
<li>For example, when adding a new component using ng generate component, 
Angular CLI finds the closest module in the module tree of your application and integrates the new feature in that module.</li>
<li>So if you have an application with multiple modules, 
Angular CLI will automatically integrate the new feature in the correct module, depending on the directory where you run the command from.</li>
</ul>
<hr>

<b>Running Your Unit Tests</b><br>
<ul>
<li>Angular CLI automatically configures the Karma test runner for you when your application is initially created.</li>
<li>When adding a feature to your application, you can use the <b>--spec</b> option to specify whether you want Angular CLI to also create a corresponding <b>.spec.ts</b> file with a sample unit test for your new feature..</li>
<li>Spec files are created in the same directory of their corresponding feature in the <b>src</b> directory. This allows you to easily locate them when working on a feature.</li>
<li>Running all unit tests of your application thus implies running all unit tests specified in all files ending in <b>.spec.ts</b> in all directories inside your <b>src</b> directory.</li>
<li>To run all unit tests, run: <b>ng test</b></li>
<li>and a special browser instance will be launched</li>
</ul>
<i>Behind the scene</i><br>
<ol>
<li>Angular CLI loads <b>.angular-cli.json.</b></li>
<li>Angular CLI runs Karma with the configuration specified in <b>.angular-cli.json.</b> 
By default this is <b>karma.conf.js</b> located in the root directory of your application.</li>
<li>Karma opens the browser specified in the Karma configuration.
By default the browser is set to Google Chrome.</li>
<li>Karma then instructs the browser (Chrome) to run <b>src/test.ts</b> using the testing framework specified in the Karma config. 
By default this is the <a href="https://jasmine.github.io/">Jasmine framework</a>. The file <b>src/test.ts</b> is automatically created when your application is created. 
It is pre-configured to load and configure the code that is needed to test your Angular application and run all spec files ending in <b>.spec.ts</b> in your <b>src</b> directory.</li>
<li>Karma reports the result of the test run to the console.</li>
<li>Karma watches the <b>src</b> file for changes and repeats step 4 and 5 when a file change is detected.</li>
</ol>
<hr>

<b>Running Your End-to-end (E2E) Tests</b><br>
<ul>
<li>Angular CLI automatically configures <a href="http://www.protractortest.org/#/">Protractor</a> for you when your application is initially created.</li>
<li>To run your E2E tests, run: <b>ng e2e</b></li>
<li>and a special browser instance will be launched</li>
</ul>
<i>Behind the scene</i><br>
<ol>
<li>Angular CLI loads <b>.angular-cli.json.</b></li>
<li>Angular CLI runs Protractor with the configuration specified in <b>.angular-cli.json.</b> 
By default this is <b>protractor.conf.js</b> located in the root directory of your application.</li>
<li>protractor opens the browser specified in the Karma configuration.
By default the browser is set to Google Chrome.</li>
<li>protractor then instructs the browser (Chrome) to run all spec files ending in <b>.e2e-spec.ts</b> in your <b>e2e</b> directory.</li>
<li>protractor reports the result of the test run to the console.</li>
<li>The process then exits automatically after step 5</li>
</ol>
<hr>

<b>Building Your Application for Production</b><br>
<ul>
<li>Running <b>ng serve</b> builds and bundles your Angular application automatically to a virtual filesystem during development.</li>
<li>However, when your application is ready for production, you will need real files that you can deploy to your server or to the cloud.</li>
<li>To build and bundle your application for deployment, run:<b>ng build</b></li>
</ul>
<i>Behind the scene</i><br>
<ol>
<li>Angular CLI loads its configuration from <b>.angular-cli.json.</b></li>
<li>Angular CLI runs <b>Webpack</b> to build and bundle all JavaScript and CSS code</li>
<li>The result is written to the <b>outDir</b> directory specified in your Angular CLI configuration. By default, this is the <b>dist</b> directory.</li>
</ol>
<br>
<i>Available options</i>
<br><b>--aot</b>, enable ahead-of-time compilation
<br><b>--base-href string</b>, the base href to use in the index file
<br><b>--environment string</b>, default <b>dev</b>, environment to use
<br><b>--output-path string</b>, directory to write the output to
<br><b>--target string</b>, default <b>development</b>, environment to use
<br><b>--watch string</b>, default <b>false</b>, watch files for changes and rebuild when a change is detected
<br>
<br>
<b>Targets</b><br>
Specifying a target impacts the way the build process operates. Its value can be one of the following:<br>
<ul>
<li><b>development</b> <i>default mode</i>, do not minify or uglify code</li>
<li><b>production</b> minify and uglify code</li>
<li>To build your application in production mode:<b>ng build --target=production</b></li>
</ul>
<i>Behind the scene</i><br>
<ul>
<li>Results in bundles that are minified, uglified and have hashes in their names</li>
</ul>
<br>
<b>Environments</b><br>
Environments let you specify settings to customize your application behavior.
You can define your own environments in the .angular-cli.json file. The default ones are:<br>
<ul>
<li><b>source</b>, use settings defined in <b>environments/environment.ts</b></li>
<li><b>dev</b>, use settings defined in <b>environments/environment.ts</b></li>
<li><b>prod</b>, use settings defined in <b>environments/environment.prod.ts</b></li>
</ul>
If you specify a different environment, the build process will use the corresponding environment:
<ul>
<li><b>ng build</b>, Uses environments/environment.ts</li>
<li><b>ng build --environment=dev</b>, Also uses environments/environment.ts</li>
<li><b>ng build --environment=prod</b>, Uses environments/environment.prod.ts</li>
</ul>
In <b>src/main.ts</b>, you can access the environment settings from your code by importing <b>environments/environment</b>
<hr>
