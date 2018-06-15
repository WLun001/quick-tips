INTERACTION TECHNIQUES IN ANGULAR 2

0. Prerequisite: Inside one component

1. Direction from parent to child component

2. Direction from child to parent component

3. Between arbitrary components

4. Connecting directives and their host elements



## 0. Prerequisite: Inside one component

### 0.1. You want to assign TypeScript constructor parameters without typing too much

You can use the shorthand syntax. But don’t forget the modifier (private or public).

Simple code example: http://plnkr.co/edit/H6d8pbKPSzAEwdD5k7JZ?p=preview

 
### 0.2. You want to use the changing values of a component’s class body directly in its template?

You can use property binding (normally used for properties of DOM elements).

Simple code example: http://plnkr.co/edit/ZzVEY5E7LGB6EK4PsBq3?p=preview

If the value is a string, you can use string interpolation (normally used for the text between HTML tags).

Simple code example: http://plnkr.co/edit/OVPtPM76BGCh8JTdH2FN?p=preview

**Attention! [ngStyle] and [ngClass] expect expressions that evaluate to JavaScript objects (no string interpolation here!)**

Simple code example: http://plnkr.co/edit/PghxL5gqFbiypyNFdO4m?p=preview

 
### 0.3. You want to listen in a component’s class body to events from its template?

Use event binding syntax.

Simple code example: http://plnkr.co/edit/NmsFGwa2rCIZ8QAc3cR5?p=preview
 
### 0.4. You want to access an HTML element of a template in this template itself?

Use a template reference variable.

Simple code example: http://plnkr.co/edit/DM4WigaDGTVk8KhIIOgj?p=preview


### 0.5. You want to access an HTML element of a template in the class body of the same component?
 
Use a template reference variable in the template and @ViewChild in the class body.

Simple code example: http://plnkr.co/edit/r7rIJ7nYf9XeuYLyo3HQ?p=preview



## 1. Direction from parent to child component

### 1.1. You want to pass values from a parent component to a child component?

Use property binding syntax in the <child> selector of the parent‘s template, and the @Input() decorator in the child‘s class body.

Simple code example: http://plnkr.co/edit/AYypCH8GHLwsFMLdCkT1?p=preview

You can use an alias for the @Input() variable.

Simple code example: http://plnkr.co/edit/7g2H8kNArY8ChZXhmjYH?p=preview

You can use a getter and a setter for the @Input() variable.

Simple code example: http://plnkr.co/edit/VWNz5Zp2XnItFPS1cw4o?p=preview

 
### 1.2. You want to detect in a child component, when the value from the parent component changes?
 
Use ngOnChanges().

Simple code example: http://plnkr.co/edit/mvKIDCZWrtEkhmUnisUm?p=preview
 

### 1.3. You want to display HTML content of the parent component in the child (and not in the parent)?
 
Use <ng-content>  and the selector attribute in the child’s template to display certain HTML that is placed between the tags of the child selector in the parent’s template.
Simple code example: http://plnkr.co/edit/Ty0iVlGpmhgMeUrPiLLn?p=preview

### 1.4. You want to display HTML content of the parent component in the child and let the child modify it?

Use <ng-content> in the child’s template to display an HTML element that is placed between the tags of the child selector in the parent’s template, a template reference variable in the parent’s element, and the @ContentChild decorator in the child’s class body to access it.

Simple code example: http://plnkr.co/edit/Bzuj5XDp0Il0XxLS6riE?p=preview

## 2. Direction from child to parent component
 
### 2.1. You want to listen to child’s events in the parent component?

 

Use event binding syntax in the <child> selector of the parent‘s template, and the @Output decorator with an EventEmitter object in the child‘s class body.

Simple code example: http://plnkr.co/edit/zksZ6QdatHJ9AJSG7lLL?p=preview

 

### 2.2. You want to use child’s values in the parent’s template directly?

 

Use a template reference variable # in the child selector of the parent‘s template, and dot notation childname.value in the parent’s template.

Simple code example: http://plnkr.co/edit/2aKWvNcU3AJTcC2vlXiy?p=preview

 

### 2.3. You want to read and write child’s values in the parent’s class body?

 

Use @ViewChild in the parent’s class body to get a reference to the child component (and to the child’s values via dot notation childname.value).

Simple code example: http://plnkr.co/edit/Pu4LfdbT4DC87rYDsQL7?p=preview


  

## 3. Between arbitrary components


  

### 3.1.You want to transfer values between independent components synchronously?

 

Use a synchronous service to store data, and inject it into both components (using their constructors).

Simple code example: http://plnkr.co/edit/tF85pFSxhO7am7FXoVBx?p=preview

 

### 3.2.You want to transfer a stream of values between independent components?

 

Use an asynchronous service with an Observable, and inject it into both components (using their constructors).

Simple code example: http://plnkr.co/edit/p0AmWd9TfomDf9RlshQA?p=preview


 

## 4. Connecting directives and their host elements


 

### 4.1. You want to access the host element of a directive in the directive’s class body?

 

You can use the @HostBinding and @HostListener decorators in the directive’s class body.

Simple code example: http://plnkr.co/edit/5NdbT077R42FLvcan4sE?p=preview

 

Or you can use ElementRef and various renderer methods in the directive’s class body.

Simple code example: http://plnkr.co/edit/T6jyqyoy9koTVhkks1lM?p=preview
