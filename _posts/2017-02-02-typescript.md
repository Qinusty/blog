---
layout: post
title: My experiences with Typescript
---

Coming from a programming background which was primarily strictly typed (except Python), I had learnt to fully appreciate the 
vast benefits which come from having variables which are statically typed. Primarily, this helps reduce the frustration of runtime errors.
I first understood these benefits while working with Haskell, a statically typed pure functional language. The amount of time fixing compilation errors was
increased but I hardly ever got runtime errors besides the occasional logic error.

Back to Typescript, the relevance of the above paragraph is that my decision to use Typescript in my pursuit to learn ECMAScript (The scripting language 
often referred to as javascript) was primarily based on the feature of Typescript which allows you to type variables. 
This as well as the ability to write code and transpile (source to source compilation) the code to any 
version of ECMAScript I wanted, this was a massive bonus to me as the I had learnt about of the new features ECMAScript 2015 and 2016 (ES6 and ES7) contain.
These features include common OO (Object Oriented) features such as classes, generators and Lambda functions which were features I was very comfortable
with after using other languages. The fact I could write code up to the latest standard and be able to run this code on any browser despite a lack of ES6/ES7 support.
The final thing that got me to use Typescript is that Typescript is a superset of ECSMAScript which means that any ECSMAScript code can be written into a typescript 
file and be valid, this means that I can learn both ECSMAscript and Typescript at the same time.

To learn Typescript, I decided to create something small which uses some of the features of both Typescript and ES6. I decided on rewriting my [A2 Project](www.github.com/qinusty/A2Project)
which I have struggled to compile lately due to using the XNA framework which was discontinued and support was not included in versions of visual studio past VS 2013.
My first steps to reimplement the project was to look at ES6 classes and which other modern features of ECSMAScript I could use to help me with the process. I found a
nice place to start with ES6 classes and Typescript interfaces, this allows me to further rely on the static typing of Typescript to reduce mistakes that I will 
innevitably make during my implementation. Interfaces are another feature I am used to having when engineering a solution to a problem, Below is an example of a Typescript interface in my implementation.

```typescript
interface IEntity {
    position: IPos
    image: HTMLImageElement
    size: ISize
    draw(ctx: CanvasRenderingContext2D) : void
}
```

For those not familiar with interfaces, an interface acts as a contract for the class which implements the interface, and Typescript allows you to type a variable as 
an interface to ensure any object assigned to the variable must include those attributes. This was great, I was able to design my classes and interfaces similar to 
how I would do so in a language such as Java or C#. 

## My setup (Workflow)
For my IDE, I am using [VSCode](https://code.visualstudio.com/), a cross-platform, open source editor by Microsoft which fully supports Typescript (Another of Microsofts
open source projects) and has an integrated terminal, a feature which I love having in any IDE.  

I am doing this as a browser based project using a HTML5 canvas, For this I am required to use another project called [Webpack](https://webpack.github.io/) which
bundles multiple js files into a single js file, thankfully it also supports transpilers to be ran prior to the bundling. So while developing the project I can simply
run `webpack --watch` in my integrated terminal, which watches the current directory for any changes to files, and then repacks the files into a file which by default, is
bundle.js. So I can have, my modules and files seperated and use webpack to bring them all together into a single js file for my HTML script tag to call upon.

## Conclusion
I think typescript is a great way to improve the quality of your ECSMAScript applications, whether for NodeJs or web applications, it allows you to use the latest
features in ECSMAScript with ease and keep an easy to maintain, scalable code base. Babel is another option to use and has faster releases for ECSMAScript features.





