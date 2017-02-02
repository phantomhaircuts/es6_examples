
## BLOCK SCOPE (LET VAR CONST) EXAMPLES

```js
//Declare a Variable ES5
var user = {
  name: 'Erik',
  password: 'abcd',
  permissions: [ ]
}
console.log(user);
```

```js
// BLOCK SCOPE WITH LET ///////////////////////////////////////////////////////

if(true){
  let user = {
    name: 'Erik',
    password: 'abcd',
    permissions: [ ]
  };
  console.log(user + ' inside the block');
}
console.log(user + ' outside the block');
```

```js
// Try to redefine Const
const loggedIn = true;

console.log(loggedIn);

loggedIn = false;

// Now try to change a property in const.
const user = {
  name: 'Erik',
  password: 'abcd'
  permissions: [ ]
};
// change property...
user.password('efgh');
console.log(user);

// now try to update the whole object
user = {
  name: 'Adrian',
  password: 'poop',
  permissions:[]
};
//! ERROR
```

## Default Params Examples
```js
//ES5
let user = {
  name: 'Erik',
  password: 'abcd'
  permissions: [ ]
  updatePassword: function(newPassword){
    this.password = newPassword || 'password';
  }
}

user.updatePassword();
user.updatePassword('banana$$$$');
//Try default params in ES6//////////////////////////////
let user = {
  name: 'Erik',
  password: 'abcd',
  permissions: [ ],
  updatePassword: function(newPassword = 'password'){
    this.password = newPassword;
  }
}
user.updatePassword();
user.updatePassword('banana$$$$');
```

## DESTRUCTURING EXAMPLES
```js
//ex 1
let [newName, newPassword] = ["James", "bunny987"] // show destructuring with array to assign multiple variables
console.log(newName)
console.log(newPassword)

//ex 2
let user = {
  name: 'Erik',
  password: 'abcd',
  permissions: [],
  updatePassword: function(newPassword = 'password'){
    this.password = newPassword;
  }
}
//ES5
console.log('my name is ' + user.name + 'and my password is ' + user.password);

//ES6
function greeting ({name, password}) {
  console.log('my name is ' + name + ' and my password is ' + password);
}
greeting(user);
```

## CONCISE OBJECT PROPERTIES AND METHODS
```js
// EX 1  (shorten method definitions)

//ES5
let user = {
  name: 'Erik',
  password: 'abcd',
  permissions: [],
  updatePassword: function(newPassword = 'password'){
    this.password = newPassword;
  }

  //ES6
  let user = {
    name: 'Erik',
    password: 'abcd',
    permissions: [],
    updatePassword(newPassword = 'password'){
      this.password = newPassword;
      console.log('new pw is: ' + this.password)
    }
  }
user.updatePassword('boop');

// Ex 2 (properties)
let name = 'erik';
let password = 'abcd';
let user = {name, password};
console.log(user);
```

```js
//TEMPLATE LITERALS////////////////////////////////////////////////////////////////////////////////////////////
let user = {
  name: 'Erik',
  password: 'abcd',
  permissions: [],
  updatePassword(newPassword = 'password'){
    this.password = newPassword;
    console.log('new pw is: ' + this.password)
  }
}

console.log(`Hello. My name is ${user.name} and my password is ${user.password}!`)

//ARROW FUNCTIONS//////////////////////////////////////////////////////////////////////////////////////////////////
let user = {
  name: 'Erik',
  password: 'abcd',
  permissions: [],
  updatePassword(newPassword = 'password'){
    this.password = newPassword;
    console.log('new pw is: ' + this.password)
  },
    autoPost() {
     setInterval( () => {
       console.log(`${this.name}'s Status: Studying Javascript right now and it's tighhhhhht!`)
    }, 1000)
  },
  add(x, y) => x + y;
}
user.autoPost()
```
