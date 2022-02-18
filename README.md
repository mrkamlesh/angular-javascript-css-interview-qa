------------------
JS Interview QnA
------------------


Find the output of the following
==========================
let z = function () {
  
  if (true) {
    console.log(y)
    console.log(m)
    
    var y = 2;
    let m = 3;
  }
}
var y = 100;
z();


------output------------
 = undefined
 = Uncaught ReferenceError: Cannot access 'm' before initialization
&
  //console.log(y) = 2
  //console.log(m) = Uncaught ReferenceError: m is not defined
----------------

==========JS================
this Keyword
How does JavaScript and JavaScript engine work?

Closures in JavaScript? advantage..
hoisting in JavaScript?

Event loop in JS.
              What is the temporal dead zone? let vs var.
              Service worker vs web worker.
              call, apply & bind
callback vs promise
es6 features, arrow function, spreed oparator=>[...]

javaScript Array methods => filter, map, some, find, reduce
javascript shallow copy and deep copy

=============Angular============
bootstraps the application Root Module - What is main.ts?

<router-outlet></router-outlet>

Component Life Cycle Look? - ngOnChanges vs ngDoCheck

What is the difference between pure and impure pipe?
How to share data with siblings, child-parent, route params


What are the class decorators in Angular?

lazy loading   ===>  @Injectable({    providedIn: 'root'  })

Template driven forms and reactive forms

property binding is done using "[ ]" attribute and 
event binding is done using "( )" attribute.

How to catch error in forkJoin?
ng-template vs ng-container

  What is Reactive Programming? What do you understand by RxJS?

What is Subject? Diff between BehaviorSubject and Observable in RxJS?
mergemap vs switchmap

What is the use of forRoot and forChild in Angular? - we should call forChild() in feature modules because forRoot() was already called in the root module 

What is difference between ViewChild and ViewChildren?
What is difference between JIT and AOT?

service worker vs web worker
What are the security principles in angular?

============HTML============
<!DOCTYPE html>
html4 vs html5



============CSS============
Pseudo-classes vs pseudo-elements 
What is CSS pre processor?
CSS grid vs flexbox


------------output------------

2+'5'+3			 => '253'
-2+'5'+3		 => '-253'
2-'5'+3			 => 0
2+'5'-7			 => 18

typeof null 					=== 'object';
typeof undefined 				=== undefined;

typeof Infinity 				=== 'number';
typeof NaN 						=== 'number';
typeof (typeof 1) 				=== 'string';
typeof {a: 1} 					=== 'object';
typeof [1, 2, 4] 				=== 'object';
typeof function () {}  			=== 'function'



1) Deference between Angular js and angular. Can we use jQuery instead of angular or react?
  
	Angular JS:
		- Written in JavaScript.
		- AngularJS uses terms of scope and controller(MVC).
		- AngularJS uses $routeprovider.when() for routing configuration.
		- Differences in template engine-  ng-model, [()]


	Angular:
		- Written in Microsoft’s TypeScript language, Superset of ECMAScript 6 (ES6).
		- Angular supported mobile browsers. Native app using ionic native
		- Angular uses @Route Config{(…)} for routing configuration.
		- Performance - speed.
		- Fast development process.
		- Better structure compare to AngularJS


2) Deference between Angular and React. which you will prefer and why?
	Angular
		- By Google
		- Based on TypeScript
		- Real DOM
		- Framework
		- Two way data-binding
		- Google Material Design
		- Ease of Update

	React
		- By Facebook
		- Based on JavaScript and JSX
		- Virtual DOM
		- Library
		- One way data-binding
		- Highly customized app

3) Angular Components vs Directives. How it works internally.

	- A @Component requires a view whereas a @Directive does not.
	Component - create a reusable set of DOM elements of UI.
			  - The most basic UI building block.

	Directive - behaviour to supplement existing DOM elements.
			  - changes the appearance or behavior of an existing DOM
		- Structural directives — Change the DOM layout by adding and removing DOM elements.
		- Attribute directives — Change the appearance or behaviour of an element, component, or another directive.


4) Angular Decorator, Injectables vs inject.

	@Inject()
		is a manual mechanism for letting Angular know that a parameter must be injected.
		When using TypeScript, @Inject is only needed for injecting primitives.

	@Injectable()
		lets Angular know that a class can be used with the dependency injector.


