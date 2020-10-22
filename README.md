# Learn Angular

A repository for my angular learning.
The materials come from LinkedIn Learning course "Learning Angular" conducted by Ray Villalobos.
This course still use an old version of Angular (angular 5), so below information from my experience might be useful. My get around was to get the course materials in one folder and use only the src folder to be transferred to my project folder with new angular version.</br></br>
My system spesification: </br>
Angular: 10.1.7 </br>
Terminal: Windows Subsystem for Linux </br>
</br>
To make my learning easy to switch between the old and new angular version, first I create first my own angular project using the ng new command:
```console
ng new [project-name]
```

The main difference between this two versions are:
1. The old version use angular-cli.json while the new one use angular.json
2. The code inside polyfill.ts is slightly different

After I create my own angular project, I clone the git repositories in another folder. Of course we cannot easily run this repositories with current system. So I just use this folder to change between branches, and then copy the src folder only to my own angular project. So I only need take care the second problem everytime I change the branch for different material.</br>

Notes for important terminal command: </br>
Change between branches
```console
git stash && git checkout [branch-name]
```
After i checkout the branch that I want to use, I copy the src project using terminal.
```console
cp -r src ../[project-name]/
```


If you are running this material on the newest angular version, it can have some problem with the code inside polyfills.ts</br>
You need to update this code: </br>
````typescript
import 'core-js/es7/reflect';
````
to: </br>
````typescript
import 'core-js/es/reflect';
````

When I run the ng serve with Linux subsystem on Windows 10 i need to add the command like this to make the browser auto update the file changes:

```console
ng serve --poll=2000
```
Other option: add "poll"=2000 on angular.json so it become like this:
```javascript
"serve": {
   "builder....
   "options": {
        "browserTarget": "[project-name]:build",
        "poll": 2000
   }
```
source: </br>
https://stackoverflow.com/questions/48092880/ng-serve-not-detecting-file-changes-automatically
https://stackoverflow.com/questions/51930195/what-is-the-function-of-poll-flag-in-cli

There is also a different approach for a case project 3 about the subcomponent. The input method is no longer valid and the solution already discussed in below Q&A.

https://www.linkedin.com/learning/questions/fyithe-input-method-used-in-this-video-is-no-longer-valid-to-perform-this-function-you-must-import-input-from-6635734562259419136

