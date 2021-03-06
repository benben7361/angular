@description
Good tools make application development quicker and easier to maintain than
if you did everything by hand.

The [**Angular CLI**](https://cli.angular.io/) is a **_command line interface_** tool
that can create a project, add files, and perform a variety of ongoing development tasks such
as testing, bundling, and deployment.

The goal in this guide is to build and run a simple Angular
application in TypeScript, using the Angular CLI
while adhering to the [Style Guide](guide/style-guide) recommendations that
benefit _every_ Angular project.

By the end of the chapter, you'll have a basic understanding of development with the CLI
and a foundation for both these documentation samples and for real world applications.

You'll pursue these ends in the following high-level steps:

1. [Set up](cli-quickstart#devenv) the development environment.
2. [Create](cli-quickstart#create-proj) a new project and skeleton application.
3. [Serve](cli-quickstart#serve) the application.
4. [Edit](cli-quickstart#first-component) the application.

And you can also <a href="/resources/zips/cli-quickstart/cli-quickstart.zip">download the example.</a>


<h2 id='devenv'>
  Step 1. Set up the Development Environment
</h2>

You need to set up your development environment before you can do anything.

Install **[Node.js® and npm](https://nodejs.org/en/download/)**
if they are not already on your machine.

~~~ {.l-sub-section}

**Verify that you are running at least node `6.9.x` and npm `3.x.x`**
by running `node -v` and `npm -v` in a terminal/console window.
Older versions produce errors, but newer versions are fine.

~~~

Then **install the [Angular CLI](https://github.com/angular/angular-cli)** globally.

<code-example language="sh" class="code-shell">
  npm install -g @angular/cli  
    
</code-example>



<h2 id='create-project'>
  Step 2. Create a new project
</h2>

Open a terminal window.
Generate a new project and skeleton application by running the following commands:

<code-example language="sh" class="code-shell">
  ng new my-app  
    
</code-example>



~~~ {.l-sub-section}

Patience please.
It takes time to set up a new project, most of it spent installing npm packages.


~~~



<h2 id='serve'>
  Step 3: Serve the application
</h2>

Go to the project directory and launch the server.

<code-example language="sh" class="code-shell">
  cd my-app  
    ng serve --open  
    
</code-example>

The `ng serve` command launches the server, watches your files,
and rebuilds the app as you make changes to those files.

Using the `--open` (or just `-o`) option will automatically open your browser
on `http://localhost:4200/`.

Your app greets you with a message:

<figure class='image-display'>
  <img src='assets/images/devguide/cli-quickstart/app-works.png' alt="The app works!">  </img>
</figure>



<h2 id='first-component'>
  Step 4: Edit your first Angular component
</h2>

The CLI created the first Angular component for you.
This is the _root component_ and it is named `app-root`.
You can find it in `./src/app/app.component.ts`.
Open the component file and change the `title` property from _app works!_ to _My First Angular App_:


<code-example path="cli-quickstart/src/app/app.component.ts" region="title" linenums="false">

</code-example>

The browser reloads automatically with the revised title. That's nice, but it could look better.

Open `src/app/app.component.css` and give the component some style.


<code-example path="cli-quickstart/src/app/app.component.css" linenums="false">

</code-example>


<figure class='image-display'>
  <img src='assets/images/devguide/cli-quickstart/my-first-app.png' alt="Output of QuickStart app">  </img>
</figure>

Looking good!

## What's next?
That's about all you'd expect to do in a "Hello, World" app.

You're ready to take the [Tour of Heroes Tutorial](tutorial) and build
a small application that demonstrates the great things you can build with Angular.

Or you can stick around a bit longer to learn about the files in your brand new project.

## Project file review

An Angular CLI project is the foundation for both quick experiments and enterprise solutions.

The first file you should check out is `README.md`.
It has some basic information on how to use CLI commands.
Whenever you want to know more about how Angular CLI works make sure to visit
[the Angular CLI repository](https://github.com/angular/angular-cli) and
[Wiki](https://github.com/angular/angular-cli/wiki).

Some of the generated files might be unfamiliar to you.

### The `src` folder
Your app lives in the `src` folder.
All Angular components, templates, styles, images, and anything else your app needs go here.
Any files outside of this folder are meant to support building your app.

<aio-filetree>

  <aio-folder>
    src
    <aio-folder>
      app
      <aio-file>
        app.component.css
      </aio-file>


      <aio-file>
        app.component.html
      </aio-file>


      <aio-file>
        app.component.spec.ts
      </aio-file>


      <aio-file>
        app.component.ts
      </aio-file>


      <aio-file>
        app.module.ts
      </aio-file>


    </aio-folder>


    <aio-folder>
      assets
      <aio-file>
        .gitkeep
      </aio-file>


    </aio-folder>


    <aio-folder>
      environments
      <aio-file>
        environment.prod.ts
      </aio-file>


      <aio-file>
        environment.ts
      </aio-file>


    </aio-folder>


    <aio-file>
      favicon.ico
    </aio-file>


    <aio-file>
      index.html
    </aio-file>


    <aio-file>
      main.ts
    </aio-file>


    <aio-file>
      polyfills.ts
    </aio-file>


    <aio-file>
      styles.css
    </aio-file>


    <aio-file>
      test.ts
    </aio-file>


    <aio-file>
      tsconfig.app.json
    </aio-file>


    <aio-file>
      tsconfig.spec.json
    </aio-file>


  </aio-folder>


</aio-filetree>


<style>
  td, th {vertical-align: top}
</style>


<table width="100%">

  <col width="20%">

  </col>


  <col width="80%">

  </col>


  <tr>

    <th>
      File
    </th>


    <th>
      Purpose
    </th>


  </tr>


  <tr>

    <td>
      <code>app/app.component.{ts,html,css,spec.ts}</code>
    </td>


    <td>
      Defines the `AppComponent` along with an HTML template, CSS stylesheet, and a unit test.      
            It is the **root** component of what will become a tree of nested components      
            as the application evolves.
    </td>


  </tr>


  <tr>

    <td>
      <code>app/app.module.ts</code>
    </td>


    <td>
      Defines `AppModule`, the [root module](guide/appmodule) that tells Angular how to assemble the application.      
            Right now it declares only the `AppComponent`.      
            Soon there will be more components to declare.
    </td>


  </tr>


  <tr>

    <td>
      <code>assets/*</code>
    </td>


    <td>
      A folder where you can put images and anything else to be copied wholesale      
            when you build your application.
    </td>


  </tr>


  <tr>

    <td>
      <code>environments/*</code>
    </td>


    <td>
      This folder contains one file for each of your destination environments,      
            each exporting simple configuration variables to use in your application.      
            The files are replaced on-the-fly when you build your app.      
            You might use a different API endpoint for development than you do for production      
            or maybe different analytics tokens.      
            You might even use some mock services.      
            Either way, the CLI has you covered.
    </td>


  </tr>


  <tr>

    <td>
      <code>favicon.ico</code>
    </td>


    <td>
      Every site wants to look good on the bookmark bar.      
            Get started with your very own Angular icon.
    </td>


  </tr>


  <tr>

    <td>
      <code>index.html</code>
    </td>


    <td>
      The main HTML page that is served when someone visits your site.      
            Most of the time you'll never need to edit it.      
            The CLI automatically adds all `js` and `css` files when building your app so you      
            never need to add any `<script>` or `<link>` tags here manually.
    </td>


  </tr>


  <tr>

    <td>
      <code>main.ts</code>
    </td>


    <td>
      The main entry point for your app.      
            Compiles the application with the [JIT compiler](glossary)      
            and bootstraps the application's root module (`AppModule`) to run in the browser.      
            You can also use the [AOT compiler](glossary)      
            without changing any code by passing in `--aot` to `ng build` or `ng serve`.
    </td>


  </tr>


  <tr>

    <td>
      <code>polyfills.ts</code>
    </td>


    <td>
      Different browsers have different levels of support of the web standards.      
            Polyfills help normalize those differences.      
            You should be pretty safe with `core-js` and `zone.js`, but be sure to check out      
            the [Browser Support guide](guide/browser-support) for more information.
    </td>


  </tr>


  <tr>

    <td>
      <code>styles.css</code>
    </td>


    <td>
      Your global styles go here.      
            Most of the time you'll want to have local styles in your components for easier maintenance,      
            but styles that affect all of your app need to be in a central place.
    </td>


  </tr>


  <tr>

    <td>
      <code>test.ts</code>
    </td>


    <td>
      This is the main entry point for your unit tests.      
            It has some custom configuration that might be unfamiliar, but it's not something you'll      
            need to edit.
    </td>


  </tr>


  <tr>

    <td>
      <code>tsconfig.{app|spec}.json</code>
    </td>


    <td>
      TypeScript compiler configuration for the Angular app (`tsconfig.app.json`)      
            and for the unit tests (`tsconfig.spec.json`).      
                  
            
    </td>


  </tr>


</table>


### The root folder
The `src/` folder is just one of the items inside the project's root folder.
Other files help you build, test, maintain, document, and deploy the app.
These files go in the root folder next to `src/`.

<aio-filetree>

  <aio-folder>
    my-app
    <aio-folder>
      e2e
      <aio-file>
        app.e2e-spec.ts
      </aio-file>


      <aio-file>
        app.po.ts
      </aio-file>


      <aio-file>
        tsconfig.e2e.json
      </aio-file>


    </aio-folder>


    <aio-file>
      node_modules/...
    </aio-file>


    <aio-file>
      src/...
    </aio-file>


    <aio-file>
      .angular-cli.json
    </aio-file>


    <aio-file>
      .editorconfig
    </aio-file>


    <aio-file>
      .gitignore
    </aio-file>


    <aio-file>
      karma.conf.js
    </aio-file>


    <aio-file>
      package.json
    </aio-file>


    <aio-file>
      protractor.conf.js
    </aio-file>


    <aio-file>
      README.md
    </aio-file>


    <aio-file>
      tsconfig.json
    </aio-file>


    <aio-file>
      tslint.json
    </aio-file>


  </aio-folder>


</aio-filetree>


<style>
  td, th {vertical-align: top}
</style>


<table width="100%">

  <col width="20%">

  </col>


  <col width="80%">

  </col>


  <tr>

    <th>
      File
    </th>


    <th>
      Purpose
    </th>


  </tr>


  <tr>

    <td>
      <code>e2e/</code>
    </td>


    <td>
      Inside `e2e/` live the End-to-End tests.      
            They shouldn't be inside `src/` because e2e tests are really a separate app that      
            just so happens to test your main app.      
            That's also why they have their own `tsconfig.e2e.json`.
    </td>


  </tr>


  <tr>

    <td>
      <code>node_modules/</code>
    </td>


    <td>
      `Node.js` creates this folder and puts all third party modules listed in      
            `package.json` inside of it.
    </td>


  </tr>


  <tr>

    <td>
      <code>.angular-cli.json</code>
    </td>


    <td>
      Configuration for Angular CLI.      
            In this file you can set several defaults and also configure what files are included      
            when your project is build.      
            Check out the official documentation if you want to know more.
    </td>


  </tr>


  <tr>

    <td>
      <code>.editorconfig</code>
    </td>


    <td>
      Simple configuration for your editor to make sure everyone that uses your project      
            has the same basic configuration.      
            Most editors support an `.editorconfig` file.      
            See http://editorconfig.org for more information.
    </td>


  </tr>


  <tr>

    <td>
      <code>.gitignore</code>
    </td>


    <td>
      Git configuration to make sure autogenerated files are not commited to source control.
    </td>


  </tr>


  <tr>

    <td>
      <code>karma.conf.js</code>
    </td>


    <td>
      Unit test configuration for the [Karma test runner](https://karma-runner.github.io),      
            used when running `ng test`.
    </td>


  </tr>


  <tr>

    <td>
      <code>package.json</code>
    </td>


    <td>
      `npm` configuration listing the third party packages your project uses.      
            You can also add your own [custom scripts](https://docs.npmjs.com/misc/scripts) here.
    </td>


  </tr>


  <tr>

    <td>
      <code>protractor.conf.js</code>
    </td>


    <td>
      End-to-end test configuration for [Protractor](http://www.protractortest.org/),      
            used when running `ng e2e`.
    </td>


  </tr>


  <tr>

    <td>
      <code>README.md</code>
    </td>


    <td>
      Basic documentation for your project, pre-filled with CLI command information.      
            Make sure to enhance it with project documentation so that anyone      
            checking out the repo can build your app!
    </td>


  </tr>


  <tr>

    <td>
      <code>tsconfig.json</code>
    </td>


    <td>
      TypeScript compiler configuration for your IDE to pick up and give you helpful tooling.
    </td>


  </tr>


  <tr>

    <td>
      <code>tslint.json</code>
    </td>


    <td>
      Linting configuration for [TSLint](https://palantir.github.io/tslint/) together with      
            [Codelyzer](http://codelyzer.com/), used when running `ng lint`.      
            Linting helps keep your code style consistent.      
            
    </td>


  </tr>


</table>



~~~ {.l-sub-section}

### Next Step

If you're new to Angular, continue on the
[learning path](guide/learning-angular).
You can skip the "Setup" step since you're already using the Angular CLI setup.

~~~