5) Different ways to share data between sibling/nested components in angular.

	1. Parent to Child component: @Input(), @Input(‘childToMaster’) masterName: string;
	2. Child to Parent component: @Output() childToParent = new EventEmitter<String>();
	3. Sharing data using ViewChild decorator: @ViewChild(AppChildComponent) child;
	4. Sharing data between not related components: Service, BehaviorSubject, setter, getter method


6) JWT whole concept (backend vs Client) how to create JWT token in node js, how to validate token, client side handling.

	Security - Authentication With JSON Web Tokens (JWT).
	Validating JWT Signatures - RS256.
	encrept using - salt key - RS256 vs HS256.
	header Authorization: `Bearer ${currentUser.token}`


7) how to setup NgRx in your project. explain reducers, actions, store, selectors, effects etc.

	- NgRx libraries used for state management. a Redux implementation(a state management tool).
	- npm install @ngrx/store --save
	- yarn add @ngrx/store
	- store > actions > effects > reducer > selectors


8) Observable vs promises.
	Promise
		- to handle asynchronous operations synchronously.
		- Handles a single event when an async operation completes or fails.
		- Promise is asynchronous
		- Resolve, Reject, pending, fulfilled
		- pending: this is the initial state, neither fulfilled nor rejected.
		- fulfilled: the operation completed successfully.
		- rejected: the operation failed.

	Observable
		- An Observable is like a Stream
		- Synchronous / asynchronous
		- Observables are stream of data
		- Observables can be canceled


9) How to call multiple APIs at the same time? what will happen if one of the API get failed. how you will handle that.
 		- forkjoin( catchError() ).subscribe();

 		 Observable.forkJoin(
		  	this.http.post<any[]>(URL).pipe(map((res) => res), catchError(e => of('Oops!'))),
  			this.http.post<any[]>(URL).pipe(map((res) => res), catchError(e => of('Oops!')))
		)
		.subscribe(res => this.handleResponse(res));


10) How to reduce angular application build size. tree-saking.
	- ng build --prod
	- ng build --prod --aot
	- ng build --prod --build-optimizer --optimization


11) Angular Routing with lazy-load and Route Guard.
	
	- Route guards are available in Angular:
		- CanActivate
		- CanActivateChild
		- CanDeactivate
		- Resolve
		- CanLoad

12.) Reactive forms -
	Reactive forms use an explicit and immutable approach to managing the state of a form at a given point in time. Each change to the form state returns a new state.
	- reusable, more robust, testable, more scalable
	- Handling a event based on a debounce time
	- Handling events when the components are distinct until changed
	- Adding elements dynamically


13) how to detect route change event in angular.
	
	- router.events.subscribe((val) => {})
	- router.changes.subscribe((val) => {})


1.) Difference between component and container.
	Component is a directive which use shadow DOM to create encapsulate visual behavior called components.
	 - used to create UI widgets.

	Directives is used to add behavior to an existing DOM element.

2.) How to use directives as component?
	Component is a directive which use shadow DOM to create encapsulate visual behavior called components. Components 
	are typically used to create UI widgets. Directives is used to add behavior to an existing DOM element. Component is used to break up the application into smaller components.


3.) Explain component lifecycle hooks?
	ngOnChanges()
	ngOnInit()
	ngDoCheck()	
	ngAfterContentInit()
	ngAfterContentChecked()	
	ngAfterViewInit()
	ngAfterViewChecked()
	ngOnDestroy()


4.) how to pass data from one page to another page using router navigation. (except URL Params/Query param)
	1) Required Routing Parameters:
	2) Route Optional Parameters:
	3) Route Query Parameters:

	--How to pass object using router navigation?
	
	Send: ---------passing state to NavigationExtras in the Router
	this.router.navigate(['action-selection'], { state: { example: 'bar' } });
	
	Receive:
	constructor(private router: Router) {
	  console.log(this.router.getCurrentNavigation().extras.state.example); // should log out 'bar'
	}


5.) What are the advantage of angular?
	CROSS PLATFORM
	SPEED AND PERFORMANCE
	PRODUCTIVITY - Template, Angular CLI, IDEs
	Testing, Animation, Accessiblity


6.) What are the features of es6?
	arrows.
	classes.
	enhanced object literals.
	template strings.
	destructuring.
	default + rest + spread.
	let + const.
	iterators + for..of.
	Promises
	International & locality


7.) How to handle http request method: get, post?
	HttpClient service class in @angular/common/http.



