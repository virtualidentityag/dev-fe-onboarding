# Onboarding Fragen und Musterantworten
Hier die Liste der Fragen inklusive Antworten, welche darauf abzielen die Grundlagen der Frage abzudecken.  

#### Legende:

(\*) - Bei diesen Fragen war ich mir unsicher, ob diese nicht entfernt werden könnten  
(\*\*) - Schreibfehler im Onboarding Dokument  
(\*\*\*) - Hier war ich mir unsicher bei der Antwort  

## Fundamentals I (HTML && CSS)
###   Preparation

- What's Git?
    > Git is a versioning system that allows teams to collaboratively work on projects.

- What is a repository? 
    > A repository is essentially a "project" or part of a project that has been put into a versioning system, in most cases Git. It's a central place where the data lays that makes up the project. 

- What is a branch? 
    > (The concept of branches is a difficult one to put into a succinct definition and usually needs further elaboration)  
    Branches are the different "versions" of the same project. When multiple people are working on a project and each of them are working on different features, then each of them makes their own branch based on the "master" branch. That way, all their work doesn't conflict. 

- What is a commit? 
    > A commit is the act of taking the work you have done locally and marking them as ready to be deployed to the central repository. Ideally, a commit represents one bugfix or one added feature (generally one coherent change). 

- What does push mean? 
    > To push is to take the commits you have made locally and putting them onto the remote system. Before a push, the changes you have committed haven't left your local system yet.

-   What does fetch mean? 
    > "git fetch" checks the list of remote branches and imports the new ones to your local system. Fetch does not pull the changes of each branch. "git fetch --prune" also deletes any local branch that does not have a corresponding remnote branch.

-   What is a pull request? 
    > A pull request (or PR) is a mechanism that has the same goal as merging a (feature) branch into another branch (usually the develop or master branch). When you open a PR, a thread is opened on the Git system where other collaborators can see the changes that have been made, make comments and approve or decline (because the changes need improvement or for other reasons) the request to merge. The purpose of this as opposed to just merging your branch into the main branch is for others to be able to do a code review and detect any potential issues before they're merged into the main branch. 

-   What's the difference between Git and GitHub? 
    > Git is the versioning technology that all these questions are based on. GitHub is just one of multiple web platforms that host/enable you to use Git functionality. Another example would be Bitbucket. 

-   What's the Git Flow?
    > The Git Flow is the approach that is used for branch management. Here's a summary from atlassian:  
    - A develop branch is created from master
    - A release branch is created from develop
    - Feature branches are created from develop
    - When a feature is complete it is merged into the develop branch
    - When the release branch is done it is merged into develop and master
    - If an issue in master is detected a hotfix branch is created from master
    - Once the hotfix is complete it is merged to both develop and master

-   What is the .gitignore and its purpose? 
    > The .gitignore file is a list of files, filetypes and folders that will be ignored by the Git system so that it cannot be commited or pushed into the repository. Some files do not and should not be checked into the repository because of multiple reasons. 
    1) The files are autogenerated by other files (dist folder, node_modules folder, ..) 
    2) The files are specific to the developer (.vscode, ..) 
    etc. 

###  Page Layout

-  What are semantic elements in HTML5? 
    > A semantic element clearly defines its purpose to the browser and the developer (as opposed to a non-semantic element).

-   When do do you use which semenatic element? (*)

-   Why is the correct hierarchy of headlines important? 
    > SEO and accessibility.

-   Should you use multiple h1 headlines in one HTML document? (*) - similar as question before
    > No. Reason: SEO.

-   How do you include webfonts? 
    > Multiple ways. 
    - CDN/Hotlinking to online resource.
    - Downloading and including font in framework. 
        -> @font-face 

-   Which webfont formats could be used? Why are there different formats? (*)
    > EOT, WOFF, WOFF2, TTF, SVG | Different support in different browsers. 

-   How can you provide different font weights and different font styles for a webfont? (*)
    > Registering each font-weight and font-style as a @font-face. 

-   How are CSS stylesheets embedded? 
    > `<link rel=".." />` (or inline with `<style>`)

-   What is the purpose of normalize.css? 
    > Different browsers have different "default" CSS settings. normalize.css aims to make the "blank slate" of each browser the same. 

-   What's the effect of specificity(**) of CSS selectors? 
    > Specificity decides which rule is applied to an element. If there are multiple instances of the same attribute being set on the same element, the one with the higher specificity wins. If the specificity is the same, the one that is registered last is applied. 

-   What has to be considered when declaring CSS selectors? (***)

-   What does !important do and why shouldn't you use it? 
    > When you add !important to a css declaration, it automatically overrides any other declaration without !important. By doing this, you are undermining the concept of specificity and building very error-prone and hard to debug code. If for example, in the future, you need something even stronger than the !important you just wrote, you are out of options. 

