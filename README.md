# AngularYourFirstApp

Application to Learn Angular concepts based on [Angular Tutorial](https://angular.io/start)

![Scheme](/readmeImages/new-app-all.gif)



Pre-requisites
--------------
- [Visual Studio Code](https://code.visualstudio.com/download)
- [Node.js](https://nodejs.org/en/)
- [Visual Studio Code Chrome Debugger Extension](https://code.visualstudio.com/docs/nodejs/angular-tutorial#_debugging-angular)
- [Angular CLI](https://angular.io/guide/setup-local#step-1-install-the-angular-cli)


References
----------
- [Getting Started with Angular: Your First App](https://angular.io/start#getting-started-with-angular-your-first-app)
- [Using Angular in Visual Studio Code](https://code.visualstudio.com/docs/nodejs/angular-tutorial)



Steps
------
1. Configure local machine environment (see guides below).
2. Download code and follow guide on [Angular Tutorial](https://angular.io/start).



Angular Installation
----------------------------------------
1. Download Visual Studio Code
   https://code.visualstudio.com/docs/?dv=osx 

2. Check Node.js
   https://angular.io/guide/setup-local#prerequisites
   From the Terminal run
      node -v
   
   See guide for update or install in 
   https://www.webucator.com/how-to/how-install-nodejs-on-mac.cfm

2.1 Open the Terminal.
2.2 Enter node - v in the Terminal and press Enter.
  ```
      Nats-MacBook-Pro:Webucator natdunn$ node -v
  ```
2.3  If you do have Node.js installed, it will output the version.
2.3.1 Update to the latest version using npm i -g npm. If you get a bunch of checkPermissions warnings, you should run the command as the superuser like this: sudo npm i -g npm
2.3.2  You now have the latest version installed. You do not need to continue with these instructions.
2.4 If you do not have Node.js installed, it will output something like -bash: node: command not found. Continue with these instructions to install it.
2.5 Go to nodejs.org. You'll see download links for MacOS.
    Install the LTS (Long Term Support) version. The Current version has the latest features, but may be more prone to changes and bugs than the LTS (Long Term Support) version.
2.6 When the file finishes downloading, locate it in Finder and double-click on it.
2.6.1  If there is a permission error: Open System Preferences -> Security and Privacy -> General tab -> Allow package Open Anyway.
2.7 Go through the entire installation process.
    Leave the Installation as default
  ```
    This package has installed:
	• Node.js v12.16.1 to /usr/local/bin/node
	• npm v6.13.4 to /usr/local/bin/npm
    Make sure that /usr/local/bin is in your $PATH.
  ```    
  ```
xengars-MacBook-Pro-2:~ xengar$ echo $PATH
/Users/xengar/Library/Android/sdk/platform-tools/:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/share/dotnet:/opt/X11/bin:/Applications/Xamarin Workbooks.app/Contents/SharedSupport/path-bin
  ```

2.8 Enter node - v in the Terminal to verify that Node.js is installed correctly and to see the version of Node.js that was installed.
  ```
xengars-MacBook-Pro-2:~ xengar$ node -v
v12.16.1
  ```

3. Check that you have the npm client installed, run npm -v in a terminal/console window.
   This setup guide uses the npm client command line interface, which is installed with Node.js by default.
  
  ```
xengars-MacBook-Pro-2:~ xengar$ npm -v
6.13.4
  ```

4. Install the Angular CLI
   https://angular.io/guide/setup-local#step-1-install-the-angular-cli 
 
  ``` 
xengars-MacBook-Pro-2:~ xengar$ sudo npm install -g @angular/cli
Password:
npm WARN deprecated request@2.88.2: request has been deprecated, see https://github.com/request/request/issues/3142
/usr/local/bin/ng -> /usr/local/lib/node_modules/@angular/cli/bin/ng

> @angular/cli@9.0.2 postinstall /usr/local/lib/node_modules/@angular/cli
> node ./bin/postinstall/script.js

? Would you like to share anonymous usage data with the Angular Team at Google under
Google’s Privacy Policy at https://policies.google.com/privacy? For more details and
how to change this setting, see http://angular.io/analytics. No
+ @angular/cli@9.0.2
added 260 packages from 205 contributors in 27.898s
xengars-MacBook-Pro-2:~ xengar$ 
  ```


Configure Launching from the command line   (code .)
-------------------------------------------------------
See https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line

1. Launch VS Code.
2. Open the Command Palette (F1) and type 'shell command' to find the Shell Command: Install 'code' command in PATH command.
3. Restart the terminal for the new $PATH value to take effect. You'll be able to type 'code .' in any folder to start editing files in that folder.



How to Create a Project in Visual Studio
----------------------------------------------
Requirements:
 - Visual Studio Code
   Everything is done from the terminal there.
 - Node.js with npm 
 - Angular CLI
 - A directory for Angular projects
   /Users/xengar/Angular

See guide at https://code.visualstudio.com/docs/nodejs/angular-tutorial

1. Create a new project.
   Open Visual Studio Code and use the terminal there to run commands.
   ng new my-app
   Note: The ng new command prompts you for information about features to include in the initial app. Accept the defaults by pressing the Enter or Return key.

2. Run the application
   Go to the workspace folder (my-app).
   Launch the server by using the CLI command:  ng serve --open
   You should see "Welcome to app!!" on http://localhost:4200 in your browser. We'll leave the web server running while we look at the application with VS Code.
 Ctrl + c <- to Stop properly and release resources

3. Open the application in Visual Studio Code
  Open another terminal (or command prompt) and navigate to the my-app folder and type code .

4. Change the title
 - expand the src\app folder and select the app.component.ts file.
 - update the sample application to "Hello World". Go back to the app.component.ts file and change the title string in AppComponent to "Hello World".

  ```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Hello World';
}
  ```


Install chrome Debugger Extension
----------------------------------------
https://code.visualstudio.com/docs/nodejs/angular-tutorial#_debugging-angular 

1. In Visual Studio Code, Open the Extensions view (Ctrl + Shift + x) and type 'chrome' in the search box. You'll see several extensions which reference Chrome. Press the Install button for Debugger for Chrome.

2. set a breakpoint in app.component.ts  in title = 'Hello World';

3. Configure the Chrome debugger
  Go to the Debug View (Ctrl + Shift + D) and click on the gear button to create a launch.json debugger configuration file. Choose Chrome from the Select Environment drop-down list. This will create a launch.json file in a new .vscode folder in your project which includes a configuration to launch the website.

We need to make one change for our example: change the port of the url from 8080 to 4200. Your launch.json should look like this:

  ```
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "chrome",
      "request": "launch",
      "name": "Launch Chrome against localhost",
      "url": "http://localhost:4200",
      "webRoot": "${workspaceFolder}"
    }
  ]
}
  ```

