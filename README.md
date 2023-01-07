Node js
Express
React Js
mongo db


JS:
day 1:
document, console, alert, variables, data types,
operators, ternary operator, 
control structures

functions: definition, call
let, var, const
callback functions

arrays, forEach(), map(), reduce(), filter()

function show(){
	var a=5;
	log(a)
}

show();
log(a);

   var obj1={id:101,name:'John'};
       var obj2={email:'john@example.com',age:28}
       var obj3={address:'A-189',...obj1,...obj2};
        console.log(obj3);
        var a=[1,2,3,4];
        var b=[6,7,8];
        var c=[10,20,30,...a,...b];
        console.log(c);


synchronous: blocking nature
asynchronous: non blocking nature
callback
p1 4 sec
p2 2 sec
p3 1 sec
log()

setTimeout(func,2000)
log()

setTimeout((a) => {
        console.log("in set timeout");
        console.log(a);
    }, 2000,5);
    console.log("after set timeout");

sum 2000
factorial 4000
cube  1500


callback hell

Promise
pending
resolve
reject

1. create a new promise
2. execute the promise
3. handle the promise


const myPromise=new Promise((resolve,reject)=>{
	var n=4;
	if(n%2==0){
		resolve();
	}
   else{
		reject();
	}
}); 

then() resolve catch() reject

myPromise.then(()=>{}).catch(()=>{});




const myPromise = new Promise((resolve, reject) => {
            var n = 6;
            if (n % 2 == 0) {
                resolve(n);
            }
            else {
                reject("not div by 2");
            }
        });

        myPromise.then((result)=>{
            console.log(result +" is even");
        }).catch((error)=>{
            console.log(error);
        });




var a=4;
        var b=6;
        var c=a+b;
        console.log("sum of "+a+" and "+b+" is "+c);
        console.log(`sum of ${a} and ${b} and is ${c}`);

 

  function sum(a,b) {
                return new Promise((resolve,reject)=>{
                    setTimeout(() => {
                        resolve(a+b)
                    }, 2500);
                });
            }
            function factorial() {
                return new Promise((resolve,reject)=>{
                    setTimeout(() => {
                        resolve(120)
                    }, 4500);
                });
            }

            sum(2,3)
            .then((c)=>{
                console.log("sum is "+c);
                return factorial()
            })
            .then((f)=>{
                console.log("factorial is "+f);
            })
            .catch(()=>{});

async await keyword
async function handlePromise() {
                try {
                    const c=await sum(2,3);
                    console.log(c);
                    const f=await factorial();
                    console.log(f);
                } catch (error) {
                    console.log(error);
                }
            }
            handlePromise();




DOM manipulate

1. new element
2. remove elements
3. get content
4. change content
5. css change
6. get attribute
7. change attribute


document is object of DOM 


<h1 id="myhead">hello world</h1>
	<button type="button" onclick="get()">Click me</button>
	<script type="text/javascript">
		function get() {
			var h1=document.getElementById('myhead');
			console.log(h1.innerHTML);
			h1.innerHTML="bye";
		}	
  		
	</script>


<input type="password" id="passwordField">
	<input type="button" value="show" id="btn" onclick="show()">
	<script type="text/javascript">
		function show() {
			var btn=document.getElementById('btn');
			var passwordField=document.getElementById('passwordField');
			if (btn.getAttribute('value')=='show') {
				passwordField.setAttribute('type','text');
				btn.setAttribute('value','hide');
			} else {
				passwordField.setAttribute('type','password');
				btn.setAttribute('value','show');
			}
			
		}
  		
	</script>


if variable name is same as id of the element:

<input type="password" id="passwordField">
	<input type="button" value="show" id="btn" onclick="show()">
	<script type="text/javascript">
		function show() {
			if (btn.getAttribute('value')=='show') {
				passwordField.setAttribute('type','text');
				btn.setAttribute('value','hide');
			} else {
				passwordField.setAttribute('type','password');
				btn.setAttribute('value','show');
			}
			
		}
  		
	</script>


change css:
<input type="text" id="nameField" onkeyup="check()">
	<script type="text/javascript">
		
		function check() {
			if(document.getElementById('nameField').value.length>=3){
				document.getElementById('nameField').style.borderColor='green';
			}
			else{
				document.getElementById('nameField').style.borderColor='red';
			}
		}
  		
	</script>



create element:
<input type="button" id="btn" value="generate" onclick="generate()">
	<div id="container">

	</div>
	<script>
		function generate() {
			var h1=document.createElement('h1');
			h1.innerHTML='hello world';
			document.getElementById('container').appendChild(h1);
		}
	</script>



remove element:
<input type="button" id="btn" value="remove h1" onclick="remove()">
	<div id="container">
		<h1 id="head">Welcome</h1>
	</div>
	<script>
		function remove() {
			var container=document.getElementById('container');
			var head=document.getElementById('head');
			container.removeChild(head);
		}
	</script>


AJAX:
asynchronous Javascript and xml

1. create an object of XMLHttpRequest
	 var xhr=new XMLHttpRequest();

2. initialize xhr object
	 xhr.open(method,url);

3. send request
	xhr.send()

4. get response
readyState is number
   0 1 2 3 4




<input type="button" value="fetch" onclick="fetchData()">
	<script>
		function fetchData() {
			var xhr= new XMLHttpRequest();
			xhr.open('GET','https://jsonplaceholder.typicode.com/users');
			xhr.send();
			xhr.onreadystatechange=()=>{
				if (xhr.readyState==4 && xhr.status==200) {
					var data=JSON.parse(xhr.responseText);
					console.log(data);
				}
			}
			
		}
	</script>


fetch() api 



<input type="button" value="fetch" onclick="fetchData()">
	<script>
		async function fetchData() {
			try {
				const response=await fetch('https://jsonplaceholder.typicode.com/users');
				const data=await response.json();
				console.log(data);
			} catch (error) {
				console.log(error);
			}
			
			
		}
	</script>

Node js:
runtime environment

module: 

predefined modules: http , fs , path ,
user defined modules: .js
3rd party modules: dependencies

npm node package manager
npm install dependency-name
npm i name

root folder: index.js-> start , package.json  -> name, version, description, author, lice, dependencies
.env

npm init 

npm i dotenv 

require() function common js 
import statement es  

nodemon cli


3rd party module
local: functions and properties
global : cli 

-s save 
npm i module-name -g 








