Subjects
----------
A Subject is a special type of Observable which shares a single execution path among observers.
	There are 4 variants of subjects:

		Subject - No initial value or replay behavior.
		AsyncSubject - Emits latest value to observers upon completion.
		BehaviorSubject -  Holds one value. Requires an initial value.
		ReplaySubject(count) - Emits specified number(count) of last(buffer) emitted values.



subject vs behaviour subject
css - two way to center
difference between CSS and SCSS.
CSSS flex, Flexbox properties
px vs rem
grid vs flexbox
async await
promise all
obserable
decorator from angular or typescript
pure vs impure pipe
design pattern
pure function
Unit testing(Karma & Jasmine, QUnit) vs End-to-End(Protractor - ng test) Testing
debugger
-------------------
event binding in angular
css preprocessor

reactive vs template driven forms

----------------------------
diff in ng8 and ng9, ng10
diff aot vs jit, lvy
promise for complete 3 request or any one request
virtual class
interface vs abstract class
var vs let
call vs apply vs bind
higher order function in js



reduce function
arrow function vs function
call, apply vs bind
subject vs behabearsubject
mjhjmj,..kj




To generate android build:
set ANDROID_SDK_ROOT=D:\work\sdk
set JAVA_HOME=D:\work\java\jdk1.8.0_65
set PATH=%PATH%;D:\work\sdk\platforms\android-27;D:\work\gradle\gradle\gradle-6.5\bin;D:\work\sdk\platform-tools
Q. Tell me something about yourself?
Your name: My name is Ashwani Sharma
Place: Basically I am from Distt. Muzaffarnagar UP. Currently I have been staying in Noida since 2007.
Academic qualification: I have graduated from Kalinga University Raipur. My highest qualification is MCA.
Experience: I am carrying an experience of 10 years in UI and Front End Development. I have good hands on HTML5, CSS3, JavaScript, Angular 2, Bootstrap, jQuery.
Family So for my family background is concerned we are 3 brothers and 1 sister.
Hobbies Watching informative videos and  walking

Q. What is the High Level architecture of Angular, how it renders on page?
Q. How angular inject components, like parent component, child component?
Q. How do you start your project?
https://blog.angularindepth.com/setting-up-angular-from-scratch-1f518c65d8ab

Q. What is Lazy loading and what are the principles of Lazy Loading and how to integrate it?
Q. draw the UI of your project on paper.
Q. when logging in the application what happens internally, what angular does internally?
Q. have you faced any compatibility issue in IE browser and other browsers?
Q. What is the command to generate components using CLI?
ng generate Content ComponentName

Q. How many types of directives in angular ?
There are 3 types of directives in Angular:
1. Component directives
Directives with a template, class, css style

2. Structural directives
Structural directives are used to change the DOM layout by adding or removing or manipulating DOM element. 
Example: *ngIf, *ngFor, *ngSwitch ( structural directives has asterisk (*) before them) * will change in <ng-template> at run time

3. Attribute directives
Attribute directives are used to change the behaviour of the DOM element. 
Example: ngStyle, ngClass

Q. What is ngStyle? how to integrate? What is the syntax? What is the type of ngStyle?

Q. What is viewChild in angular?
“The Child Element which is located inside the component template”, 
viewChild is a decorator, using viewChild we can inject components, directives or elements inside the template.

Q. What is an Interceptor ? How to integrate an Interceptor ?
Adding the extra information over the http request is called interceptor, by making a clone of that request and add request in that clone

Steps to implement interceptor:
1.	Include packages [ HTTP_INTERCEPTOR] in app.module.ts and declares in providers also

Q. What is Provider in Angular?
Provider is an Inversion of control (IOC) container.
Providers are classes that create and manage service objects. Provider is used to register the classes to an angular module as a service. And then, this service class can be used by other components during itself creation phase in the module.

Q. What is the Singleton pattern how to achieve?
Static object or Global object is known as Singleton. We write a program in a way that it will create Static object.
In Singleton we create a private constructor, so that it can not be instantiated outside the class.
If a class has Private constructor it can’t have member functions.

Routing, auth guard, pipe, service, directives, decorators, push notifications, interceptor, error handling, rxjs(dbounce, mergemap)
Q. What is JSON web token? What are the advantages of JSON web token? How to integrate JSON web token? How JSON web token works?
Advantages:
No Session to manage (stateless): JWT is self contained digitally signed, has authentication info and expire time info it has header, body and digital signature
Portable: A single token can be used with multiple backends
No cookies required, it is mobile friendly
Decoupled/Decentralized: can be generated anywhere

