# Arrow Functions

## Basic Syntax with One Parameter
```javascript
// ES5

function double(number) {
  return number * 2;
}

// ES6

double = number => number * 2;
```

## Basic Syntax with Multiple Parameters
```javascript
// ES5

function sum(a, b) {
  return a + b;
}

// ES6

let sum = (a, b) => a + b;
```

## No Parameters
```javascript
// ES5

function printHello() {
  return console.log('Hello');
}

// ES6

let printHello = () => console.log('Hello');
```

## Basic Syntax with anonymous function

```javascript
// ES5

document.addEventListener('click', function() {
  console.log('Click');
})

// ES6

document.addEventListener('click', () => console.log('Click'));
```

## Keyword *this*
```javascript
// Example

class User {

  constructor(name) {
    this.name = name;
  }

  printNameArrow() {
    setTimeout(() => {
      console.log(`Arrow: ${this.name}`)
    }, 100);
  }

  printNameFunction() {
    setTimeout(function() {
      console.log(`Function: ${this.name}`)
    }, 100);
  }
}

let user = new User('John Doe');

user.printNameArrow();     // Arrow: John Doe
user.printNameFunction();  // Function:


// Another example

function User(email, roles) {

  this.email = email;
  this.roles = roles;

  this.getRolesFunction = function() {
    return this.roles.map(function(role) {
      console.log(this.email + ' has the privilege : ' + role)
    })
  }

  this.getRolesArrow = function() {
    return this.roles.map( role => {
      console.log(this.email + ' has the privilege : ' + role)
    })
  }
}

let user = new User('john.doe@mail.com', ['ROLE_USER', 'ROLE_ADMIN']);

user.getRolesFunction();

// undefined has the privilege : ROLE_USER
// undefined has the privilege : ROLE_ADMIN

user.getRolesArrow();

// john.doe@mail.com has the privilege : ROLE_USER
// john.doe@mail.com has the privilege : ROLE_ADMIN
```