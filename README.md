# Learn Angular

A repository for my angular learning.
The materials come from LinkedIn Learning course conducted by Ray Villalobos.

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

Notes for important Github command: </br>
Change between branches
```console
git stash && git checkout [branch-name]
```