Q. What is sms protocol?
Q. What is a Decorator in Angular?
Q. How to create Custom Directive in Angular, what is the method (create to change bg of element)?
Q. How to create a Custom Pipe in Angular What is the method inside the custom pipe ?
Q. What is the Pipe annotation?
Q. What is the method to apply Pipe?
Q. How to integrate Pipe?
Q. What is Angular Universal?
Q. How to handle multiple Events using Observable?  => fromEvent  then Observable.merge
Q. What is the difference between Native and Responsive application?
Q. What is the best search pattern for mobile apps?
Q. How to integrate multilingual support in the app?
Q. What is change detection in Angular?
1.	ChangeDetectionStrategy.Default 
2.	ChangeDetectionStrategy.onPush
Q. How JavaScript works in the browser? Or How Browsers read JavaScript?
Q. What is Tree Shakable in Angular?  => Tree shaking is a build step which removes unused code from the code base at build time.
Q. Difference between JIT and AOT?
Q. What is @ViewChild and @ViewChildren in Angular?
Q. Difference between template driven and reactive forms in Angular?
Q. What is Rout resolver in Angular? How to load Heavy DOM in Angular?
Q. Component lifecycle hook and difference between them. [ UX Trendz best video for this]
Q. What is Angular Transpiling how it works?
Q. What is Host Binding in Angular?
Q. What is the difference between *ngIf and ngHidden?
Q. How to get route param data? Using paramMap().get method
Host binding is used in custom directive to transform content for example: apply class or attribute to the host element.
Q. What is the HostListener in Angular?
Q. What is the difference between Constructor() and ngOnInit(). 
Q. Why incremental DOM slower than Virtual DOM?
Q. What are the steps to integrate third party API in the project.
Q. How to integrate popup for the user logging in first time?
Q. What is the difference between Service and Component?
Q. What is service data type?
Q. What is http call return type?
Q. How to get 2 or more than 1 API data in one go? Using forkJoin() method
Q. What are the Generics in Angular?
Q. What are the ways to download Components in Angular?
Q. What is Snapshot in Angular?
Q. What is queryparams and queryselector in Angular?
Q. Can we apply multiple AuthGuard to a single route? Yes by putting comma separated guard names inside canActivate array like this : canActivate: [GuardOne, GuardTwo]
Q. Steps to integrate an Angular Form in the project [Reactive or Template Driven] ?
Q. How to inject Service? How Service communicate? What are the Service methods?
Q. What is the difference between Factory and Service?
Q. Can we change the name of canActivate method inside component? Ans. No [it will show error]
Q. What is the difference between CanActivate and CanActivateChild ?   ===========
Q. Difference between Ang 7 and Ang 8?
Q. How to handle error in Observable?
Q. How to use cookies in Angular?
Q. How to make app compatible in different browser IE, EDGE, Chrome, Firefox?
Q. Encryption decryption in JavaScript . for example password encryption.
Q. What is Angular CLI? 
Q. How to load select menu in ngOnInit() lifecycle?
Q. How to make HTML elements editable? Ans. using contenteditable =”true” method
Q. How to create prod build?
Q. What is the difference between ng serve, ng build and ng build prod?
Q. What is Micro Content?
Q. How to handle multiple api requests using mergeMap and forkJoin in Angular to avoid multiple subscription?
So when do we apply mergeMap?
mergeMap
When we need data from the first API request to make requests to the second API.
flatMap is an alias for mergeMap.
mergeMap maintains multiple active inner subscriptions at once, so it’s possible to create a memory leak through long-lived inner subscriptions.a
 
ForkJoin
This operator is best used when you have a group of observables and only care about the final emitted value of each. It means that forkJoin allows us to group multiple observables and execute them in parallel, then return only one observable.
When do we apply forkJoin?
We use it when API requests are independent. It means that they do not depend on each other to complete and can execute in parallel.
 

Combine mergeMap and forkJoin
 

Q. What is Interface?
A class is a blueprint from which we can create objects that share the same configuration - properties and methods. An interface is a group of related properties and methods that describe an object, but neither provides implementation nor initialisation for them.
Q. How to exclude files at build time in angular?
Q. What is the difference between Model and Interface?
Q. What is Abstract Class and Component in Angular?
Q. What is ViewEncapsulation and ShadowDOM?
Q. What is a template outlet?
Q. Difference between ng-container and ng-template? 
Ng-container create node while ng-template don’t create any node.
Q. What is ActivatedRoute and DeactivatedRoute?
Q. What is Metadata in Angular?
Q. What is Multicasting in Angular?
broadcasting to a list of multiple subscribers in a single execution.
Q. routes dependency in Angular
	Need minimum 2 components.