-   What are vendor-prefixes and which ones do exist? (*)
    > Vendor prefixes are made for specific browsers and used for experimental or nonstandard CSS properties. Internet explorer/edge has "-ms-", webkit based browsers like Safari or Chrome have "-webkit-", Mozilla Firefox uses "-moz-".

-   What are pseudo elements? What is their purpose?
    > Pseudo elements such as ::before or ::after are elements that don't actually "exist" in the DOM and are only simulated and editable by CSS. Pseudo elements are not the same as pseudo classes.

-   What are shorthand properties? Which ones do exist?
    > Shorthand properties sum up multiple CSS declaration that can be thought of as "semantically connected". Example: padding (padding-top, -right, -bottom, -left), border (border-width, -style, -color), background (background-clip, -color, -image, -origin, -position, -repeat, -size, -attachment)

-   When do you use img tags and when CSS background images? (***)

-   What are the different position properties and what's their effect on surrounding elements?
    - relative: positions the element according to the flow of the document.
    - absolute: positions the element absolutely to the next relatively positioned parent element. Removes the element from the normal document flow. 
    - fixed: positions the element absolutely in the viewport, i.e. the element will stay in position when the user scrolls. Removes the element from the normal document flow. 
    - static: same behaviour as "relative" except that the properties top, right, bottom, left have *no* effect. Default setting for any element.
    - sticky: The element is positioned according to the normal flow of the document, and then offset relative to its nearest scrolling ancestor and containing block (nearest block-level ancestor), including table-related elements, based on the values of top, right, bottom, and left. The offset does not affect the position of any other elements. (**)

-   What is z-index and what's the effect? 
    > The z-index decides the stacking order of the elements on the website. An element with a higher z-index will overlap/cover an element that has a lower z-index. 

-   How can you place two block element side by side? (*)
    > float/flexbox/css-grid

-   What is the CSS box-model?
    > Each element in CSS follows the "box-model", that means it has a margin, border, padding and inner dimensions. 

-   What is CSS flex-box? When do you use it? (*)
    > Flex-box is a way to position/layout elements on the website. It's a more modern alternative to positioning elements with the float property. 

### Navigation

-   Which semantic element should be used for page navigation?
    > `<nav>`

-   How can you add semantic meaning to any HTML elements?
    > classes / IDs

-   Why should semantic attributes be added to html elements? (***)

### Responsive Webdesign

-   What is responsive design?
    > Responsive design is web design that changes and adapts based on the size of the screen. 

-   What are media queries?
    > Media queries are CSS selectors that detect the screen size (and other things) and apply rules based on them. 

-   How can you realize a responsive image? (* / ***)

-   What do you use the viewport meta tag for? (*)

### SVG Sprites

-   What is SVG?
    > Scalable Vector Graphics - file format for vector based images (as opposed to pixel based)

-   What are SVG sprites and how do you use them? (***)

-   What are the advantages of SVG sprites compared to icon fonts and pixel graphics?
    > They're scalable, small in size and they're more easily manipulatable from within the code. 

## Fundamentals II (SASS && JavaScript)

### Preparation

-   What is a package manager and what are the benefits of using one?
    > A package manager, in the context of web development, is a program that you install on your computer that automates the process of installing, upgrading, configuring and removing packages (= 3rd party code) that are used in projects.  

    > A package manager saves you a lot of work and time, reduces the error-proneness of your project (because computers and programs make less mistakes than humans) and improves collaboration by enabling collaborators to have the same set of packages. 

-   What is the purpose of the package.json file?
    > The `package.json` file serves multiple purposes, but the most important one is listing the packages that a project requires (including version numbers and possibly source URLs). Other purposes are information fields for publication purposes, versioning and script aliasing. 

-   What is the node_modules folder?
    > The `node_modules` folder is where the installed packages of a project live. It's auto-generated by running the install command of your package manager. It's generally not checked into a versioning system to save space and streamline the versioning/checkout process. 

-   What happens when you execute npm install? Why is it necessary to execute this command?
    > `npm install` downloads and installs (--> `node_modules`) all the packages listed in the `package.json` file including their respective dependencies.  

    > It's necessary to execute the command because when you checkout a project from GIT, it generally only includes a list of packages that need to be installed (`package.json`) and not the packages themselves (`node_modules`). 

-   How do you add a new package to a project?
    > Either by running the respective install command of your package manager (For yarn: `yarn add <package-name>`, for NPM: `npm install <package-name>`) or by writing the package-name into `package.json`'s `dependecies` field and running the general `install` command of your package manager (`yarn` or `yarn install`, `npm install` or `npm i`). You can specify specific versions and sources of the package in both cases. 

-   What is a taskrunner and what are the benefits of using one?
    > A taskrunner is a programm for the automation of certain procedures in projects.

    > A taskrunner saves you a lot of work and time and reduces the error-proneness of your project (because computers and programs make less mistakes than humans).

-   What are good tasks to automate? Think of typical processes that need to be executed for a project to run.
    > compiling, copying, moving, renaming, minifying, ugilifying, bundling files