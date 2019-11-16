
Arithmeetic Operators\\\\\\\\\\\



https://www.toptal.com/javascript/interview-questions



https://www.glassdoor.com/Interview/Facebook-Solutions-Engineer-Interview-Questions-EI_IE40772.0,8_KO9,27.htm







1)


var bar = null;
console.log(typeof bar === "object");  // logs true!
console.log((bar !== null) && (typeof bar === "object"));  // logs false
2)

var a = b = 3;   --> .  

b = 3;

var a = b;
so a undefined and b defined





3)

this keyword



var myObject = {

    foo: "bar",

    func: function() {

        var self = this;

        console.log("outer func:  this.foo = " + this.foo); // this refer to myObject

        console.log("outer func:  self.foo = " + self.foo); // self will scope in Function

        (function() {

            console.log("inner func:  this.foo = " + this.foo); // this will be global and return null

            console.log("inner func:  self.foo = " + self.foo); // will srturn same value bar

        }());

    }

};

myObject.func();

In the outer function, both this and self refer to myObject and therefore both can properly reference and access foo.

In the inner function, though, this no longer refers to myObject. As a result, this.foo is undefined in the inner function, whereas the reference to the local variable self remains in scope and is accessible there.





var hero = {
    _name: 'John Doe',
    getSecretIdentity: function (){
        return this._name;
    }
};

var stoleSecretIdentity = hero.getSecretIdentity;

console.log(stoleSecretIdentity());  // undefined
console.log(hero.getSecretIdentity()); //John Doe


4)

use strict -->  to enforce stricter parsing

adv --> makes debug easy , prevents default globals







5)

Number equal check

function areTheNumbersAlmostEqual(num1, num2) {
 return Math.abs( num1 - num2 ) < Number.EPSILON;
}
console.log(areTheNumbersAlmostEqual(0.1 + 0.2, 0.3));




6

function isInteger(x) { return Math.round(x) === x; }



7

A closure is an inner function that has access to the variables in the outer (enclosing) function’s scope chain. The closure has access to variables in three scopes; specifically: (1) variable in its own scope, (2) variables in the enclosing function’s scope, and (3) global variables.

var globalVar = "xyz";

(function outerFunc(outerArg) {
    var outerVar = 'a';

    (function innerFunc(innerArg) {
    var innerVar = 'b';

    console.log(
        "outerArg = " + outerArg + "\n" +
        "innerArg = " + innerArg + "\n" +
        "outerVar = " + outerVar + "\n" +
        "innerVar = " + innerVar + "\n" +
        "globalVar = " + globalVar);

    })(456);
})(123);


8)

Closures can be used to prevent this problem by creating a unique scope for each iteration, storing each unique value of the variable within its scope, as follows:







9)Visiting all elements in the Tree

function Traverse(p_element,p_callback) {
   p_callback(p_element);
   var list = p_element.children;
   for (var i = 0; i < list.length; i++) {
       Traverse(list[i],p_callback);  // recursive call
   }
}




10)Clone Object

var obj = {a: 1 ,b: 2}
var objclone = Object.assign({},obj);


11)

Adding to array

var myArray = ['a', 'b', 'c', 'd'];
myArray.push('end');
myArray.unshift('start');
console.log(myArray); // ["start", "a", "b", "c", "d", "end"]


12)



1