Q. What is the Router state in Angular?
A router state is an arrangement of application components that defines what is visible on the screen
Q. What are wildcard routes in Angular, what will happen if we will put a wildcard route in the beginning?
Q. What is a State function?
Q. How to load components dynamically?
Q. Tabs behavior in Angular?
Q. Pure and impure pipe Angular pipe
Q. What types of Injections in Angular?
Q. What is Abstract Class and Components in Angular?
Q. How to use Authentication API?
Q. What is switchMap, mergeMap and difference between them?
Q. Angular common module ( where v have http, httpModule, httpClient etc )?
Q. How to pass parameters in routes? Ans. using ( /:id ).
Q. What is ngrx library? How to handle State? How to handle Storage in ngrx? How ngrx storage is differ from Local and Session storage?
Q. What is ngx bootstrap?
Q. What is the difference between FormGroup and FormBuilder?
Q. What is @viewChild scope in lifecycle hooks ? Ans. in ngOnInt() only.
Q. What will return a form when it is valid? Ans. it will return Object.
Q. How to apply form validation on fly ( dynamically )?
Q. What is functional programming?
Below is the link for @parent @child component communication using @Input, @Output:
https://www.youtube.com/watch?v=3srOOe_hI-I

JavaScript
Q. What is “use strict” mode in JavaScript? 
Ans. “use strict” is a directive which defines that JavaScript code will be executed in Strict Mode. With “use strict” mode for example, we can not use undeclared variables.
Mistyping a variable name creates a new global variable. In strict mode, this will throw an error, making it impossible to accidentally create a global variable.
Q. What is reactive programming?
Q. How to get n dimensional array in ES6?
Q. What are the coding guidelines you have used? For example access modifier : public, private
Q. What are the disadvantages of JavaScript?
Q. DateTimePicker(). How to pick only date ? Ans. using date method
Q. What is Debounce and Throttle?
Q. What are the advantages of JavaScript?
Q. What are the differences between Client side and Server side JavaScript?
Q. What is deep and shallow copy in Javascript? What is by default?
Q. What is BOM? Ans => BOM is a Browser Object Model which has Window and Document object model inside it.
Q. Difference between ECMA Script and JavaScript ?
Q. Diff. between Window object and Document object in JavaScript?
Q. How to use JavaScript page function in another javascript page? Like page1. js function into page2.js
Ans. Exporting function or methods form page1.js and importing in page2.js
Q. Scope in JavaScript.
Q. Instance methods in JavaScript?
Q. onClick call multiple API’s with a single method?
Q. What is RXJS library? 


Q. What is setTimeout in JavaScript? 
Q. What is setInterval in JavaScript? 
Q. What is the difference between null and undefined?
Q. What is arrow function, what are the advantages of arrow function? 
https://www.youtube.com/watch?v=wV3HQbg9oaw
https://www.youtube.com/watch?v=qdvGXSUk7Mo

Q. What Event loop in JavaScript? 
Q. What is Event bubbling and Event capturing in JavaScript?  Note: [ this works as parent & child relationship ]
Q. what callback, promise, closure, observable, async, await, anonymous, IIFE function? 
Q. what is scoping (let, const, var) JavaScript?
Q. What is class, constructor, inheritance in JavaScript?
Q. What is classical and prototype inheritance in JavaScript?
Q. Difference between Classical and Prototype inheritance?

Q. What is _ _proto_ _ in JavaScript? 
Q. What is Template Literal in JavaScript? 
Q. What is a Destructuring assignment in JavaScript? 
Q. What are the High Order Function ( sort, filter, slice, push, map, index, indexOf, forEach, reduce, each, every  ) JavaScript?
Q. What is the REST and SPREAD operator in JavaScript?
Q. What is call, apply and bind in JavaScript? 

call()	apply()	bind()
let obj = {things: 3};
let addThings = function(a, b, c){
 return this.things + a + b + c;
};
console.log( addThings.call(obj, 1,4,6) );
It binds totally unrelated object and function and returns result	Same as call() the main difference is the way we can pass arguments. We can pass them as an array.

let obj = {things: 3};
let addThings = function(a, b, c){
 return this.things + a + b + c;
};
let arr = [1,4,6];
console.log( addThings.apply(obj, arr) );
	let obj = {things: 3};
let addThings = function(a, b, c){
 return this.things + a + b + c;
};
console.log( addThings.bind(obj, 1,4,6) );
We expected the number 14, but  Instead, it returned a function. Bind works by returning a copy of the function, but with a different context. We passed obj as the context, but we didn’t execute it.
console.log( addThings.bind(obj, 1,4,6)() );
console.log( addThings.bind(obj)(1,4,6) );
var obj = {num: 2}

var functionName = function(arg1, arg2, arg3){
}
functionName.call(obj, arg1,arg2,arg3);
var x = [arg1, arg2, arg3];
functionName.apply(obj, [arg1,arg2,arg3]);
functionName.apply(obj, [x]);

var bound = functionName.bind(obj);
bound(arg1,arg2,arg3);


Q. What is For in and For of in JavaScript? 
Q. What is Symbol data & Map, set, weakMap, weakSet in JavaScript? 
Q. object methods in JavaScript? 
Q. string methods in JavaScript? 
Q. array methods in JavaScript? 
Q. currying function in JavaScript? 
Q. async operation( fetch API ) in JavaScript? 
Q. What is call by Value and call by reference in JavaScript?
Q. What is the difference between forEach() and map() method?
Ans.
	map()		forEach()
1	map() method returns new array		when forEach() always returns undefined
2	map() method is chainable we can attach reduce(), sort(), filter() like methods		forEach() returns undefined, so it is not chainable
3	If we want to change, alter, mutate data we should use 
map() method		If we don’t want to returned anything, we need to use 
forEach()

Q. PROXY reflections in JavaScript? 
Q. recursion in JavaScript? 
Q. web workers in JavaScript? 
Q. What are the Iterators in JavaScript?
Q. generators in JavaScript? 
Q. How to create an object of Prototype?
Q. What is the difference between local Storage and session storage 
Q. array.prototype in JavaScript
Q. calculate no. of days between two dates
Q. What is JavaScript (void:0)
Q. Expression Function
Q. map()
Q. *ngFor – index methods 
Q. What is observable and what is the usage of Observable
The Observable isn’t an Angular specific feature, but a new standard for managing async data that was included in the ES7 release. Angular uses observables extensively in the event system and the HTTP service.
Observables are a new way of pushing data in JavaScript. An observable is a Producer of multiple values, “pushing” them to subscribers.

Pull
When pulling, the data consumer decides when it get’s data from the data producer.

Push
The data producer (the creator of the newsletter) decides when the consumer (the subscriber to the newsletter) gets the data.
We will probably encounter observables when setting up your HTTP requests.

In Angular we can subscribe to an observable in two ways:
Manner 1:
We subscribe to an observable in our template using the async pipe. The benefit of this is that Angular deals with your subscription during the lifecycle of a component. Angular will automatically subscribe and unsubscribe for you. Don’t forget to import the “CommonModule” into your module, as the async pipe will be exposed from that.

Manner 2:
We subscribe to the observable ourselves using the actual subscribe() method. 

Q. How do you write custom service?

Q. Component communication, parent to child and child to parent ?
There are two types of component communication based on below situation
( i ) When components not logically related use 
1.	Using Browser Storage 
(i) Local Storage
(ii) Session Storage
2.	Route Navigation
(i) Using Snapshot (when data is static)
(ii) Using Observable (when data is live like: Movie ticket booking, share mkt.)

( ii ) When components are logically related
3.	@Input
4.	@ViewChild
5.	@EventEmitter + Output
6.	Behaviour Subject

Q. Angular component compatibility issue in IE ?

Q. What is call() apply() and bind() function? Diff. between Call vs Bind?
https://www.youtube.com/watch?v=PoRJizFvM7s

Q. Async JS Crash Course - Callbacks, Promises, Async Await ?
https://www.youtube.com/watch?v=PoRJizFvM7s
https://www.youtube.com/watch?v=SWWl1o0LT1I&feature=youtu.be [asynchronous programing]

Q. What is lexical scope in JavaScript?
Q. What is method chaining in JavaScript?

What is promise
Why we need it 
Example of simple Promise 
what is finally keyword
Exception handling with promise
Promise Channing
Error handling with promises
Promise.all
promise.allsettled
promise.race
https://www.youtube.com/watch?v=UFdv0DDVGrs

Q. Hoisting in JavaScript? Benefits of Hoisting?
Q. What will happen if there is not Hoisting in JavaScript? Ans => Can not use variable before declaring it.
Q. Garbage collector in JavaScript?
Q. If we have multiple angular pipes together, in which order they will execute
A.	In parallel
B.	LIFO order
C.	In the order which pipes are declared  
D.	None of the above	
Q. What is the difference between PUT and POST?
Q. What is the difference between Agile and Scrum technology?

OnPassive
Q. What is the difference between async and defer?
defer
DOMContentLoaded event handler waits for the deferred script. It only triggers when the script is downloaded and executed.
Deferred scripts keep their relative order, just like regular scripts.
async
async scripts load in the background and run when ready.
DOMContentLoaded and async scripts don’t wait for each other:
The async attribute means that a script is completely independent:

Higher-order functions
A function that accepts a function as an argument or returns a function is called a Higher-order function.
In simpler words, we can take a function and wrap it with another function that as a whole will have the functionality of both the functions.
First Class Functions
Functions in Javascript are first class citizens i.e. they can be assigned to a variable , can be added to an Object and arrays, can be used as an argument to other functions, and can be returned by a function.
Being a first-class citizen provides abilities to write functions in Javascript in various ways.
Function Statements
function greet(){
   console.log("Hello");
}
Function Expressions
// Assigning anonymous function to a variable
const greet = function(){
    console.log("Hello!");
}
// Invoking the function
greet();

What are the Function Factories?
Function factories are functions that return an Object. It is not a class or a constructor, it’s a function that returns or builds an object. The functions that create objects without using the new keyword are function factories.
const firstname = "Ashwani";
const lastname = "Pandey";
const user = ({firstname, lastname}=>{
    firstname,
    lastname,
    greet: function(){
               this.firstname = firstname;
               this.lastname = lastname;
               console.log(`Hello ${this.firstname} ${this.lastname}`); 
           }
});

What is Function Currying?
A Curried function is a function that has multiple arguments but only takes one at a time, each time we pass an argument, the function returns another function waiting for the next argument and repeats the process until all the arguments are passed and the output is returned.
Currying is a transform that makes f(a,b,c) callable as f(a)(b)(c)
we can implement function currying using bind()

Immutability
Immutability is one of the key concepts of Functional programming. Data in functional programming never change, to update the value of a variable we need to create a new variable In javascript, immutability is achieved using const key word. 
const name = "Ashwani"; // Constant variable
const greet = () => {   // Constant function expression
    return "Hello";
}

Pure Functions
Pure functions are functions that take input and return output without modifying any data outside its scope, i.e. every time you pass a set of values as the input you will get the same output irrespective of the changes in the data outside the scope of the function.
const add = (x,y) => x + y;
add(2,3) // Will always return 5

Recursion
Recursion is one of the key topics or pattern that is used in Functional Programming. Recursion is a process wherein a function calls itself again and again inside its function definition until it stops.
// Fibonacci Series
function fibonacci(num){
    if(num==1)
        return 0;
    if (num == 2)
        return 1;
    return fibonacci(num - 1) + fibonacci(num - 2); 
}
In the above example, the Fibonacci function calls itself if the number is greater than 2. When the number decreases to 2 the function returns 1 and the recursion is completed.



jQuery
Q. How to open any specific Accordion using jQuery?
Using active keyword and passing index value of Accordion item like below:
$("#accordion").accordion({ active: 2 });
Q. difference between $each and forEach?
forEach() is a build in Array method and $each() can be used on any type of collection and to use $each we need to include jQuery
Q. which method you will use in jQuery to iterate over an array $each or forEach?
forEach()
Q. have you used any jQuery plugin?
what is method chaining in jQuery
diff between .get .ajax in jQuery
how to detect https and http anchor tags
$('a[href*="http:"]').click(function(){
            alert('Success! Selected link starting with http in href.');
            });
        });
<a href="http://demo" title="new" >Demo1</a><br>
<a href="https://demo" title="new" >Demo2</a><br>
<a href="#demo" title="new" >Demo4</a><br>
<a href="/cplusplus/" title="C++ Tutorial" >C++</a>

onclick next arrow how next image slides behind the seen bootstrap slider


HTML
Q. What is the doctype? What it does? And what if it is not used?
Q. What are the Web Sockets?
The WebSocket API is an advanced technology that makes it possible to open a two-way interactive communication session between the user's browser and a server. With this API, you can send messages to a server and receive event-driven responses without having to poll the server for a reply.
Q. What are Server sent events?
Ans. A server-sent event is when a web page automatically gets updates from a server.
Examples: Facebook/Twitter updates, stock price updates, news feeds, sport results, etc.
Q. What is accessibility in HTML5?
Q. can we use multiple header and footer on a page? Ans. Yes

Q. What are your key strengths apart from your technical skills?
Q. HTML5 main features
Q. Difference between HTML4 and HTML5
1.	Simplify and clear syntax, for example: Doctype difference
2.	Multimedia ( HTML4 need : silverlight or adobe flash player )
3.	Local storage ( HTML4 : cache memory now SQL Database)
4.	Client server comm. ( HTML4 had lengthy cumbersome process now easy through Web Sockets )
5.	JavaScript multithread threading ( inbuilt JS Web worker API to run JavaScript and browser UI runs on different thread  )
6.	Geolocation
Q. What are the semantic elements in html5?
Q. What are the new form tags in HTML5?
Q. What is <iframe> ? use cases of <iframe> ?
Q. How to show a longer text string in a single line dynamically?
Q. How to make HTML pages compatible in older browsers?
Q. have you used any client base element in HTML?
Q. What is the difference between cookies and cache?
Cookies used to store information related to the user while cache is used to make the loading of web pages faster.
Q. difference between Cookies and Storage?

Cookies		Storage	
Cookies are primarily for reading server-side		Storage can only be read by client-side	
Cookies has the limit of 4096 bytes (4096 bytes per cookie)		Storage has the limit of 5MB per domain	
		Stores data in key-value pairs	

Q. What is Local storage and Session Storage?
Q. How to set value in Local and Session storage?
Q. How to make HTML4 responsive?
Q. Canvas in HTML5.
Q. API’s in HTML5, which API’s you have used?
Q. difference between <b> and <strong> tag?
Q. Run video in a banner
CSS
Q. How many types of Position are there in CSS?
Q. What is the default position of HTML elements?
Q. What is Grid layout in CSS?
Q. What is Flexbox in CSS?
Q. What are the CSS methodologies?
Q. What is Object Oriented CSS?
Q. CSS3 Animations (Transition, transform, keframe)
Q. Difference between units (pixels, em, rem)
Q. Box model 
Q. How to set 16 columns in bootstrap grid 
Q. How to make existing non responsive application responsive

Sass
how to use mixin hover 
how to use if else condition in sass
diff between .scss & sass file

Skill - Technical	Rating (X/5)	Comments (Mandatory)
 Angular 2+	2	Asked about routing, interceptors, Error Handle not answer well  by him.
 HTML5 & CSS3	3	
JavaScript	2.5	
 
Skill - Functional	Rating (X/5)	Comments (mandatory)
Project functional explanation	3	He is able to explain his project
Project architecture explanation (module to module integration)	2	
 

 
Tech Lead Questions


Q. What are the development environments?
Q. How many types of development environments?
Q. How to create development environments?
Q. What are the differences between Production, Dev, UAT, QA ?
Q. How to handle different API URLs for different environments?
Q. Is it possible to host any app without Node?
Q. How to set up a project ?
Q. What are the requirements to set up a project in a different environment?
Q. Difference between Git and SVN?
Q. how you merge code
Q. Development methodologies
Q. how frequently you deploy code on Staging and Production
Q. Change detection







Question
1. Write a function to remove a value from array? (for 3 to 5 years experienced candidate)
2. Write a function to get Max value of a number Array? (for 3 to 5 years experienced candidate)
3. Write a function to find indexes of value from a sorted array. (for 3 to 10 years experienced candidate)
4. Write a function to find average marks by subject. Given Data is in following format.
data = [{
id: "Unique String Value",
subject: "Any String Value",
marks: number value
}] (for 3 to 5 years experienced candidate)
5. Write a method to check whether 2 strings are made up of same characters (for 3 to 5 years experienced candidate)
6. Write a program to render customer list in a table. With Each row having a remove button in Angular (for 3 to 5 years experienced candidate)
7. How to monitor memory, CPU of Web Application? (for 6 to 10 years experienced candidate)
8. If your Page is crashing due to high memory and high CPU Usage than how you will resolve? (for 6 to 10 years experienced candidate)
9. Write a function to sort date and time column in a table (for 6 to 10 years experienced candidate)
10. Write a method to reverse an Array of n integers (for 3 to 10 years experienced candidate)
